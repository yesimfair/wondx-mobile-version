---
name: "wondx-design-system"
description: "Decisões de kit do projeto Redesign — grid base 4, accent fixo no escuro, e os Kinds Accent e Tint Danger do Button"
---

- Botões não têm texto de 13px — é 16 ou 14 em Geist
- Propôs manter o botão de accent sempre #3D38E9, sem mudar no modo escuro; só outros elementos, como o selo de verificado, mudam no dark (restringe ao preenchimento do botão a regra antiga do accent 600→300 no dark)

## Grid e tamanhos — correção que ele teve de fazer (21/set/2026)
- Pediu que TODO frame siga o grid do kit: base 4 em espaçamento, e também em avatar, botão, chip e frame. Eu vinha usando 2, 6, 9, 10, 11, 14 — ele corrigiu sem eu perceber
- A direção das correções dele: sempre para o degrau de 4 MAIS JUSTO (6→4, 9→8, 14→12), nunca para o mais folgado. Raios 12 controle · 16 card · 24 painel · pill; ícones 16/24/32; avatares 24/32/36
- Decidiu na varredura do Final Screens (26/set/2026): espaçamento de 10 vira 12, e de 2 vira 0
- Padding de container (ex.: a caixa das tags) é 8 ou 16, que é o padrão — nada de 4 e 8 misturados no mesmo container (26/set/2026)
- Campo de descrição também mostra o total de caracteres, como o título (26/set/2026)
- Bookmark nos cards de post é glifo de 16, centralizado, não 24
- Coração preenchido é SEMPRE status/danger, e a contagem ao lado dele também; contorno fica em text/secondary

## Accent no escuro — aplicado (21/set/2026)
- Pediu para registrar: action/accent virou #3D38E9 FIXO nos dois modos. O valor antigo do Dark (#6B66F0) dava 4,39:1 com rótulo branco e reprovava AA; fixo dá 7,14:1. É seguro porque botão é identificado pelo rótulo, não pela borda (WCAG 1.4.11)
- Pediu para registrar: o selo de verificado NÃO segue essa regra — é gráfico de estado e precisa de 3:1 contra a página; #3D38E9 sobre #141414 dá só 2,58:1, então o selo usa text/accent, que clareia no Dark. Com o selo em #A5A3F8, o check branco dentro cai para 2,28:1 e precisa virar ink no escuro

## Button — dois Kinds novos (21/set/2026)
- Pediu e aprovou dois Kinds novos no componente Button: Accent e Tint Danger. O componente passou a ter 64 variantes (8 Kinds × 4 estados × 2 tamanhos)
- Pediu para registrar a construção do Accent: clonado do Danger (mesma lógica de preenchimento que não inverte); usa action/accent, text/on-accent, overlay/on-accent e overlay/on-accent-pressed — os três últimos foram criados seguindo o padrão do on-danger; rótulo 7,14:1
- Pediu para registrar a construção do Tint Danger: clonado do Sunken; usa tint/danger e text/danger, hover com overlay/on-surface; rótulo 5,54:1 no claro e 6,36:1 no escuro
- Disabled dos dois é NEUTRO (surface/sunken + text/disabled), igual aos outros Kinds — desabilitado é inativo, não perigo
- A propriedade Label do Button agora está LIGADA ao texto nas 64 variantes. Antes existia mas não fazia nada: trocar o Label no painel não mudava o botão. Todos os estados passaram a ter estilo de texto (só o Default tinha)
- Proposta de uso do Tint Danger que pediu para registrar, AINDA NÃO confirmada por ele: reversível (Remove, Disconnect, Unsubscribe) → Secondary; irreversível que ABRE a confirmação (Delete post, Delete account) → Tint Danger; o que CONFIRMA dentro do modal → Danger. Encaixa na regra antiga de que a cor segue a consequência
- Aprovou (22/set/2026) ampliar a exceção escrita do text/danger (antes, vermelho em texto só nos chips de prazo estourado da fila de moderação): vale também para o rótulo do Tint Danger, a tag −rep do Guestbook, o item Delete dos menus (que troca status/danger por text/danger) e a linha de erro do arquivo removido no editor de perfil

## Mapa de atividade (22/set/2026)
- Aprovou a rampa sólida por tema no lugar do accent com opacidade: variáveis activity/level-1 a level-5, claro #CDD0FC · #A5ADF9 · #7C89F7 · #5965F5 · #3D38E9, escuro #232270 · #3D39A6 · #5A53DB · #7E7BF6 · #A5A3F8; o nível 0 continua surface/sunken. Motivo: com opacidade, no escuro o nível 1 ficava mais escuro que o dia vazio e o topo não passava de 3:1

## Pastilhas de tag (21/set/2026)
- DECIDIDO depois de comparar no protótipo: tags são em CONTORNO border/strong, sem fundo (o estilo "Outline · border/strong", com selecionada em ink) — NÃO tingidas. Vale para toda tag do produto (fileira de tags, relacionadas, populares, busca). O segmentado de tipo continua na mesma fileira das tags
- Motivo dele: tag tingida tinha o mesmo surface/sunken da trilha do segmentado ("All · Desktop · Phone") e parecia opção do mesmo controle; tirar o segmentado da fileira não resolvia. Refina, para tags, a regra antiga de pastilha de filtro tingida sem borda

## Sidebar — estado ativo e ícones (21/set/2026)
- Item ativo da sidebar usa o ícone Phosphor preenchido (Fill), e o fundo do item também muda quando ativo — no Library, bookmark-simple preenchido
- PADRÃO: o fundo do item ativo da sidebar é totalmente arredondado (raio 999), não 12px — vale para todos os itens
- Ícone da Home na sidebar passa a ser o Phosphor "house" (antes "house-line"), em todas as páginas
- Ícone do Following na sidebar é o Phosphor "users", com "users-fill" quando ativo

## Correções que ele pediu para valer daqui em diante (21/set/2026)
- Título de modal NÃO usa display: é o estilo title/20, Geist 20px — regra já decidida antes, que ele relembrou
- Só existe um title/20, em 20/24 (23/set/2026): o estilo duplicado de 20/28 foi apagado e todos os títulos que o usavam passaram para 20/24
- Botão de voltar só com ícone é um círculo com contorno, igual aos botões de share e save, para ser identificado como botão (ex.: página da coleção)
- REGRA que pediu para registrar: seleção SOBRE IMAGEM usa accent — anel accent de 2px com uma folga da cor da superfície por dentro + selo accent de 24px com check branco no canto (primeiro caso: seletor de capa do Edit collection). Seleção sobre SUPERFÍCIE (tags, chips, segmentado) continua ink. O check é obrigatório, não enfeite: pela WCAG 1.4.1, seleção não pode ser indicada só por cor. Motivo do accent: a arte da Wondx é quase toda escura e o ink some sobre ela
- Os ícones da Wondx são SEMPRE do Phosphor (22/set/2026). No arquivo do redesign o padrão é Phosphor Bold, com os frames nomeados "Phosphor / X Bold"; o Fill fica para casos de estado, como o item ativo da sidebar. Achado da conferência do site atual: hoje a página de perfil mistura Phosphor Bold (seletor do Contributions e troféu do rank) com um conjunto traçado de viewBox 24 (local, e-mail, chama do streak) e um glifo de marca para o Discord — no redesign tudo fica em Phosphor Bold. Ícones confirmados do Contributions: pulse (Activity), link-simple (Links), user (About), star (Featured work), chat-circle-text (Guestbook), trophy (rank), caret-down (ordenar). Selo de verificado e badge Pro não são ícone: são as badges próprias — no perfil, a badge Pro usa a arte canônica wondx-subscriber-pro em 20px, e o verificado fica no SealCheck Fill em text/accent (22/set/2026)
- Aprovou testar (25/set/2026) o token overlay/backdrop — #141414 a 92%, igual nos dois modos — como fundo da tela cheia de imagem na página do post, "pra ver como fica"
- Aprovou (26/set/2026) o token overlay/scrim — #000 a 40%, igual nos dois modos — para o fundo dos modais de conteúdo
- Button sem opção de ícone, por ora (26/set/2026): foi da opção B — o componente continua só com texto e os botões com ícone (Upload, Download, voltar com nome) seguem como peças clonadas das telas, porque ícone trocável no componente exigiria componentes de ícone, que a regra dele proíbe. Substitui a aprovação anterior de pôr ícone à esquerda no Button
- Escolheu (21/out/2026) seguir com peças clonadas para os botões com ícone do help center, em vez de um slot no Button do kit; disse que o slot no Button é uma possibilidade em projetos futuros
- Plano deles para o futuro (26/set/2026): refazer o kit, com uma documentação mais precisa que a atual
- Logos de marca (X, Reddit, WhatsApp, Telegram, Pinterest, Facebook) usam a marca oficial, não a versão redesenhada do Phosphor (26/set/2026) — exceção à regra de ícones sempre do Phosphor, só para logos de marca
- Decidiu (27/set/2026) que links informados pela própria pessoa não levam logo do site — "não iremos cobrir todos esses": saiu o logo do ArtStation do campo de link do formulário de Official Creator, e aprovou ícone genérico no botão de loja dos posts ("Buy on {site}") no lugar do logo do Gumroad
- Prefere campos de formulário só com contorno, sem fundo, como no Settings atual do site, aos campos preenchidos que o kit define, mas decidiu (2/out/2026) manter os campos preenchidos por agora: tokens e estilo do kit não mudam
- Decidiu (2/out/2026) que logos de empresas (Discord, Google etc.) ficam nas cores da própria marca, não em ink/preto e branco — inclusive nas telas de login e sign up, que tinham virado ink sem ele perceber durante a conversa do passkey (escopo fechado em 3/out/2026: logos coloridos e oficiais só no login e nas contas conectadas do Settings, onde a Steam também usa o logo oficial da empresa e não o do Phosphor; nos links do perfil e do Showcases fica o logo cinza num quadradinho e a primeira letra do endereço para site desconhecido — ver [[wondx-settings]])
- Decidiu (3/out/2026) manter os botões de ligar/desligar (switches) em ink em todo o site; não trocar para accent
- Aprovou (8/out/2026) os números das abas (contagem ao lado do nome) e os rótulos do mapa de contribuições em text/secondary, não em text/disabled, que fica abaixo de 4,5:1 (perfil 14.x, busca 10.2 e Library 12.x)
- Aprovou (9/out/2026) action/danger em #BF0014 também no modo escuro, igual ao claro
