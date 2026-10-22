---
name: "wondx-settings"
description: "Settings do site Wondx hoje (Profile, Showcases, Account, Theme, Privacy) e como alimentam o perfil; redesign adiado, com dados reais"
---

- Edit profile NÃO é modal: é a página de settings do site (wondx.net/settings/profile) para onde o usuário é levado. As settings vão ser refeitas no futuro com dados reais de uso, removendo e adicionando opções, e por isso ficam fora do redesign do perfil por enquanto (22/set/2026) — ver [[redesign-perfil]]
- Como o sistema funciona hoje no site (capturas de 22/set/2026) — abas de Settings: Profile, Showcases, Account, Account status, Notifications, Theme, Privacy

## Profile (settings/profile)
- Banner (Upload Banner, Remove) e foto de perfil (Upload Image, Remove); Display name; Username com @ e a URL wondx.net/<username>, até 24 caracteres; Bio até 200 caracteres ("Appears below your name on your profile page"); Location por país; Contact details com o e-mail e a caixa "Show my Discord" (mostrado publicamente; o Discord abre o perfil de lá). Os links saíram daqui para Showcases

## Showcases (settings/showcases)
- O card ao lado da foto de perfil alterna entre painéis. O dono escolhe quais os visitantes podem ver (liga e desliga cada um), qual abre primeiro ("Open first") e, no Pro, a ordem, com setas; o número é a ordem
- Painéis: Activity (sempre ligado: heatmap, streak e rank no leaderboard), Links, Achievements (coming soon, ainda não existe), About (Pro), Featured work (Pro), Guestbook (mensagem e voto de rep)
- Links: limite por plano — Free 1, Lite 2, Pro 6 (22/set/2026); rótulo opcional mais a URL, e o ícone é escolhido automaticamente pela URL. No perfil oficial @wondx o widget mostra 6 links em duas colunas (Discord, X, Instagram, YouTube, TikTok, Patreon)
- About (Pro): versão longa da bio, com quebras de linha preservadas, até 1200 caracteres
- Featured work (Pro): hoje fixa até 6 posts, na ordem escolhida (o redesign do perfil fixa 3)

## Account, Theme e Privacy
- Account: login principal pelo Discord (com Sync Discord Roles), e-mail de cobrança para os recibos do Stripe, senha opcional para quem entra pelo Discord, contas conectadas (Google; Steam verificado libera Steam Showcase Guides), assinatura Wondx Pro (Manage Subscription), Gifts (link de presente /gifting?to=<user>, Gift Points e progresso para as badges de Gifter, enviados e recebidos) e Delete Account
- Theme: Light, Dark ou Auto; Compact mode, Reduce motion e High contrast
- Privacy: Public profile, Show contribution heatmap, Show follower count, Show like count, Show bookmarks publicly; Allow comments on posts e Appear in search results
- "Show like count" desligado esconde só o total de curtidas do perfil; o número de curtidas em cada post continua visível (22/set/2026)
- Perfil não público (Public profile desligado, com tela de login para quem não está logado) fica para depois, junto com a refação das settings (22/set/2026)

## Redesign do Settings (2/out/2026)
- O site hoje também tem as abas Feed (categorias que o For You mostra primeiro, com botão Save) e Account status (histórico de casos de moderação)
- Aprovou a navegação em dez seções: Profile, Showcases, Account, Billing (sai de dentro de Account; o nome ficou só "Billing", decidido em 2/out/2026, e a página já existe no Final Screens desde o Bloco 20), Notifications, Privacy, Feed (categorias do For You + preferências de IA e aviso de conteúdo), Appearance (antigo Theme) e Account status (fica como está, moderação congelada); botões de ligar e desligar salvam na hora, sem Save. A seção Language and region saiu inteira (2/out/2026): o site fica só em inglês por agora
- Aprovou o Notifications novo: grupo "Always sent" sem botão (sign-in e segurança, recibos e plano, decisões sobre posts ou conta); demais tipos com colunas In app e Email (e-mail de atividade em resumo semanal, respostas imediatas); Sales fica fora até a Fase 2; Purchases e Moderation Alerts deixam de ser botões (viram Always sent e "Report results")
- Limites confirmados (2/out/2026): bio 200 caracteres, nome de exibição 32 e username 24
- Decidiu (2/out/2026) no Showcases: o Lite também pode mudar a ordem dos painéis (o grátis não), e o About fica com 1.000 caracteres no redesign (o site hoje aceita 1.200)
- Pediu (2/out/2026) no Settings › Profile que trocar e remover foto e banner seja um botão na própria imagem que abre um menu (Upload new / Remove), no lugar das linhas com dois botões
- Showcases (2/out/2026): prefere o layout do redesign ao do site atual; pediu que cada painel vire um card com os próprios controles (ligar e desligar, abrir primeiro, ordem), sem a lista separada de painéis, e que os links mostrem o logo dos sites conhecidos (Discord, Instagram etc.) e um ícone de mundo para os desconhecidos (mudou em 3/out/2026: logos de marca coloridos só no login e nas contas conectadas do Settings; nos links do Showcases fica o padrão do widget Links do perfil, logo cinza num quadradinho e a primeira letra do endereço para site desconhecido)
- Apagar a conta (2/out/2026): 14 dias para desistir, como no Discord; comentários seguem o que a maioria das plataformas faz
- Aprovou (2/out/2026) no modal de apagar a conta a linha "Your Pro plan won't renew.": com Lite ou Pro ativo, pedir a exclusão faz o plano parar de renovar
- Privacy no redesign (2/out/2026): sai "Show bookmarks publicly"; os posts são sempre indexados por buscadores, sem opção de desligar (o botão de busca vale só para a busca e o Explore da Wondx); desligar comentários vale só para os posts publicados depois, com a opção daquele momento. O site já tem "Who can sign your guestbook" (Everyone, People you follow, Nobody)
- Appearance no redesign (2/out/2026): sai o Compact mode, e o High contrast também sai por agora; o Reduce motion fica. Aprovou o grupo "Motion" no modelo do Discord: "Reduce motion" (começa ligado se o aparelho pedir) e "Play animations automatically" (posts em GIF, fotos e banners animados; desligado, tocam ao passar o mouse), que fica desligado e travado quando o Reduce motion está ligado
- Aprovou (3/out/2026) os modais que faltavam no Settings e mandou levar ao Figma: Change email (novo e-mail + senha atual, código para o endereço novo), Change password / Set a password, Change receipt email (sem código) e Pin a post (até 3 fixados); conta que só entra pelo Discord confirma a troca de e-mail com "Continue with Discord" no lugar da senha
- Aprovou (8/out/2026) a recuperação da conta nos 14 dias: ao recuperar, o plano continua sem renovar (religa pelo Resume plan no Billing); durante os 14 dias, perfil, posts e comentários ficam escondidos e o link do perfil dá a 404; passado o prazo, vale o estado de conta encerrada (14.3)
