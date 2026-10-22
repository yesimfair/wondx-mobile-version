---
name: "redesign-topbar"
description: "Topbar do redesign Wondx — quatro estados de sessão, onde o Pro entra e o debate sobre qual botão leva o preenchimento"
---

## Estados de sessão (20/set/2026)
- A topbar tem QUATRO estados, não dois: deslogado; logado sem plano; logado Lite; logado Pro
- Deslogado: só "Log in" em texto e "Sign up" preenchido — nada de Get Pro nem Upload, que exigem conta. O site ao vivo hoje mostra os dois, e isso está errado
- Logado sem plano: botão "Pro". Logado Lite: o mesmo botão diz "Upgrade", não "Get Pro" — reconhece o que a pessoa já tem
- Logado Pro: nada de venda; o slot vira a badge do tier dentro da pílula de pontos
- Ordem atual do cluster: Upload, pontos, sino, avatar. O botão do Pro entra colado nos pontos, porque são o mesmo assunto
- Evidência para esconder do assinante: guia de churn lista "botão Subscribe ainda aparecendo para quem já assinou" como fricção real, e trocar por "My Account" depois do login reduziu carga de suporte
- Evidência para esconder deslogado: é indireta, vem das próprias medições de onboarding dele (paywall depois de valor = 2,1× mais início de trial; 40–60% melhor depois de 3–5 telas de valor)
- Nodes: 8573:2 (as quatro topbars empilhadas a 1440)

## FECHADO em 20/set/2026: o Upload fica com o ink
- Escolheu manter o Upload preenchido e o botão de assinatura em contorno — descartou inverter agora. As variantes invertidas ficaram no Figma marcadas como NÃO ESCOLHIDO (8575:2 e 8575:24)
- Rótulos fechados: "Get Pro" para quem não tem plano, "Upgrade" para quem tem Lite
- Nada de ícone na pílula de pontos — a badge do tier NÃO fica na topbar, fica no menu do avatar (ao lado do nome e como ícone da linha do Wondx Pro)
- Consequência aceita: o assinante Pro se distingue na topbar por AUSÊNCIA do botão de assinatura, não por marca própria

## Histórico do debate sobre qual botão leva o ink
- Proposta dele e do [[nedddz]]: fazer o botão de assinar PREENCHIDO em ink e o Upload virar secundário, seguindo o que observaram no Behance e no Dribbble
- A favor: NN/g mediu 90% lurkers, 9% contribuindo pouco e 1% respondendo por quase toda atividade — o Upload como botão mais forte serviria ~1 a 10% das pessoas
- Contra, no caso da Wondx HOJE: em comunidades abaixo de 5.000 membros, 33% são criadores e contribuidores, três vezes o padrão; entre 10k e 50k cai para 20%; só acima de 50k chega em ~5%. A Wondx é pequena e o público veio de um Discord de artistas
- Contra também: o gargalo da Fase 1 é oferta, não receita; e o posicionamento escrito da Wondx é creator-first e NÃO monetization-forward
- Minha recomendação, ainda não decidida por ele: Upload em ink na Fase 1, Pro fantasma, com gatilho ESCRITO para inverter — quando a participação de criadores cair abaixo de ~10% da base, ou quando o catálogo deixar de ser o gargalo (na prática a Fase 2). E mesmo invertido, o Upload não deveria virar fantasma puro num marketplace onde o criador é o fornecedor

## Alinhado ao site no ar (21/out/2026)
- Mandou atualizar a topbar e a barra lateral de todas as telas do Figma para as medidas do site no ar; a pílula de pontos mostra também a posição no leaderboard ("#21") em todas as topbars logadas, e o item do Official Creator na barra lateral segue o site (o selo colorido); o ponto vermelho de notificação passa a ser recortado do ícone, sem anel
