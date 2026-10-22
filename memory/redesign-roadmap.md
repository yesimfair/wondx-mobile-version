---
name: "redesign-roadmap"
description: "O que falta refazer no redesign Wondx — verificação de artista, dashboard de criadores, aba do plano Pro, Explore/Trending — e decisões de escopo"
---

- Confirmou (24/set/2026) o inventário do que falta no redesign: fim do upload, página do post (galeria de várias imagens, linha "With", download, edição do post), notificações, leaderboard e pontos, Pro e Gift, Help, Settings por último, e os modais (editar e apagar post, compartilhar, Gift Pro, aceitar colaboração; o de opções de download saiu do inventário em 26/set/2026)
- Além disso faltam outras páginas da Everything do Figma, entre elas o formulário de artista (verificação), o dashboard de criadores e a aba do plano de quem é Pro
- Dashboard de criadores: mostra as métricas mais importantes do post ou da conta; precisa ser intuitivo para o usuário entender; pediu o planejamento do que entra e como
- Explore e Trending ainda não tinham sido redesenhados e precisam ser refeitos (no site mudou como devem ser); aprovou juntar os dois num Explore único, com o Trending virando o "See all"
- O fluxo de "Esqueci a senha" foi removido do produto

## Explore único — regras aprovadas (24/set/2026), para o documento do [[nedddz]]
- Aprovou o Explore único do protótipo: "Trending this week", "Rising", "Editor's Picks", Coleções populares e Tags (a seção de Categorias em mosaico saiu em 25/set e voltou no mesmo dia como cards, quando a barra de categorias saiu do Explore); saem o raw wall, "Most active creators" (fica no Leaderboard) e "Most active tags"; a barra lateral fica com um ícone só
- Trending: download pesa 3, save 2 e curtida 1, atualizado de hora em hora; 7 dias como padrão; o "24 hours" só aparece quando 12 posts passam do mínimo num dia; com menos de 8 posts na semana, a lista mostra os últimos 30 dias e avisa; a fileira do Explore mostra no máximo um post por criador; os cards não mostram contagem
- Rising: posts dos últimos 14 dias com pelo menos 20 visualizações, ordenados pela proporção de downloads por visualização (não pelo total); a seção some quando menos de 4 se qualificam

## Explore — correções aprovadas (25/set/2026)
- Manteve o Explore único; o Trending volta a ter ícone próprio na barra lateral quando a lista de 24 horas passar a ter 12 posts ou mais com frequência
- Consistência com o kit: Category tabs com os nomes do kit ("PFPs + Banners", "Steam Profiles"); período com a peça segmentada do kit (8681:105); fileiras de Trending, Rising e Editor's Picks em layout justificado (o do Flickr), sem cortar formatos, até duas linhas
- Revisto em 25/set/2026: o Explore fica SEM barra de categorias (antes: Category tabs também no Explore). No topo ela parecia a barra da Home e, para quem saía da Home, parecia quebrada; decidiu pelos cards de categoria. Quer o card com uma imagem grande e dois quadrados pequenos, não três colunas iguais: no desenho anterior levou mais de 2 segundos para achar e identificar as categorias. Aprovou (25/set/2026) esses cards com o nome embaixo e a seção de categorias como a primeira logo abaixo do título
- Seguiu (25/set/2026) com o Trending no layout da Library, com as categorias como abas embaixo do título, e com o voltar mostrando o nome "Explore" (antes: botão redondo só com o CaretLeft, como no 13.1)
- Subtítulo abaixo do H1, também meta description: "Wallpapers, PFPs, banners, digital art, photography and Steam profiles: what's trending, our team's picks, and new work on the rise." (o "this week" saiu em 27/set/2026, porque no lançamento a lista pode mostrar 30 dias); title "Explore wallpapers, PFPs, banners and Steam profiles · Wondx". Aprovou (27/set/2026) o title e a description do /trending: "Trending wallpapers, PFPs, banners and Steam profiles · Wondx" e "The most downloaded, saved and liked posts on Wondx, updated every hour."
- SEO do Explore: links como <a href> renderizados no servidor, filtros do /trending depois de "#", alt text em todas as imagens, primeira fileira sem lazy loading

## Ordem de trabalho (25/set/2026)
- Upload (Bloco 15) fechado e em dia com o protótipo https://claude.ai/artifact/ASKeqR3bebUkTk7MzYq1FB; Explore é o Bloco 16 (16.1, 16.2, 16.3), protótipo https://claude.ai/artifact/3usiLHy8FpySLhhgwg4Ybq
- Depois do Explore, nesta ordem: 1 página do post (galeria, "With", download, edição); 2 notificações; 3 autenticação e páginas de sistema; 4 verificação de artista; 5 planos, Pro e Gift; 6 leaderboard, pontos e badges; 7 help, FAQ, sorteio e landing; 8 settings. O protótipo do dashboard de criadores entra junto, com o plano de eventos para o [[nedddz]] vindo antes

## Depois do redesign (27/set/2026)
- Quando terminar o redesign, quer uma fase para os pequenos ajustes de UX que mudam como o usuário navega (ex.: confirmar o código de e-mail sozinho no sexto dígito) e para UX de conversão das assinaturas (ex.: avisar que a pessoa ganhou um banner animado ou tema com o Pro e levá-la a experimentar)
- Depois disso, vão refazer todo o redesign em versão de celular
- Caminho aprovado para o celular, em 4 etapas (27/set/2026): 1 testar os protótipos HTML em larguras de celular (390 iPhone, 360 Android) e listar o que quebra, página por página; 2 decidir os padrões de celular uma vez, como um mini-kit (navegação embaixo no lugar da barra lateral, menus e modais como folhas que sobem da base, busca em tela cheia); 3 desenhar primeiro as páginas mais visitadas (feed, post, busca, perfil), numa coluna de celular por bloco, só com as telas principais — estados iguais ao desktop não são redesenhados; 4 acrescentar à skill wondx uma seção de celular com esses padrões
- Lembrou (29/set/2026) que o redesign ainda inclui os modais de trocar de conta (switch account), que não estavam no inventário

## Lista de prioridades dele (1/out/2026)
- "Fair's priority list" (mensagem fixada): contador de contribuições na topbar; pop-up de perfil no nome do criador no feed da home (corrigido por ele em 1/out/2026: abre ao passar o mouse, como o Instagram faz, não ao clicar); tarefas de onboarding para novos usuários com dicas; capa de coleção, que pode aparecer também no feed da home; página de boas-vindas da assinatura Pro/Lite; página de Updates; pôsteres para os fóruns do Discord incentivando upload (um por categoria); novo kit de PFP/banner da Wondx para o lançamento; telas de celular. Também na lista: melhoria das páginas 404, tela explicando a verificação e um possível redesenho do top 3 do leaderboard; telas do menu de moderação marcadas como feitas
- Decidiu (1/out/2026) deixar o documento do Bloco 21 para o [[nedddz]] para o final, porque ainda precisa entender o que fazer nele
- Decidiu (2/out/2026) que as telas do painel de moderação/admin (inclusive as de Announcements e Suggestions do Bloco 23) ficam na página "Moderation System" do Figma, para revisar depois; por enquanto o trabalho é só nas páginas do produto em si (Final Screens)
- Esclareceu (2/out/2026) que a "landing" da lista do que falta era a teaser page, que já foi feita — sai da lista; seguem com o Settings
- Decidiu (8/out/2026) deixar a página de sorteio (giveaways) completamente parada por agora e seguir para o próximo item da lista
- Decidiu (8/out/2026) pular por agora os pôsteres dos fóruns do Discord e deixar de lado também o kit novo de PFP/banner do lançamento: o foco passa a ser as páginas do site em si e o que falta desenhar
- Pediu (14/out/2026) para pôr na lista de afazeres o redesign da seção de drafts (rascunhos) no perfil

## Creator Dashboard (3/out/2026)
- O nome continua "Creator Dashboard" (não só "Dashboard"); período com "All time" (não "Lifetime"); prefere o layout novo do protótipo ao do dashboard atual do site
- Aprovou trazer do dashboard atual do site as funções que o Claude recomendou (impressões e taxas, engajamento com comentários por 100 views, visitas ao perfil, tags, store clicks para Official Creators e assinantes Pro (antes só Official Creators; o Pro entrou em 9/out/2026), o "?" de como os números funcionam) e deixar de fora as que não foram recomendadas (Best day, Daily average, New posts, Daily/Total, card de melhor post)
- Decidiu (3/out/2026): a página continua em ink e o índigo fica só nos gráficos; números no layout de abas coladas no gráfico (o "A"), sem a linha em cima do card selecionado, que ganha fundo surface/sunken
- Aprovou (3/out/2026) "What stands out" (até 3 frases automáticas, só acima dos mínimos) e o "your usual" (primeiros 7 dias de cada post contra a mediana dos últimos 10 posts), com as frases novas; aprovou o 27.1 no Figma com ajustes dele (32 entre seções, 16 entre os cards)
- Revisto (3/out/2026), preocupado que "Below your usual" afastasse artistas: a tabela não marca post abaixo do normal (fica só "Above your usual" e "In its first 7 days"); a página do post mostra a comparação em números ("First 7 days: {n} views · Your usual: {n}"), com a marca verde só quando acima

## Prévias de link (3/out/2026)
- Quer incluir no redesign as imagens de prévia de link (Discord, X etc.) de posts, páginas e perfis: o site já tem algumas, mas ele acha que não são boas
- Decidiu (3/out/2026), depois de começado o protótipo das prévias de posts, deixar as prévias de link como pendência para o [[nedddz]], depois que ele terminar o sistema de moderação
- Decidiu (10/out/2026): só o Pro vê o período All time do Creator Dashboard; o "detailed analytics" do Pro são métricas extras mais um período de tempo maior
- Em 21/out/2026: o beta foi liberado para os artistas e os patrons, e ele acha que o lançamento sai em alguns dias; a fase agora é corrigir bugs e erros de design
- Lista de prioridades dele (21/out/2026), para continuar e provavelmente terminar o app: 1 novos designs do selo Early supporter; 2 atualizar os selos de gifter (mais detalhes e customização); 3 ideia de trocar a tela "your post has been uploaded" por voltar ao feed com um aviso no canto inferior direito por alguns segundos (continuar rolando, criar outro post, copiar link/compartilhar), porque muitas plataformas fazem assim e a prévia do post ainda carrega na tela atual; 4 layout de celular
