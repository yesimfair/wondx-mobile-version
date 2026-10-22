---
name: redesign-perfil
description: Perfil no redesign Wondx — o que fica do perfil atual: Contributions e suas variações, banner no método do YouTube e badges
sources: [chat]
aliases: [perfil wondx, profile page, página de perfil, contributions]
---

- Ao abrir o redesign do perfil (22/set/2026), quer MANTER: a seção Contributions e as variações dela (links, guestbook, featured work etc. — guestbook detalhado em [[wondx-telas]]), o banner usando o método do YouTube e as badges ao lado do handle. O resto do perfil está aberto para análise e mudança
- Aprovou (22/set/2026, "prototipe assim"): o perfil mostra o rank do MÊS ("#2 this month"); nos primeiros dias do mês mostra o último mês fechado ("#2 in August"); o rank só aparece dentro de um corte (top 100 como ponto de partida, a ajustar pelo número de criadores ativos); o ranking semanal (a Wondx tem os dois, semana e mês) fica no leaderboard e na tela de publicado. Base: efeito recomeço mais forte na semana (bom para competir), reset desmotiva quem vinha bem (Dai 2018), semana tem o dobro de ruído, e o Duolingo mostra a liga no perfil, não a posição semanal
- Diagnóstico do perfil atual aceito como ponto de partida do Bloco 14: largura 970 em vez de 1320; grade em quadrados (volta a masonry, mesmo card do feed); "All Categories" em dropdown (vira segmentado com All + categorias com posts); botões do cabeçalho fora do padrão; "Collections 0" para visitante; seletor do Contributions sem rótulo; About repetindo a bio e contador de caracteres visível; rodapés que repetem; Guestbook com rolagem própria e sem Sign; links em dois formatos (domínio sempre visível); rank sem período; Featured em quadrado. No lançamento as abas são Posts e Collections, mais Drafts para o dono (Store só na Fase 2)
- Primeiro protótipo HTML do perfil publicado em 22/set/2026 (https://claude.ai/artifact/VmQHPVGBY5ao1Ye4M69pGF), com a recomendação de bio de uma linha embaixo do nome e About como texto longo dentro do Contributions (some para o visitante quando vazio) — a revisar por ele
- Contributions (22/set/2026): os widgets eram o que ele menos gostava no design atual e quer o componente exatamente como está no site (cabeçalho com título e contagem, selos de streak e rank, dias da semana, seis níveis, legenda Less/More), só com as correções; decidiu a largura de 640px e o seletor com ícone + nome na aba ativa e só ícone nas inativas (nome em tooltip no hover e no foco)
- Aprovou (22/set/2026) dois comportamentos do perfil: apagar uma assinatura do Guestbook não abre modal — some na hora, com toast e Undo (no menu do dono e no Edit your signature); e o Unfollow é direto — clicar em Following deixa de seguir e o próprio botão desfaz, como o Subscribed da coleção
- Aprovou (22/set/2026) o protótipo do perfil como base para o Figma, com as frases novas (estados vazios, Guestbook limitado, ajudas do Edit profile, "This account is closed"), os limites bio 100 caracteres (corrigido em 2/out/2026: a bio é de 200), About 1.000 e até 5 links, e o texto do popover "How contributions count" — as regras de pontuação ainda dependem de confirmação do [[nedddz]]
- Correção (22/set/2026): Links vão até 6, como no site (o perfil oficial @wondx tem 6), e o widget precisa ficar consistente com mais de 3 links
- Edit profile e Edit featured work saem do redesign do perfil (22/set/2026): editar o perfil é a página de settings, que será refeita depois com dados reais (ver [[wondx-settings]]); no perfil, os pontos de entrada levam para Settings › Profile e Settings › Showcases
- Featured work fica em até 3 posts no redesign (o site hoje deixa fixar 6)
- Refez os ícones do perfil no 14.1 (22/set/2026), direto da biblioteca do Phosphor
- Aprovou (22/set/2026) as recomendações pendentes do Bloco 14: menu da assinatura para staff igual ao ⋮ de comentário do 8.3 (comment track, Remove this signature, Warn this account, Add a note, Route to safety, Open in the moderation panel; Lift this restriction para o head quando há pausa), Report antes de Delete no menu do dono, "Open in the moderation panel" sem seta, tooltip de curtidas sem bolinhas e seletor sem cortar a sombra da aba ativa
- Aprovou (22/set/2026) fechar o resto do Bloco 14 num plano curto em fases: aplicar o que já estava aprovado, ícones (depois que ele refizer), links até 6, estados que as settings reais produzem (painel desligado, outro painel abrindo primeiro, dono sem Pro, contagens e mapa escondidos) e uma nota final do que o perfil espera das settings

- Aprovou (23/set/2026) as regras dos estados que as settings produzem: painel desligado some para todos, inclusive o dono; se o painel que abre primeiro estiver desligado, vazio ou fora do plano, o widget abre no Activity; ordem própria só no Pro (mudou em 2/out/2026: Lite e Pro podem mudar a ordem dos painéis, só o grátis não); sem Pro, About e Featured work somem e não há oferta de Pro no perfil; contagem escondida some sem nada no lugar e o dono sempre vê as suas; mapa privado mantém pontos, sequência e rank — frases aprovadas "Haruki keeps the activity map private." (visitante) e "Only you see the map." (dono)
- O documento do perfil para o [[nedddz]] fica para depois do redesign completo (23/set/2026)

## Para o documento do [[nedddz]] (regras de backend do perfil)
- Quando o Pro vence, o About e os posts fixados em Featured work NÃO são apagados: ficam guardados e escondidos até a pessoa voltar ao Pro (22/set/2026)
- Limite de links por plano: Free 1, Lite 2, Pro 6 (22/set/2026)
- Links acima do limite do plano também ficam guardados e escondidos, e voltam com o plano; o widget mostra os primeiros, na ordem das settings (23/set/2026)
- "Show like count" desligado esconde só o total de curtidas do perfil, não o número em cada post (22/set/2026)
