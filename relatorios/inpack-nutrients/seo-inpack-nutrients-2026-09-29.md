# Auditoria de SEO: InPack Nutrients

Data da observação: 2026-09-29. Preparado por Howz.
Site principal auditado: store.inpacknutrients.com (Shopify). Também lidos: www.inpacknutrients.com (Wix), shop.inpacknutrients.com (segundo Shopify), regelpharmalab.com, Facebook, LinkedIn, Linktree.
Negócio: vitamin packs (pacotes diários de vitaminas) criados por Josh Regel, PharmD, farmacêutico de manipulação dono da Regel PharmaLab, Germantown, Tennessee (região de Memphis). Fundada em 2022. Público: EUA, em inglês.

## O que esta rodada não cobre

- Os três domínios da marca estão bloqueados pela política de rede do ambiente (proxy devolve 403 no CONNECT). Nenhum HTML foi lido diretamente. Todo conteúdo veio do índice do Exa (texto renderizado). Para liberar: adicionar `*.inpacknutrients.com` à política de rede do ambiente.
- Por isso NÃO foi possível verificar: robots.txt, sitemap.xml, canonical, JSON-LD, tags de conversão (GA4, Google Ads, Meta Pixel), velocidade, theme-color e CSS. Esses itens estão como "verificar" no checklist, com o comportamento padrão do Shopify anotado.
- Semrush: sem unidades de API (`no_api_units`). Firecrawl: sem créditos. Sem volume de busca nem dificuldade numérica. Tudo é estimativa qualitativa.
- Posições: buscas manuais em 2026-09-29 via WebSearch (índice tipo Bing, EUA). Não é Google. Use como presença aproximada, não como ranking.
- Instagram @inpacknutrients: perfil existe (confirmado por Socialinsider e LinkedIn), mas não abriu por nenhuma ferramenta. Seguidores, bio e legendas não foram lidos. Copy de Instagram avaliada pelos posts espelhados no Facebook e LinkedIn (mesma equipe, mesmas legendas).
- Perfil de Empresa no Google da InPack: não localizado como entidade própria. O que aparece é o da Regel PharmaLab (4,8 estrelas, "10+ reviews" via agregadores). Página do Facebook da InPack: 0 avaliações.
- Sem Search Console, sem GA4.

## Resumo executivo

Veredito: a InPack tem o melhor diferencial do nicho (farmacêutico de manipulação real, 9 times da NBA, NSF Certified for Sport) e o esconde atrás de três sites diferentes, textos de placeholder e produtos de teste indexados. A loja que vende (store.) é a pior das três em conteúdo. Uma pessoa que chega pelo Google encontra "Inpack Nutrients" como título, descrições com "(Include details on each of the ingredients)" e um "Sobre nós" copiado do tema do Shopify. A confiança quebra antes do checkout.

Os três problemas que fazem a loja perder leads hoje:

1. **Marca dividida em três domínios (www, store, shop) mais regelpharmalab.com vendendo o mesmo Immune Pack.** Autoridade e links se dividem por quatro. O www tem o melhor texto e o blog atualizado, mas não vende. O store vende, mas tem o pior texto. O shop está praticamente vazio ("collections/all" sem produtos) e ainda assim indexado com o título mais forte de todos ("Sports Supplement Packs for Athletes & Teams"). Custo: cada busca de marca vira uma loteria de qual site abre, e cada backlink conquistado fortalece só um quarto do todo.
2. **Placeholder e boilerplate em páginas que vendem.** "Pack Ingredients: Learn more about this pack. (Include details on each of the ingredients as an active link)" aparece em todos os produtos. "Vitmain C", "Vitmain D" na página do Immune Pack. "RIGTH", "PACKED F OR RESULTS", "optimal affect" no www. A página "About Us" do store diz "Several decades of successful operation and thousands of happy customers" para uma empresa de 2022. Custo: sinais de qualidade baixa para o Google (YMYL) e para a pessoa que ia comprar um produto de saúde de US$ 90 por mês.
3. **Produtos de teste e de afiliados indexados como catálogo público.** "Jessica Performance Pack", "Jessica Performance Pack 2", "Jessica Sleep Pack", "Daavon Men/Women Sports Performance" (US$ 150/mês), "Forever Fit Performance Nutrient Pack" estão em /collections/all com a MESMA descrição do Sports Pack. 14 produtos, dos quais 5 são canônicos. Custo: conteúdo duplicado, canibalização do Sports Performance Pack, e um comprador vendo o "pack da Jessica" sem entender o que é.

Maior surpresa da rodada: **o site da loja não diz que é feito por um farmacêutico de manipulação, não cita os 9 times da NBA e não menciona NSF Certified for Sport.** Tudo isso está no www (Wix), no Facebook (post de 25/09/2026 fala de NSF) e no LinkedIn. Na loja, onde a pessoa decide, o vendedor listado é "InPack Nutrients" e o tipo de produto é "Vitamins & Supplements". Nada mais.

Risco regulatório que vira risco de SEO: "help you control your diabetes", "lower A1C levels", "decreased likelihood of bacterial and viral diseases such as Influenza and COVID-19". São alegações de doença em suplemento (FDA/FTC nos EUA) e o Google trata saúde como YMYL: páginas com alegação de cura sem disclaimer perdem para páginas com linguagem de estrutura/função ("supports healthy glucose metabolism*"). Não há o asterisco nem o disclaimer padrão da FDA em nenhuma página lida.

## Oportunidades de palavras-chave (estimativa qualitativa, sem ferramenta)

### Prioridade alta

| Palavra-chave | Dificuldade (est.) | Presença hoje (2026-09-29, WebSearch) | Intenção | Onde trabalhar |
|---|---|---|---|---|
| sports performance vitamin pack | média | store aparece em ~4º (produto Sports Performance) | compra | Página do produto: título, descrição completa, NSF, "used by NBA teams", FAQ, schema Product |
| vitamin pack for athletes | média-alta | ausente | compra/pesquisa | Coleção "Athletes & Teams" no store, com texto de 400+ palavras |
| pharmacist designed vitamin packs | baixa | ausente | compra | Home do store + página Sobre: reposicionar toda a marca aqui, é o nicho onde ninguém grande compete |
| travel vitamin pack athletes / road trip supplement pack | baixa | ausente (RoadGame não aparece) | compra | Coleção RoadGame: renomear para incluir "travel", explicar 15 dias, quem usa |
| custom supplement packs for gyms / private label vitamin packs for trainers | baixa | ausente (página está no www com slug "trainers-and-gyms-1") | B2B lead | Migrar para o store como /pages/gyms-and-trainers com formulário |
| vitamin packs Memphis / supplements Germantown TN | baixa | ausente; só a Regel PharmaLab aparece | local | Perfil de Empresa no Google da InPack + página local + schema LocalBusiness |

### Prioridade média

| Palavra-chave | Dificuldade (est.) | Presença hoje | Intenção | Onde trabalhar |
|---|---|---|---|---|
| personalized vitamin packs | alta (Persona, Care/of, HUM, Shaklee dominam) | ausente no top 10 | pesquisa/compra | Não brigar de frente; usar como termo secundário na home com o ângulo "by a compounding pharmacist" |
| immune booster vitamin pack | média | ausente | compra | Produto Immune: corrigir typos, tirar alegação de COVID, adicionar ingredientes com dose |
| blood sugar support supplement pack / berberine magnesium pack | média | ausente | compra | Produto Glucose: reescrever para linguagem estrutura/função |
| NSF certified for sport vitamin pack | média | ausente | compra | Só faz sentido depois de confirmar quais SKUs têm a certificação; então página de coleção própria |
| magnesium for athletes recovery | média | blog do www tem post (jun/2025) | informacional | Manter no blog, linkar para o Sports Pack |

### Prioridade baixa

Weight loss vitamin pack (dominado por marcas grandes e com risco de alegação), "vitamins for ADHD" (o post de 2022 do store atrai tráfego errado e tem risco regulatório), "compounding pharmacy Memphis" (é da Regel, não da InPack).

## Problemas nas páginas

| Página | Problema | Gravidade | Correção |
|---|---|---|---|
| store home | Title tag é só "Inpack Nutrients". Sem meta description. Sem H1 com palavra-chave. Nenhuma menção a farmacêutico, NBA ou NSF | crítica | Title: "Pharmacist-Designed Vitamin Packs for Athletes & Teams \| InPack Nutrients". H1 e primeiro parágrafo com o diferencial |
| store home | Card do Weight Loss Pack mostra o placeholder "(Include details on each of the ingredients)" na própria home | crítica | Reescrever descrições curtas dos 4 packs principais |
| store /pages/about-us | Texto boilerplate do tema Shopify ("Several decades", "thousands of happy customers", "FIXED SHIPPING", "FREE RETURN 30 days") | crítica | Substituir pela história real: Josh e Summer Regel, UT 2000, Regel PharmaLab 2003, InPack 2022, 9 times da NBA, foto da farmácia |
| store /products/immune-booster-pack | "Vitmain C", "Vitmain D"; alegação sobre COVID-19 e Influenza; placeholder de ingredientes | alta | Corrigir typos, linguagem estrutura/função, lista de ingredientes com dose e forma, disclaimer FDA |
| store /products/glucose-control-vitamin-pack | "control your diabetes", "lower A1C"; URL diz "glucose-control", título diz "Glucose Support" (inconsistência) | alta | Reescrever alegações; manter URL (não quebrar) mas alinhar título; disclaimer |
| store /products/sports-performance-vitamin-pack | Descrição de 60 palavras para o produto principal; sem NSF, sem NBA, sem "who is this for", sem FAQ, sem reviews | alta | 400+ palavras, tabela de ingredientes com dose, FAQ, prova social, schema Product com AggregateRating quando houver reviews |
| store /collections/all | 14 produtos, 5 canônicos. "Jessica Performance Pack", "Jessica Performance Pack 2", "Jessica Sleep Pack", "Daavon Men/Women", "Forever Fit" duplicam a descrição do Sports Pack | alta | Tornar packs de afiliado não publicados (ou canal de venda só por link direto) e marcar noindex; se forem produtos reais, descrição única e explicação de para quem são |
| store /products/daavon-* | Texto de 1.500+ palavras copiado de bula de fornecedor (Active Life Nutrient, magnesium) sem contexto de marca; preço US$ 150/mês sem justificativa visível | média | Resumir, explicar o que diferencia do Sports Pack de US$ 90 ou despublicar |
| store /blogs/news | 2 posts, ambos de 18/09/2022. Post de ADD/ADHD com linguagem de tratamento e "micro-nutrient testing" | média | Migrar os 4 posts de 2025 do www para cá (ou o contrário, ver plano) e revisar o post de ADHD |
| store /pages/contact | Rótulo "STORE LOCATOR" com o endereço da farmácia; sem mapa, sem horário completo, sem formulário visível no texto lido; sem WhatsApp (normal nos EUA), mas sem SMS/click-to-call declarado | média | "Visit our pharmacy" com mapa, horário (M-F 9-5 CST, fechado 13h-13h30), link tel:, e formulário |
| store /collections/roadgame | Nome interno "RoadGame" sem explicar; sem a palavra "travel" no título | média | Title "RoadGame Travel Vitamin Packs for Athletes (15 days)"; texto explicando viagem, hotel, jogos fora |
| www home | Typos "RIGTH", "PACKED F OR RESULTS", "optimal affect", "Wholistic". Texto bom, mas em Wix, sem carrinho | média | Corrigir typos; decidir destino do www (ver plano) |
| www /trainers-and-gyms-1 e /copy-of-pharmacies | Slugs de rascunho do Wix indexados ("-1", "copy-of-") | média | Renomear para /gyms-and-trainers e /healthcare-professionals com 301 |
| shop.inpacknutrients.com | Site inteiro indexado com o melhor title da marca e sem produtos | alta | Redirecionar 301 para store (ou decidir que shop é o novo e migrar tudo de vez; não manter os dois) |
| regelpharmalab.com | Vende "Immune Booster Pack" por fora, sem link para a InPack | baixa | Link cruzado "Now sold as InPack Nutrients" e canonical ou redirecionamento do produto |

## Lacunas de conteúdo

| Prioridade | Esforço | Tema | Por que importa |
|---|---|---|---|
| alta | baixo | Página "Why a compounding pharmacist" (o diferencial) | Nenhum concorrente nacional (Persona, Care/of, HUM) tem isso. É a única história que a InPack ganha sozinha |
| alta | médio | Página "Teams & Athletes" com os 9 times da NBA (com autorização) e NSF | "trusted by 9 NBA teams" é a prova mais forte da marca e não tem página própria |
| alta | baixo | Tabela de ingredientes com dose, forma e marca do fornecedor em cada pack | Concorrentes (Designs for Sport, Klean) mostram Supplement Facts completo; a InPack mostra nomes soltos |
| alta | baixo | FAQ por produto (quando tomar, manhã/noite, pode com remédio, cancelamento da assinatura) | Assinatura de US$ 30 a 150 por mês sem FAQ de cancelamento perde venda e gera chargeback |
| média | médio | Blog unificado com 1 post/mês sobre nutrientes para atletas, viagens, recuperação | Blog do www tem 4 posts de 2025; do store, 2 de 2022. Um só, no domínio que vende |
| média | baixo | Página local "InPack Nutrients in Germantown, TN" com retirada na farmácia | Cliente de Memphis pode buscar na Regel; hoje não há como saber |
| média | médio | Depoimentos com nome e esporte (atletas, treinadores, pacientes) | Zero avaliações no Facebook, zero na loja. Só a Regel tem 4,8 |
| baixa | alto | Quiz "Which pack is right for me?" | Todos os concorrentes têm; conversão da home |

## Checklist técnico

| Item | Status | Detalhe |
|---|---|---|
| HTTPS | passa | Todas as URLs lidas são https; Shopify e Wix forçam TLS |
| robots.txt | verificar | Shopify gera por padrão (bloqueia /cart, /checkout, /account); não lido por bloqueio de rede |
| sitemap.xml | verificar | Shopify gera /sitemap.xml automaticamente; confirmar envio no Search Console |
| Indexação | atenção | 3 subdomínios indexados + regelpharmalab.com com produto igual; /cart do store apareceu no índice do Exa |
| Canonical | verificar | Shopify coloca self-canonical; problema real é entre domínios, não dentro do store |
| Dados estruturados | verificar | Shopify emite Product JSON-LD no tema padrão; não há como confirmar sem HTML. Não há LocalBusiness/Pharmacy em nenhum domínio (inferido) |
| Velocidade / Core Web Vitals | verificar | Não medido. Rodar PageSpeed Insights nas 3 páginas de produto principais |
| Mobile | verificar | Temas Shopify e Wix são responsivos; confirmar tap targets no menu |
| Nome, endereço, telefone (NAP) | atenção | Store: "1352 Cordova Cove Germantown, TN 38138". Facebook: "1352 Cordova Cove #201". NPI da Regel: endereço antigo em Cordova (1679 Bonnie Ln). Padronizar com "#201" em todo lugar e atualizar cadastros antigos |
| Perfil de Empresa no Google | falha | InPack não tem perfil próprio localizado; Facebook com 0 avaliações; Regel PharmaLab 4,8 (10+ avaliações) |
| Tags de conversão (GA4, Google Ads, Meta Pixel) | verificar | Não lido. Checar com Tag Assistant: ID AW- duplicado, GA4 em dobro, pixel duplicado são os erros comuns em Shopify + apps |
| WhatsApp | não se aplica | Mercado americano. Verificar link tel: e SMS |
| Firewall / bloqueio de bots | atenção | Domínio recusado pelo proxy do ambiente; pode ser política do ambiente e não do site. Confirmar que o Googlebot não é bloqueado (Search Console > Configurações > Estatísticas de rastreamento) |
| Domínio e www | falha | www (Wix), store (Shopify), shop (Shopify), linktr.ee como "homepage" no LinkedIn. Quatro portas de entrada |
| Alegações de saúde / disclaimer FDA | falha | Nenhuma página lida traz "These statements have not been evaluated by the FDA" |
| Blog | atenção | Dois blogs, nenhum com post depois de out/2025 |

## Concorrentes

Busca "sports performance vitamin pack" (WebSearch, 2026-09-29, EUA): Designs for Sport (Amazon e site próprio), Thorne, InPack (~4º), Designs for Health, Target, NeoLife, Six Star, Wilderness Athlete.
Busca "personalized vitamin packs": Shaklee Meology, BodyLogicMD, Persona, Vitable, Fortune, Perelel, VitaRx, VitaminLab, Forbes. InPack ausente.
Busca local "vitamin packs Germantown TN compounding pharmacy": Regel PharmaLab aparece (Healthgrades, Yelp, Facebook); InPack ausente.

| Concorrente | "sports performance vitamin pack" | "personalized vitamin packs" | Instagram | Avaliações | Blog | Marca própria | Diferencial |
|---|---|---|---|---|---|---|---|
| Designs for Sport (Power Pack, US$ 86 a 98) | 1º e 3º | ausente | não medido | 4,9 em revendedores (22 mil na Supplement First) | sim | sim | NSF Certified for Sport, Supplement Facts completo |
| Persona Nutrition (Nestlé) | ausente | 3º | não medido | 4,4 (10 mil+ Trustpilot) | sim | sim | Quiz, nutricionistas, checagem de interação com remédios |
| Klean Athlete (Klean Sport Pack, US$ 93) | presente em Exa | ausente | não medido | não medido | sim | sim | NSF, patrocínio de atletas |
| Regel PharmaLab (mesmo dono) | ausente | ausente | não tem | 4,8 (10+) | não | sim | É a prova local que a InPack não usa |
| InPack Nutrients (Sports Pack, US$ 90) | ~4º | ausente | existe, não medido | 0 na loja, 0 no Facebook | 2 blogs parados | sim | Farmacêutico de manipulação, 9 times da NBA, NSF (não dito na loja) |

Quem ganha em quê: Designs for Sport ganha em prova de produto (rótulo completo, NSF na cara, 22 mil avaliações via revendedores). Persona ganha em personalização e escala. A InPack já está na primeira página para o termo de produto sem ter feito nada, o que mostra que o nicho "vitamin pack for athletes" está aberto. Ela perde em prova social visível e em clareza de quem faz o produto.

## Plano de ação

### Fazer nesta semana

| Item | Tempo |
|---|---|
| Corrigir title e meta description da home do store e dos 4 produtos principais | 1 h |
| Apagar o placeholder "(Include details on each of the ingredients)" das 9 páginas e escrever a lista de ingredientes com dose | 3 h |
| Corrigir "Vitmain", "RIGTH", "PACKED F OR", "affect" | 20 min |
| Despublicar ou marcar noindex nos packs Jessica, Daavon e Forever Fit (ou dar descrição única) | 1 h |
| Reescrever a página About Us com a história real e foto de Josh na farmácia | 2 h |
| Redirecionar shop.inpacknutrients.com para store (301 no domínio) | 30 min |
| Adicionar disclaimer FDA e trocar alegações de doença por estrutura/função nos packs Glucose e Immune | 2 h |
| Criar Perfil de Empresa no Google "InPack Nutrients" com endereço #201, telefone, categoria "Vitamin & supplements store", fotos | 1 h |
| Pedir 10 avaliações a clientes e atletas atuais (Google e loja) | 1 h de envio |
| Rodar PageSpeed Insights e Tag Assistant nas 3 páginas de produto e registrar | 1 h |

### Investimentos do trimestre

- **Unificar domínios**: um único domínio que vende. Recomendação: mover o conteúdo do www (Wix) para páginas do Shopify e apontar www.inpacknutrients.com para o store, com 301 de cada URL do Wix (home, blog, trainers-and-gyms-1, copy-of-pharmacies, linkinbio). Encerrar o shop. Premissa: manter Shopify porque já tem catálogo, assinatura e checkout.
- **Página "Teams & Athletes"** com NSF, times (com autorização), depoimentos de treinadores.
- **Página "Why a compounding pharmacist"** com Josh e Summer, UT 2000, Regel 2003, o que muda na escolha de forma e dose.
- **Tabela de ingredientes** (Supplement Facts) em todos os packs, com foto do rótulo.
- **Blog único** no store, 1 post/mês, começando pelos 4 posts do www migrados.
- **Schema**: Product + Offer + AggregateRating nos packs, Organization com sameAs (Instagram, Facebook, LinkedIn, YouTube), LocalBusiness/Pharmacy na página de contato com geo e horário.
- **Programa de afiliados B2B** com landing própria e formulário (hoje o CTA é "schedule a call" sem link visível no texto lido).
