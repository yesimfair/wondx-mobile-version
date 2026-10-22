---
name: "redesign-busca"
description: "Bloco 3 do redesign Wondx — página de categoria, tag, busca e sem resultado num molde só; ordem padrão, autocorreção, URLs"
---

## Molde (21/set/2026)
- Concordou: categoria, tag, busca e sem resultado são UM molde (fileira de categorias + cabeçalho + masonry), com três cabeçalhos diferentes e um estado vazio
- Hoje são só 5 categorias, então escrever a descrição de cada uma é trabalho pequeno — fazer antes de crescer
- Pediu para registrar, para o documento do [[nedddz]]: protótipo HTML em https://claude.ai/artifact/ExmE9DhexHVyHKAKfqx3Tm

## Categoria
- Indexada. Mesma fileira de categorias da home com a categoria ativa, depois título + descrição (o que ele já tinha desenhado), subtags e o menu de ordenação. Free e Paid SAEM na Fase 1
- Aceitou a ordem padrão por RELEVÂNCIA, não Popular nem Newest. Pediu para registrar a regra: pontuação = curtidas + salvamentos + downloads com decaimento por idade; diversidade por criador (ninguém com mais de ~1 em 10 dos primeiros 20) e por subtag; algumas vagas para posts recentes com pouca exposição. Menu: Relevant (padrão) · Newest · Popular; preço só na Fase 2. Mesma regra na página de tag
- Base da decisão que pediu para registrar: Baymard manda ordenar por relevância baseada em diversidade, com popularidade como fator mas nunca o único, e os principais tipos representados nos primeiros ~20 itens; o MusicLab (Salganik, Dodds, Watts, Science 2006, 14.341 participantes) mostrou que ranquear por total de downloads aumentou desigualdade e imprevisibilidade do sucesso em relação à ordem aleatória

## Tag
- noindex, follow, a não ser que a tag tenha demanda real de busca. Cabeçalho leve "#tag · N posts". Related NÃO pode listar a própria tag (bug da 3.4)

## Busca — decisões para o documento do [[nedddz]]
- noindex sempre. Aba "All" mistura Pessoas, Tags e Posts (busca federada); abas de linha All · Posts · People · Tags, com contagem UMA vez só (tirar a linha "5 posts · 1 people · 2 tags" que duplica)
- Ordem das seções pela INTENÇÃO, com uma trava: POSTS SEMPRE POR ÚLTIMO, porque é masonry infinita e nada pode vir depois dela (mesma regra do "More like this" na página do post). A intenção só ordena as seções compactas acima: consulta bate exato com um handle → Pessoas, depois Tags; senão → Tags, depois Pessoas. CORRIGE a versão anterior desta nota, que dizia "senão Posts primeiro" — isso só funcionava no protótipo porque a grade lá era finita
- Título é só a consulta entre aspas. "Showing results for" fica RESERVADO para autocorreção
- AUTOCORREÇÃO: só quando a consulta original dá ZERO resultados e a corrigida dá muitos. Aí troca a página e mostra "Showing results for X. Search instead for Y". Fora disso, "Did you mean" sem trocar a página. A página de sem resultado só aparece quando não há correção confiável
- Card de pessoa na busca: três miniaturas do trabalho + Follow, SEM contagem de seguidores (número pequeno trabalha contra o criador)
- No "All", só tags com 3 ou mais posts; a aba Tags mostra todas
- Plural certo: "1 person", "1 post" — o site ao vivo mostra "1 people" e "1 posts"
- O seletor da busca ao vivo é segmented com o selecionado em ink, o que contradiz o kit duas vezes: troca de seção é aba de linha, e segmented selecionado usa surface/selected

## Sem resultado
- "Popular tags" com tags de verdade (a versão antiga dizia tags e mostrava categorias). Sem ícone de imagem quebrada. A grade "You may like" embaixo fica, porque o vazio é a consulta e não a página

## URLs — recomendação, ainda a decidir com o [[nedddz]]
- Pediu para registrar: Google recomenda hífen entre palavras e dá palavras coladas como exemplo de não recomendado. Proposta: /steam-profiles, /digital-art, /pfps-banners, com 301 das atuais que já estão no ar. /allcategories provavelmente duplica a home: canonical para / ou não existir

## Navegação e filtros (21/set/2026)
- Aprovou aplicar no protótipo: categorias viram ABAS DE LINHA (nível 1, navegação entre páginas). Motivo dele: duas fileiras de pastilhas iguais deixavam a navegação confusa
- Seguiu com, e pediu para atualizar as páginas no Figma assim: o nível 2 da categoria é o TIPO, como controle segmentado. Steam Profiles: All · Full profiles · Artwork · Showcase guides; PFPs + Banners: All · Matching sets · PFPs · Banners; Wallpapers: All · Desktop · Phone. Digital Art e Photography não têm tipo. As tags de tema (Dark, Anime…) SAEM da fileira e vão para dentro do Filters. Substitui a ideia anterior de subtags como pastilhas no nível 2
- Collections vai para a fileira de cima, como aba no fim, depois de um divisor
- Aprovou: "Filters" abre todos os filtros e tudo aplica ao vivo, sem botão de aplicar
- Aprovou TIRAR o atalho promovido no lançamento (corrige a aprovação anterior de dar ao filtro mais importante um botão próprio): Motion, Minimum resolution e Orientation vivem só dentro do Filters, com o atributo da categoria no topo do painel; um filtro só ganha atalho depois que analytics mostrar que é o mais usado naquela categoria
- Pediu a fileira de tags também na HOME — aplicada e aprovada nas três versões da home no Figma (7.1, 7.2, 7.3). Na home o Filters saiu da ponta da fileira de abas e foi para a ponta da fileira de tags (substitui a decisão anterior de manter o Filters na ponta das abas)
- DECIDIDO: tags em contorno border/strong, sem fundo, e o segmentado de tipo continua na mesma fileira das tags — detalhes em [[wondx-design-system]]
- Revisto (29/set/2026), depois de um comentário do [[nedddz]] pedindo o toggle de IA no painel de filtros das Public Collections: o painel Filters da home, das páginas de categoria/tag/busca e das Public Collections ganha a seção "Content", com "Show AI-generated posts" e "Posts with a content warning" (Warn · Hide). É a MESMA preferência de conta, não filtro da página: mudar num painel muda no site inteiro e o Clear all não mexe; acima da grade ficam pastilhas tracejadas com "Change", que abre o painel. Aprovou Warn como padrão e Suggestive sempre escondido para contas com menos de 18 — o Suggestive sempre escondido para menores de 18 foi confirmado por ele em 10/out/2026; o Warn como padrão ainda pede confirmação do [[nedddz]] (antes, 21/set: IA fora do painel, só a pastilha acima da grade)
- Motion (animado ou estático) não existia nos filtros e vale adicionar, a começar por Steam Profiles
- Aprovou (29/set/2026), depois de um comentário do [[nedddz]] pedindo Workshop no nível 2: na Steam Profiles, "Artwork" vira "Showcases" (All · Full profiles · Showcases · Showcase guides), e Featured, Artwork e Workshop viram o filtro "Showcase" no topo do painel da Steam Profiles, antes de Motion — Workshop é formato de showcase, não tipo, e aparece também dentro de perfis completos. Substitui o "Artwork" da linha de 21/set acima. Aplicado no protótipo e no Figma (10.4)
- Decidiu em seguida (29/set/2026) tirar também "Showcase guides" do nível 2: o guia é formato de showcase, como os outros. A Steam Profiles fica All · Full profiles · Showcases, e o filtro "Showcase" passa a Any · Featured · Artwork · Workshop · Guide. O upload continua com os três tipos Steam (Steam Profile, Steam Showcase, Steam Guide). Aplicado direto no Figma (10.4) e no protótipo
- Mandou ao [[nedddz]] (29/set/2026) um documento separado com a matemática do Relevant de coleções e de posts: https://claude.ai/code/artifact/f5552b57-57a1-47ae-8511-4fd269c6fd6b
- Steam Profiles hoje se divide em All, Full profiles, Artwork e Showcase guides; PFPs + Banners aceita PFP e banner em posts separados ou juntos no mesmo post (matching sets)

## Tags da comunidade na fileira do nível 2 (21/set/2026)
- DECIDIDO: as tags VOLTAM para a fileira do nível 2, entre o segmentado de tipo e as ferramentas, no estilo do VGen (fileira horizontal que rola, com seta). Corrige a nota acima que tirava as tags da fileira. Motivo dele: as tags não serão uma lista fixa, serão inúmeras, criadas pela comunidade — o grupo fixo dentro do Filters não escala
- Pediu para registrar o achado que sustenta a decisão: (1) tags colaborativas seguem LEI DE POTÊNCIA — poucas tags usadas com enorme frequência, muitíssimas usadas raramente — e depois das primeiras ~100 marcações de um item cada tag vira proporção quase fixa do total (Golder e Huberman, J. Inf. Sci. 2006, dados do del.icio.us); (2) exibir só as mais populares tem RECALL BAIXÍSSIMO: como a marcação é cauda longa, a maioria dos itens fica inacessível pelas tags visíveis; (3) SUGESTÃO muda a distribuição: a lei de potência se forma sem sugestão na interface e deixa de valer com sugestão — as pessoas imitam o sugerido; (4) NN/g: conteúdo escondido por rolagem horizontal fica em desvantagem, nem pistas salientes dão sinal forte, e seta que só aparece no hover pode nunca ser descoberta
- Regras que saem disso, para o [[nedddz]]: a fileira ORDENA POR POPULARIDADE dentro da categoria (nunca alfabética, nunca por recência) — assim o que cabe na tela é a cabeça da distribuição e o que fica escondido é a cauda, e a fraqueza da rolagem horizontal coincide com o formato dos dados; a cauda longa tem outro caminho: aba Tags da busca, páginas /tag/…, e um CAMPO DE BUSCA de tags dentro do Filters no lugar da lista fixa; a seta `›` fica SEMPRE visível, com degradê na borda
- Também registrado: sugerir tags existentes no upload é a alavanca mais forte contra fragmentação ("dark", "darkness", "dark-aesthetic"); UMA TAG POR VEZ por enquanto, porque com catálogo pequeno combinar duas zera resultado — combinação fica na busca e pode ser liberada quando o catálogo crescer; a moderação precisa conseguir ESCONDER uma tag da fileira sem apagar ela dos posts
