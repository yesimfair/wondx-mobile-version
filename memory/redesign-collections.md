---
name: "redesign-collections"
description: "Coleções no redesign Wondx — vitrine Public Collections (entrada, filtros, Relevant), capa no estilo Pinterest, prateleira no feed e página da coleção"
---

## Public Collections (21/set/2026)
- Coleções são criadas pelos usuários, que escolhem deixar cada uma pública ou privada; a aba Collections mostra só as públicas, e por isso o título "Public Collections" fica
- Decidiu que a página de Collections NÃO tem fileira de tags; gostou de "Contains" (categorias) dentro do Filters
- Regra de entrada da vitrine pública: a coleção aparece a partir de 1 post visível (antes: mínimo de 3, trocado por ele no mesmo dia); com zero visível não aparece
- Pediu para registrar: com o limiar em 1, quem separa coleção boa de pasta pessoal é a ORDENAÇÃO — o tamanho entra na fórmula do Relevant e faz coleção pequena aparecer mais abaixo. O rodapé da página volta a dizer "That's every public collection on Wondx so far. Yours shows up here as soon as it's public."; com filtro aplicado, diz que são todas as que batem com os filtros
- Pediu: contador de itens da capa é o ÍCONE DE PILHA + número (como no site ao vivo), também na aba Subscribed collections do Following (9.3), no lugar de "N items"; o chip fica a 12px do topo e 12px da direita da capa
- Coleção com nada visível não aparece na vitrine, mas continua no perfil do curador e na Library/Following de quem assina (a regra de 21/set de capa com imagem inteira para coleção de 1 post foi substituída pela capa no estilo Pinterest, abaixo)

## Capa no estilo Pinterest e coleções no feed da home (1/out/2026)
- Pediu a capa de coleção "estilo Pinterest" e aprovou: imagem maior à esquerda como capa, duas menores empilhadas à direita, espaço sem post em cinza, formato 3:2, em todos os cards de coleção
- Aprovou que coleções entrem no feed da home numa prateleira "Collections for you" com "See all", em vez de cards soltos na masonry, e pediu que o porquê (o caso do Pinterest) acompanhe essas decisões
- Deixou para depois do bloco de Help/FAQ (1/out/2026) a tela de escolher a capa da coleção; aprovou (3/out/2026) o desenho: no Edit collection, o campo Cover mostra a prévia da capa e "Change cover", que abre o seletor no mesmo modal (prévia ao vivo, Automatic e os posts da coleção, Cancel e Done), e pediu para levar ao Figma (13.4)

## Relevant de coleções — a matemática (21/set/2026)
- Pediu para registrar, para o [[nedddz]]: Relevant = Interesse × Tamanho × Frescor
- Interesse = (inscritos + 1) ÷ (aberturas + 10) — taxa de quem abre e se inscreve, com suavização de Laplace (palpite inicial de 10%). Coleção nova começa em 10% em vez de 0; 1 de 1 vira 18% em vez de 100%; 30 de 100 fica em 28%. Escolhida em vez do limite inferior de Wilson (Evan Miller) porque o Wilson é enviesado para baixo e dá zero para quem ainda não foi aberto, enterrando toda coleção nova. Taxa em vez de número bruto de inscritos para não repetir a armadilha do MusicLab (a coleção antiga e grande trava o topo)
- Tamanho = mín(1, log₂(1 + posts visíveis) ÷ log₂ 13): 1 post 27%, 3 posts 54%, 6 posts 76%, 12 ou mais 100% — satura em 12 para coleção gigante não ganhar só por tamanho
- Frescor = máx(0,25; 0,5^(dias desde o último post adicionado ÷ 14)): cai pela metade a cada duas semanas sem post novo, com piso de 25% para coleção boa e já terminada não sumir
- Dois ajustes depois da conta: nenhum curador duas vezes na mesma fileira de quatro; e, se nenhuma coleção dos últimos 7 dias entrou nas 8 primeiras, a melhor nova ganha a posição 8 (vaga de exploração)
- Exemplo registrado: Dark PFPs, com o maior número de inscritos (120), fica em 5º porque só 13% de quem abre se inscreve e está 12 dias sem post novo; Retro OS, com 19 inscritos, fica em 1º com 29% de conversão e atualizada ontem
- Os números (10% de palpite inicial, saturação em 12 posts, meia-vida de 14 dias, piso de 25%) são de PARTIDA, não calibrados — a estrutura da fórmula é a decisão; os números o [[nedddz]] ajusta com dado real depois do lançamento
- Ordenações da página: Relevant (padrão) · Recently updated (não "Newest": para quem assina, importa coleção que recebe post novo) · Popular (mais inscritos). No Filters: Contains (as cinco categorias, múltipla escolha) e Creators
- No site atual, o bookmark do card abre um seletor de coleção, como no Pinterest: salvar um post é escolher em qual coleção ele entra
- Decidiu que os botões Subscribed e Unsubscribe (hover) das coleções são OUTLINED; rejeitou o Sunken para eles ("não é algo que eu adicionaria")

## Página da coleção (21/set/2026)
- Rejeitou mostrar a contagem de inscritos só a partir de 10; seguiu com ela sempre visível, zero incluído, como o Pinterest mostra os seguidores de um quadro
- A confirmação de apagar uma coleção cita os inscritos quando existem
- Aprovou que a barra lateral acenda conforme a origem: na página da própria coleção, Library; chegando pelo Following, Following
- Aprovou (25/set/2026) que o voltar da página da coleção (13.1) mostre o nome da página de onde ela foi aberta (Public Collections, Library ou o perfil), como o "‹ Explore" do Trending, em vez do botão redondo só com a seta
- Aprovou (1/out/2026) a regra da coleção pública com inscritos que vira privada: ela some para quem assinava e as assinaturas acabam; antes de confirmar, o curador vê quantas pessoas vão perder acesso, como na confirmação de apagar, que já cita os inscritos
