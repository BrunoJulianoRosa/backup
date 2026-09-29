---
name: seo-howz
description: "Esteira de diagnóstico da Howz para uma loja ou negócio local: pede site e Instagram, audita o site com /seo-audit, avalia a copy do site e do Instagram com o rigor da /ads-copywriter, e entrega tudo numa página compartilhável feita com /design-taste-frontend, nas cores da marca. Use SEMPRE que o operador disser \"faz um SEO da loja X\", \"audita o site de X\", \"analisa o site e o Instagram de X\", \"me dá um diagnóstico do site X\", \"relatório de SEO pra cliente\", \"roda o seo-howz\", ou invocar /seo-howz. Use também quando ele mandar só uma URL ou um @ de Instagram e pedir \"o que dá pra melhorar\". NÃO use para escrever anúncios do zero sem auditar nada (isso é /ads-copywriter sozinha), nem para plano de marketing completo por AARRR (isso é /marketing-plan)."
---

# SEO Howz, diagnóstico de site e Instagram em três passos

Esta skill encadeia três etapas que já existem como skills independentes e fecha com uma entrega que a cliente consegue abrir num link. Ela não reimplementa auditoria, copy ou design. O trabalho dela é garantir a ordem, o que entra em cada etapa e o formato do que sai.

```
site + @instagram  →  /seo-audit  →  /ads-copywriter (avaliar copy)  →  /design-taste-frontend (página do relatório)
```

O operador é uma agência (Howz) entregando para uma cliente que não é técnica. Isso muda duas coisas em relação a uma auditoria de SEO comum: cada achado precisa dizer o que a loja perde com ele, e o relatório precisa ser bonito o bastante para ser encaminhado sem retrabalho.

Crie uma lista de tarefas (`TaskCreate`/`TaskUpdate`, se disponível) com os quatro passos abaixo e marque cada um conforme fecha. São etapas de minutos cada e o operador acompanha por ela.

## Passo 1: pedir site e Instagram

Pergunte direto no chat, em texto livre:

> Qual o site e o Instagram da loja? (ex.: `www.loja.com.br` e `@loja`)

Se a mensagem que disparou a skill já trouxe os dois, não pergunte de novo. Se trouxe só um, pergunte o outro uma vez e siga com o que tiver se ele não responder: o Instagram sozinho ainda rende análise de copy e prova social, e o site sozinho ainda rende a auditoria inteira.

Pergunte junto, na mesma mensagem, se há **prazo ou verba** em vista. Não é obrigatório, mas muda o plano de ação da Parte 3 do relatório. Se não vier, assuma e declare a premissa no relatório em vez de travar.

Guarde `{site}`, `{instagram}` e a cidade (descubra pelo próprio site ou pelo Perfil de Empresa no Google se o operador não disser).

## Passo 2: auditar o site com /seo-audit

Invoque `Skill` com `skill: "seo-audit"` e em `args` passe o contexto já resolvido, para a etapa não perguntar de novo:

```
args: "Site: {site}. Negócio local em {cidade}, {segmento}. Foco: SEO local, on-page, técnico e conversão de lead. Sem acesso ao Search Console."
```

O que a `/seo-audit` faz bem sozinha é o framework (rastreio, indexação, on-page, conteúdo, autoridade). O que ela não sabe, e você precisa cobrir por cima dela, veio de rodadas reais desta esteira:

**Acesso ao site.** Sites de loja costumam ter firewall (Azion, Cloudflare) que devolve 403 para `curl`, e o proxy do ambiente pode bloquear o domínio inteiro. Tente nesta ordem e pare no primeiro que funcionar: `WebFetch`; navegador embutido (Playwright com o Chromium pré-instalado); `mcp__Exa__web_fetch_exa` em lote com várias URLs; `mcp__Exa__web_search_exa` com `site:` para pelo menos listar as páginas indexadas. Se nada abrir o HTML, o Exa ainda entrega o texto das páginas, e isso basta para títulos, descrições, H1 e conteúdo fino. Diga no relatório o que foi lido diretamente e o que foi inferido.

**Dados de ferramenta.** Tente o Semrush (`mcp__Semrush__*`) para volume e posição. Se voltar `no_api_units` ou sem assinatura, não invente número: faça buscas manuais no Google para as 6 a 10 consultas mais importantes e registre a posição aproximada com a data. Marque dificuldade e oportunidade como estimativa qualitativa. O mesmo vale para o Firecrawl sem créditos.

**Cheque estes pontos sempre**, porque são onde uma loja local perde lead e a auditoria genérica não olha:
- Tags de conversão: ID do Google Ads malformado (ex.: `AW-AW-…`), mais de um GA4 carregando, pixel duplicado.
- Links de WhatsApp: número com dígito a mais ou a menos (ex.: `5555…`), link que não abre a conversa.
- Consistência de nome, endereço e telefone entre site, schema e Perfil de Empresa no Google.
- Schema `LocalBusiness` ou equivalente do segmento (`ClothingStore`, `Restaurant`), com horário e coordenadas.
- Páginas de marca ou categoria vazias indexadas, página de login indexada, duplicatas sem canonical.
- O diferencial que o negócio tem e o site não fala. Em lojas de roupa foi a numeração; em restaurantes costuma ser estacionamento ou horário; procure no Perfil do Google e nas avaliações o que as clientes elogiam e confira se está no site.
- Concorrentes: os 3 que aparecem nas mesmas buscas, com posição, seguidores e avaliações, para a cliente ver onde ganha e onde perde.

Ao terminar, guarde as tabelas em `{pasta}/seo-{slug}-{AAAA-MM-DD}.md` (o slug é o nome da loja em kebab-case). Confira o nome real do arquivo antes de seguir.

## Passo 3: avaliar a copy com /ads-copywriter

A `/ads-copywriter` é uma skill de geração, não de análise. Use a régua dela (headline com palavra-chave, prova, CTA, limite de caracteres por plataforma, variantes A/B) para **julgar a copy que já existe** e só depois propor a reescrita.

Antes de invocar, reúna o material: títulos e descrições das páginas principais, texto da home, da página "sobre", das categorias, a bio do Instagram, as legendas dos 6 a 10 posts mais recentes e os depoimentos. Se o Instagram não abrir por ferramenta, `mcp__Exa__web_search_exa` costuma trazer bio e alguns posts; registre o que não foi possível ler.

Invoque `Skill` com `skill: "ads-copywriter"` e em `args`:

```
args: "Avalie a copy existente de {loja} antes de gerar qualquer coisa. Material: {resumo do que foi coletado}. Para cada peça: nota de 1 a 5, o que quebra (clareza, prova, CTA, palavra-chave, diferencial ausente) e a reescrita. Depois gere: 3 títulos e 2 descrições para busca local no Google, 3 variantes de anúncio no Meta com formulário de lead, e uma nova bio do Instagram. Em português do Brasil."
```

O ponto que mais rende aqui é o cruzamento com o Passo 2: se a auditoria achou um diferencial que o site não comunica, a copy nova precisa carregá-lo. Se a `/ads-copywriter` devolver copy genérica ("qualidade e conforto para você"), rejeite e peça de novo com o diferencial nomeado. Copy genérica é o mesmo que nada para uma loja local.

Salve em `{pasta}/copy-{slug}-{AAAA-MM-DD}.md`.

## Passo 4: montar a página do relatório com /design-taste-frontend

Invoque `Skill` com `skill: "design-taste-frontend"` e depois carregue também `artifact-design` (o skill de design cobre o gosto, o de artifact cobre o contrato técnico da página publicada: título, tokens de tema claro e escuro, largura de celular, CDN permitida). Os dois juntos, sempre.

Leia `references/relatorio.md` desta skill: ele traz a estrutura das três partes do relatório e o que vai em cada uma. Preencha com o conteúdo dos Passos 2 e 3.

**Cores da marca.** Tente ler o CSS do site (`meta theme-color`, variáveis `--color-*`, cor do botão principal, cor do logo). Se o site não abrir, derive das pistas que tiver (cores dos produtos no catálogo, feed do Instagram) e **diga no relatório e no chat que a paleta é uma assunção**, com os tokens nas três primeiras linhas do CSS para a troca ser imediata quando os hex reais chegarem. Uma página bonita nas cores erradas é pior do que uma neutra, porque a cliente percebe na hora.

**Regras que valem para este relatório e que o skill de design já exige:** zero travessão (`—` ou `–`) em qualquer texto visível; um acento de cor só, travado na página inteira; sem roxo de IA, sem três cards iguais, sem etiqueta em caixa alta acima de toda seção; tabelas dentro de contêiner com rolagem horizontal; tema claro e escuro; funcionando em 400 px de largura. Antes de publicar, rode uma contagem de travessões no arquivo. Não é opcional.

**A seção "O que esta rodada não cobre" fica logo abaixo da abertura**, visível. Ela lista o que não foi possível medir (ferramenta sem crédito, site bloqueado, posição manual com data). Esconder isso faz a cliente cobrar depois um número que a agência não tem.

Publique com a ferramenta `Artifact` (ícone `report`), com `description` de uma frase. A página nasce privada; avise o operador que a cliente só abre depois que ele compartilhar pelo menu Share da página. Dê o link no chat com um resumo de 4 a 6 linhas do que a página traz. Não repita o relatório inteiro no chat.

## Se algo travar no meio

- **Site e Instagram bloqueados e o Exa também não traz nada:** entregue mesmo assim a parte que depende só de busca (posições manuais, concorrentes, Perfil do Google) e marque o resto como pendente de acesso. Diga ao operador qual host precisa ser liberado na política de rede do ambiente.
- **Uma das três skills não está instalada:** diga isso ao operador em vez de reimplementar a etapa. Esta skill só orquestra.
- **Operador pede só um passo** ("só a copy", "só a página"): rode o passo pedido com o material que existir na pasta (`seo-*.md`, `copy-*.md`) e não refaça os anteriores.
- **Já existe relatório da mesma loja:** publique uma nova versão com `url` do artifact anterior para manter o link, a menos que o operador peça uma página separada.

## O que esta skill nunca faz

- Inventar volume de busca, posição ou dificuldade sem ferramenta e sem busca manual datada.
- Assumir a paleta do site sem dizer que assumiu.
- Compartilhar a página com a cliente por conta própria. Quem compartilha é o operador.
- Esconder os limites da rodada para o relatório parecer mais completo.
