# Contexto do projeto · Redesign Wondx (atualizado em 1/out/2026)

Cópia do documento de contexto do projeto "Wondx redesign" no claude.ai, para que sessões fora do projeto comecem com ele.

**Versão de celular:** protótipo publicado em https://claude.ai/artifact/RcgYN3WqQD3UsGNostajVP (cópia em `prototype/index.html`). As decisões do celular ficam em `memory/redesign-mobile.md`.

---

**Quem sou e o que é a Wondx.** Yuri (Fair), cofundador da Wondx, um marketplace de assets digitais: wallpapers, PFPs, banners, perfis de Steam, arte e fotografia. Cuido de produto, UI/UX, frontend e comunidade; o Nedddz cuida do backend. Falo em português; o produto é em inglês.

**Onde o redesign está.** Figma, arquivo 3ZAMekpucqKTvLAlSbIJoi, página Final Screens. Fechados: acesso (1.1 a 1.6), onboarding (4.2, 5.1, 5.2, 6.1), feed (7.1 a 7.4; 7.5 cartão de perfil ao passar o mouse; 7.6 prateleira "Collections for you"), post (8.x), following (9.1 a 9.5), busca e categoria (10.x), coleções públicas (11.x, capa no estilo Pinterest), Library (12.x), página da coleção (13.x), perfil (14.x), upload (15.x), Explore (16.x), notificações (17.x), páginas de sistema (18.x), Official Creator (19.x), planos, Pro e Gift (20.1 a 20.7), leaderboard, pontos e badges (21.1 a 21.3, coluna x = 40718), help center (22.1 a 22.6, coluna x = 44674). O próximo bloco começa em x = 48630. O sistema de moderação está congelado desde 22/set/2026 (MODERATION-SYSTEM.md e a página "Moderation System | Rules & Pages"); só reabre por erro que quebre um fluxo, exigência legal ou dado real de uso.

**O que falta, nesta ordem.**
1. FAQ: os textos dos artigos do help center (FAQ do presente reescrito, sem "0% de comissão").
2. Página de Updates (ideia: metade progresso do app, metade anúncios).
3. Sorteio: depende de decidir as entradas 10x do Pro e 5x do Lite. Pela lei americana ("equal dignity"), quem paga não pode ter chance maior sem uma forma grátis de entrar com a mesma chance; Suíça e UE ficam para o advogado.
4. Landing e banner de cookies (preciso dos requisitos que o Nedddz passou).
5. Settings: conta, idioma e região, notificações, privacidade, perfil com edição e crop, tema, showcases, lista de seguidores, preferências de conteúdo (IA e aviso).
6. Dashboard de criadores, junto com o plano de eventos do Nedddz.
7. Modais de trocar de conta, com a revisão do Bloco 1 e o Figma do Bloco 1 com senha.

**Pendências de blocos já feitos.**
- Help center: prazo real de resposta ("We usually reply within 24 hours." é provisório); crédito da arte do banner (ainda diz "@haruki.px"); textos dos artigos (etapa do FAQ).
- Bloco 21: o painel de pontos do topo ainda não foi para o Figma (o protótipo está pronto; frases esperando ok: "Contribution points", "Recent", "Leaderboard" e a dica "A Steam Profile earns 14 to 25."); documento do Bloco 21 para o Nedddz (deixado para o fim); as seis decisões do documento de riscos dos contribution points; confirmar se o leaderboard conta pontos de interação ou só de upload.
- Coleções: tela de escolher a capa (13.x); regras da prateleira para o Nedddz (entra depois de uns 20 posts, uma vez por sessão, mínimo de 4 coleções).
- Bloco 20: documento para o Nedddz; advogado (20.4: confirmações legais, botões da UE, desistência depois de aceitar um presente).
- Menores: pergunta de IA no onboarding (5.1); linha do sino e e-mail de subida de estágio (20.7); número "Following" do perfil abrindo o modal 9.5; destino do link compartilhado da 20.7; onde aparece o anúncio do plano Free.
- Da minha lista de prioridades, ainda não começados: tarefas de onboarding com dicas; pôsteres para os fóruns do Discord (um por categoria); kit de PFP e banner do lançamento; melhoria das páginas 404; tela explicando a verificação; possível redesenho do top 3 do leaderboard. Celular só depois do redesign.

**Em aberto e esperando o Nedddz.** Warn como padrão e Suggestive sempre escondido para menores de 18; perguntas abertas do documento do Relevant; proporção de posts por tipo Steam; hub de comunidade no lançamento ou não; a tela da conta restrita e os motivos de recusa de arquivo (checar no MODERATION-SYSTEM.md). Post pago fica para a Fase 2.

**Decisões recentes que valem para as próximas telas.**
- Filtros (home, categoria, tag, busca e Public Collections): seção "Content" com "Show AI-generated posts" e "Posts with a content warning" (Warn · Hide); é preferência de conta, o Clear all não mexe, e acima da grade ficam chips tracejados com "Change".
- Steam Profiles: nível 2 é All · Full profiles · Showcases; Featured, Artwork, Workshop e Guide são o filtro "Showcase" no topo do painel. O upload segue com três tipos Steam.
- Following: sem coluna lateral; a lista completa fica no modal "Manage who you follow".
- Pontos por post (valores do site, 1/out): Digital Art 25, PFP + Banner set 24, Wallpapers 20, Photography 15, Steam Profiles 14 a 25, Steam Showcases 12, Steam Guides 12, PFPs 10, Banners 10. Recomendação do documento de riscos (sem decisão ainda): leaderboard só com pontos de upload, interação com travas, teto diário de upload pelo p95.
- Coleções: capa no estilo Pinterest em todos os cards (3:2, a maior imagem à esquerda é a capa, duas empilhadas à direita, espaço vazio em cinza). No feed, coleção só aparece na prateleira "Collections for you", com "See all".
- Cartão de perfil ao passar o mouse (7.5): formato do Instagram (foto, nome e selos, números, 3 posts; Follow + Guestbook, ou Guestbook + Following; só "Edit profile" no próprio nome); abre em 0,5 s, só com mouse.
- Help center: banner com arte da comunidade escurecida (overlay/scrim + overlay/backdrop com a camada a 40%, cerca de 62%), "How can we help?" e a busca no centro, crédito do criador no canto; atalhos urgentes de NCII e copyright; temas por tarefa em "Using Wondx" (6) e "Creating on Wondx" (3), em grade de três, título e descrição de uma linha e mesma altura; Popular articles; Resources; "Still need help?" numa linha com "Open a ticket on Discord" e "Email us". Artigo: "In short" em sunken como abertura, no máximo um quadro por artigo (Tip e Good to know em sunken), 32 px entre as seções, sem coluna lateral em artigo curto, "Related articles" no fim, "Was this article helpful?" com ícone e texto (o Button do kit não tem ícone, então no Figma fica só o texto).
- Tooltip de badge (board 21.3): raio 12, sem brilho, descrição em Geist Regular (copy/14), no máximo duas linhas e nunca uma ou duas palavras sozinhas na última; Verified em text/accent no modo escuro (#A5A3F8, 7,13:1 sobre o card); Discord em dois estados; Official Creator sem link. Os selos de co-founder, website moderator e associate são os do site em produção.

**Copy aprovada hoje.**
- Help center: "How can we help?" · "Questions about uploads, plans or your account? Start here." · "Search help articles" · "Someone shared intimate images of me" / "Get them removed. You don't need an account." · "My work was posted without permission" / "Send a copyright request." · "Using Wondx" · "Creating on Wondx" · temas: Getting started (Your account, profile and the basics.), Download and use assets (Downloads, the license and credit.), Collections and Library (Save posts and build collections.), Plans, billing and gifts (Pro, Lite, payments and gifts.), Safety and reporting (Reports, moderation and appeals.), Policies (Terms, privacy and copyright.), Upload and manage posts (File types, Steam showcases and edits.), Points and leaderboard (What earns points and how ranks work.), Official Creator and badges (The creator program and every badge.) · "Popular articles" · "Resources": Wondx brand assets (Logos, colors and how to use them.), Badges for your socials (Show your Wondx profile anywhere.), Discord bot commands (What the Wondx bot can do.) · "Still need help?" · "We usually reply within 24 hours." (prazo a confirmar) · "Open a ticket on Discord" · "Email us".
- Artigo e busca: "In short" · "Updated {date}" · "Was this article helpful?" · "Yes" · "No" · "What was missing?" · "Thanks for letting us know." · "Thanks. We read every answer." · "Related articles" · "You can apply if" · "You can't apply yet if" · "{n} results for '{query}'" · "No articles match '{query}'" · "Try fewer words, or browse a topic." · "See all results for '{query}'" · "No articles yet. Search anyway for '{query}'".
- Tooltips: Co-founder "One of the founders of Wondx." · Associate "Works alongside the co-founders." · Website Moderator "Reviews reports and moderates posts to keep Wondx safe." · Official Creator "A verified creator. Their posts can link to where the original is sold." · Discord: "WONDX DISCORD", "Member since {month year}", "{n} Online", "{n} Members", "Open the server" (membro) e "Join the server" (quem não é membro ou não conectou a conta).
- Coleções e perfil: "Collections for you" · "See all" · "No posts yet." · "Guestbook" · "Following" · "Edit profile".

**Medidas e kit.** Canvas 1440, conteúdo 1320, rail 72, margem 96, gap 16, tudo em múltiplos de 4, inclusive paddings, raios e posições. Bricolage faz display; Geist nunca passa de Medium; escala 13, 14, 16, 20, 24, 32, 48. Títulos: página em display/48, fluxo ou formulário em display/32, seção em title/20. Ícones em Phosphor Bold pelos SVGs oficiais (Fill no item ativo). Logos de marca vêm do Simple Icons; selos e ilustrações vêm do próprio arquivo. Cores por token da coleção Wondx, nunca valor solto: índigo é o que é clicável, verde é positivo, vermelho é perigo, âmbar é comércio. Botão só com ícone é círculo com contorno. Button do kit: Primary é o escuro; não tem espaço para ícone. Título de modal é verbo mais objeto e nunca muda pelo resultado. Copy sem travessão.

**Como quero trabalhar.**
- Faça só o que eu pedir, do jeito que eu pedir. Frase nova, cor, peça nova ou mudança fora do pedido vira pergunta antes de mexer. Decisão técnica é sua.
- Uma mudança por vez quando eu estiver revisando, com captura do Figma de cada frame alterado antes de dizer "pronto". Não mexa em frames que eu fiz ou editei.
- Design de produto sai primeiro em HTML, para eu revisar aos poucos, e só depois vai para o Figma. Protótipo publicado sempre no mesmo link.
- No Figma, clonar as peças que já existem em vez de redesenhar; o arquivo só tem Button e Category tabs como componentes. Sem frame espaçador. Só a página Final Screens conta. Estados, modais e variações num board branco; 200 px entre frames na coluna.
- Respostas críticas, não complacentes; se eu estiver errado, me diga, com dado quando houver. Pesquisar fora (NN/g, Baymard, fontes reais com números) quando a pergunta for de caso real que a Wondx não responde com dados próprios.
- A skill wondx guarda só processo. Quando ela mudar, entregar o wondx.skill num card separado. Decisões detalhadas por bloco, copy antiga aprovada e o diário de armadilhas estão nos arquivos decisoes-por-bloco.md, copy-aprovada.md e diario-armadilhas.md.

**Links.**
- Help center: https://claude.ai/artifact/MhVWGFgXYT3HgxupbinBnh
- Leaderboard e painel de pontos: https://claude.ai/artifact/NonhHnQefLXQZoaBUBV12D
- Coleções (capa e prateleira) e cartão de perfil: https://claude.ai/artifact/QFGpzarNSyGJpTiQJg5vrH
- Riscos dos contribution points: https://claude.ai/code/artifact/d53fc160-7999-4194-9845-a1bb5edc6695
- Bloco 20: https://claude.ai/artifact/Vz9G4qJsi7twXQKEcCg8RQ · 20.7: https://claude.ai/artifact/TKsc86x6ssLAENnB7Zfpao
- Navegação (home, categorias, busca, coleções): https://claude.ai/artifact/ExmE9DhexHVyHKAKfqx3Tm
- Following: https://claude.ai/artifact/9vyVUqcppLSMsstrXXwbVJ · Upload: https://claude.ai/artifact/ASKeqR3bebUkTk7MzYq1FB · Explore: https://claude.ai/artifact/3usiLHy8FpySLhhgwg4Ybq
- Post: https://claude.ai/artifact/DTSAxwWhT2QZt5RhDhfKLH · Notificações: https://claude.ai/artifact/YAgh2JiaTwiqmDCk25qB3n · Acesso e sistema: https://claude.ai/artifact/VfJjgT2RfnSbgdz3c2pece · Official Creator: https://claude.ai/artifact/1GPdpL2zoLvFarYZEzuwTK
- Documento do Relevant: https://claude.ai/code/artifact/f5552b57-57a1-47ae-8511-4fd269c6fd6b · Plano de eventos do dashboard: https://claude.ai/code/artifact/87564598-204c-419e-9c40-b9b0245f7e48

**Pessoas.** Nedddz (cofundador, backend), Sussing (manager). Os documentos de sistema são escritos para o Nedddz, que não participou das decisões.
