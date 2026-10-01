---
name: colinha-eleicao-2026
description: Cria o app "Colinha da Eleição 2026", uma página web de uma tela onde o eleitor escolhe o estado (UF), busca os candidatos reais do TSE e monta a colinha com Presidente, Governador, 2 Senadores, Deputado Federal e Deputado Estadual (ou Distrital no DF). Use quando o usuário pedir "colinha da eleição", "cola eleitoral", "app pra anotar meus candidatos", "lista de números pra levar na urna" ou invocar /colinha-eleicao-2026.
---

# Colinha da Eleição 2026

Entrega: um app web (HTML + JS puro, sem build) que gera a colinha no visual de cartões: foto, cargo, nome e os dígitos em quadrados laranja seguidos do botão verde "CONFIRMA".

## 1. Fluxo do usuário

1. Primeira tela: só um seletor de **UF** (27 opções, incluindo DF).
2. Ao escolher a UF, o app carrega os candidatos daquele estado + os candidatos a Presidente (nacionais).
3. Seis campos, nesta ordem (a mesma da urna):
   | Campo | Código TSE | Dígitos |
   |---|---|---|
   | Deputado Federal | 6 | 4 |
   | Deputado Estadual (Distrital no DF: código 8) | 7 / 8 | 5 |
   | Senador 1 | 5 | 3 |
   | Senador 2 | 5 | 3 |
   | Governador | 3 | 2 |
   | Presidente | 1 | 2 |
4. Cada campo é um **combobox** com três formas de achar o candidato:
   - digitar o **número** (filtra por prefixo: "15" mostra 1510, 1515...)
   - digitar o **nome** (filtra por nome de urna, sem acento e sem caixa: "derrite" acha "DERRITE")
   - abrir a **lista suspensa** com um botão de ordenação: **A→Z** (nome de urna) ou **0→9** (número crescente)
5. O Senador 2 não pode repetir o Senador 1: remova da lista o já escolhido.
6. Botões finais: **Imprimir** (CSS `@media print` só com os cartões) e **Salvar imagem** (html2canvas via cdnjs). Guarde as escolhas em `localStorage` por UF, com try/catch.

## 2. Fonte dos dados (TSE / DivulgaCandContas)

Base: `https://divulgacandcontas.tse.jus.br/divulga/rest/v1`

1. Descobrir o ID da eleição geral de 2026 (nunca chumbe o ID sem conferir):
   `GET /eleicao/ordinarias` → pegue o item com `ano == 2026` e turno 1. Registre o `id` encontrado no código como constante, com a data da conferência.
2. Listar candidatos:
   `GET /candidatura/listar/2026/{UE}/{idEleicao}/{codCargo}/candidatos`
   - Presidente: `UE = BR`
   - Demais cargos: `UE = sigla da UF` (ex.: `SP`)
3. Campos úteis de cada item: `numero`, `nomeUrna`, `nomeCompleto`, `partido.sigla`, `descricaoSituacao`, `id`.
4. Foto: `GET /candidatura/buscar/foto/2026/{UE}/{idEleicao}/{idCandidato}` (ou o campo `fotoUrl` quando vier no payload).
5. Mostre só candidaturas aptas: descarte `descricaoSituacao` com "Indeferido", "Renúncia", "Cancelado", "Falecido". Exiba um selo "sub judice" para "Pendente de julgamento" / "Deferido com recurso".

### Plano B obrigatório (o TSE cai e bloqueia CORS)

A API do TSE não envia cabeçalho CORS confiável e fica instável perto da eleição. Chamar direto do navegador vai quebrar. Faça assim:

- **Gere um snapshot estático** com um script (Node ou Python) que baixa todos os cargos das 27 UFs + BR e salva `data/{UF}.json` e `data/BR.json`. O app lê esses JSONs locais.
- Alternativa ao script: Dados Abertos do TSE, `https://cdn.tse.jus.br/estatistica/sead/odsele/consulta_cand/consulta_cand_2026.zip` (CSV `;`, encoding latin-1, colunas `SG_UF`, `CD_CARGO`, `NR_CANDIDATO`, `NM_URNA_CANDIDATO`, `SG_PARTIDO`, `DS_SITUACAO_CANDIDATURA`).
- Mostre no rodapé: "Dados do TSE atualizados em {data do snapshot}". Sem isso o usuário não sabe se a lista está velha.

## 3. Regras de qualidade (teste antes de entregar)

- [ ] SP carrega e lista os 6 campos; DF troca "Estadual" por "Distrital" e usa código 8.
- [ ] Busca por "1515", "15" e "baleia" retorna o mesmo candidato.
- [ ] Ordenação A→Z e 0→9 funciona nas duas direções e não perde o filtro digitado.
- [ ] Senador 2 não aceita o mesmo número do Senador 1.
- [ ] Número digitado que não existe mostra "Número não encontrado (na urna vira voto nulo)".
- [ ] Campo vazio fica permitido e aparece como "Em branco / não escolhido" na colinha.
- [ ] Layout funciona em 360px de largura (o uso real é no celular, na fila da seção).
- [ ] Funciona offline depois de carregado (o snapshot vem junto).

## 4. Neutralidade

O app não sugere, ordena por popularidade nem destaca partido algum. Ordem só alfabética ou numérica. Sem nenhum candidato pré-selecionado.

## 5. Aviso legal no app

Celular é proibido na cabine de votação (Res. TSE). Exiba: "Imprima ou anote no papel: o celular fica com o mesário." A colinha em papel é permitida.
