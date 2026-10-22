---
name: "redesign-autenticacao"
description: "Acesso (Bloco 1) e páginas de sistema (Bloco 18) do redesign Wondx — perfil na 1ª ação pública, passkey, sem Pro no modal, status page"
---

- Autenticação e páginas de sistema começaram como Bloco 18 do redesign (27/set/2026). Protótipo: https://claude.ai/artifact/VfJjgT2RfnSbgdz3c2pece
- Decidiu (27/set/2026) que as telas de acesso (sign up, log in, código, passkey, estados de erro e set up profile) viram as primeiras do Final Screens, como Bloco 1, no lugar das antigas 1.1–1.3, que foram apagadas; o Bloco 18 ficou só com as páginas de sistema
- Conta com o mesmo e-mail em outro método de login: ligar as contas automaticamente quando o e-mail é verificado dos dois lados; senão, mandar a pessoa para o método original (27/set/2026)
- Página de status como a do Discord (27/set/2026)

## Decisões aprovadas (27/set/2026)
- Perfil (foto + @) pedido só antes da PRIMEIRA ação pública, não no cadastro: postar, comentar e responder, assinar Guestbook e tornar uma coleção pública. Curtir, salvar, seguir e baixar não pedem
- Toda conta nasce com um @ provisório (do nome do Discord ou do Google, ou da parte antes do @ do e-mail, com números se já existir); o passo de perfil chega preenchido
- O passo de perfil não perde o que a pessoa estava fazendo: o comentário digitado é publicado depois de salvar, o upload segue de onde parou
- SEM banner nem apresentação do Pro no modal de perfil. Aprovada (27/set/2026) só uma linha contextual: quando alguém do plano grátis escolhe uma foto animada, a foto fica com o primeiro quadro e aparece "Animated pictures come with Lite and Pro." com o link "See plans" (foto animada vem no Lite e no Pro), medida com um evento
- Aprovada a tela de passkey depois do login por código: "Sign in faster next time" / "Save a passkey on this device. Next time, you won't need a code." / "Create a passkey" / "Not now"
- Ordem dos botões de login decidida por dado real: pedir ao [[nedddz]] a divisão das contas por método (Discord, Google, e-mail) nos últimos 90 dias
- 404: registrar os endereços que dão 404 e criar redirecionamentos 301 para o que mudou de lugar; o código fica pequeno no pé, sem número grande. Post indisponível: o feed embaixo se chama "More {categoria}" (ex.: "More wallpapers"), sem subtítulo (aprovado 27/set/2026), e mede os cliques pelo campo de origem do evento de visualização
- Conta encerrada NÃO tem página de sistema própria: usa o estado "Closed account · visitor" do 14.3 do perfil ("This account is closed" / "Its posts and collections are no longer on Wondx."), respondendo 410; um @ que nunca existiu recebe a 404 (aprovado 27/set/2026)
- Página de status hospedada fora dos servidores da Wondx (Statuspage, Instatus ou Better Stack) em status.wondx.net; a do Discord é feita no Statuspage da Atlassian. Erro do servidor e manutenção apontam para lá

## Métricas para o documento do redesign (pedidas em 27/set/2026)
- Participação: 90% dos usuários de comunidades online só olham, 9% contribuem de vez em quando, 1% faz quase tudo (Nielsen, NN/g, "Participation Inequality", 2006) — base para pedir perfil só na primeira ação pública
- Passo extra antes do objetivo: 19% de 1.026 adultos nos EUA abandonaram uma compra por não querer criar conta (Baymard)
- Momento de vender assinatura: cerca de 50% das conversões pagas acontecem no dia 0, e oferta antes de a pessoa entender o produto soa brusca (RevenueCat, State of Subscription Apps 2026 — apps de assinatura)
- Banner: as pessoas ignoram o que parece anúncio (posição, visual, proximidade de promoções); texto simples é lido (NN/g, Banner Blindness Revisited)
- Passkey: 98% de sucesso contra 32% com senha, e pedir a passkey depois do login reduziu o uso de senha em mais de 20% (Microsoft); 93% contra 63% no FIDO Passkey Index (out/2025); adesão de 2–5% quando o pedido fica só nas configurações; mais de 90% das passkeys da Uber vieram de lembretes no login e no cadastro, 99% das do TikTok de um único pedido
- Página de erro: dizer o que houve em linguagem simples, sem culpar, o que fazer e o código pequeno (USWDS); sem caixa de busca na página quando o cabeçalho já tem (CMS.gov); removido de vez responde 410
- Aprovou (27/set/2026) as frases novas do Bloco 18: os erros de acesso, o modal "Set up your profile" (incluindo a regra do @: 3 a 30 letras, números, pontos ou sublinhados) e as páginas de sistema (404, 410 de post, 500, 429, manutenção)
- Passkey fica fora do lançamento (29/set/2026): o [[nedddz]] decidiu segurar porque a passkey do Supabase ainda não tem suporte estável e seria um dos métodos menos usados; o design da tela fica guardado para quando entrar, e ele achou ok
- Senha mantida (29/set/2026), depois de o [[nedddz]] ser contra tirá-la: aceitou a recomendação revisada — e-mail + senha, com "Email me a code instead" como alternativa (serve também de esqueci a senha; juntado ao "Forgot password?" em 3/out/2026); proteção contra senha vazada do Supabase ligada (consulta o HaveIBeenPwned e recusa senhas vazadas; plano Pro para cima); 2FA obrigatório para moderadores e equipe como requisito de lançamento (TOTP do Supabase ou conta do Discord com 2FA); passkey depois do lançamento. No Bloco 1 entram o campo de senha, "Forgot password?", "Email me a code instead", a criação de senha no cadastro e um estado de senha vazada — aprovou (29/set/2026) as regras de senha e as frases novas propostas para o acesso (o mínimo de caracteres ainda depende do [[nedddz]]); o protótipo de acesso já tem a senha, e o Figma do cadastro e do login fica para depois
- Mínimo da senha definido (3/out/2026): 8 caracteres (antes a proposta era 15); no campo de senha, o "Show" vira um ícone de olho
- Motivos da senha mantida, para o documento: quem entra por e-mail no site atual já usa senha; login só por e-mail depende da entrega (atraso, spam, troca de app; alguns e-mails levam de 3 a 10 minutos); o próprio Supabase diz que OAuth e link por e-mail são mais seguros, mas que as senhas vieram para ficar
- Regra de troca de @ aprovada (1/out/2026): uma troca a cada 30 dias; o @ antigo fica reservado para a própria pessoa por 30 dias; o link antigo do perfil redireciona para o novo enquanto ninguém pegar aquele nome
- Trocar de conta (3/out/2026): aprovou o modal "Switch accounts" no modelo do Discord (aberto pelo menu da foto de perfil, até 5 contas no aparelho, "Add an account" leva ao Log in) e as frases novas; pediu para levar ao Figma junto com o Bloco 1 com senha
- Pediu (3/out/2026) o Switch accounts mais parecido com o Discord: conta deslogada continua aparecendo na lista com o texto em vermelho (é bloqueio), e "Current" em verde. Revisto no mesmo dia: as outras contas têm um botão "Switch"; o "···" serve só para "Log out", sem "Log in" no menu
- Decidiu (3/out/2026) juntar o "Email me a code instead" com o "Forgot password?": sai o botão do código; "Forgot password?" manda o código, a pessoa entra e criar a senha nova é opcional ("Not now"). Quer o "Forgot password?" em texto secundário, como "Log in" e "Create an account"
- Escolheu (9/out/2026) pedir a data de nascimento no cadastro, em vez de tirar as regras para menores de 18; até então o site não pedia a data de nascimento
- Aprovou (9/out/2026) pedir a data de nascimento numa tela própria logo depois da conta criada, antes do 5.1, e não no formulário de e-mail e senha
- Aprovou (9/out/2026) as frases da tela de data de nascimento: "When’s your birthday?" · "We use it to keep Wondx right for your age. It won’t show on your profile." · "Month" · "Day" · "Year" · "Continue" · "Log out" · erros "Enter your full date of birth." e "Enter a real date." · menos de 13: "We can’t create your account" / "You don’t meet the age requirements to use Wondx." / "Back to Wondx"
- Decidiu (10/out/2026): quem perdeu o acesso ao e-mail da conta é mandado para o ticket no Discord e para o contato por e-mail
