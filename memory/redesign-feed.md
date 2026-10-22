---
name: "redesign-feed"
description: "Feed do redesign Wondx — rolagem infinita e restauração de posição, renomear Bookmarks para Library, e correções de medida ao documento de contexto"
---

## Rolagem
- DECIDIDO: rolagem infinita, sem corte de "carregar mais" a cada N lotes
- Voltar de um post aberto devolve a pessoa exatamente onde ela estava antes de clicar
- Aceita que a barra de rolagem deixe de informar quanto falta

## Navegação
- DECIDIDO: a página Bookmarks vai ser renomeada para Library (ela já guarda Collections, Saved posts e Downloaded). O item "Library" some do menu do avatar
- O bookmark do card hoje abre um seletor para escolher em qual coleção salvar, igual ao Pinterest — salvar um post é sempre salvar dentro de uma coleção
- Concordou (21/set/2026): a Library passa a ter duas abas, Saved · Downloaded. Saved reúne as suas coleções (com um card "All saved" com tudo); as coleções que você ASSINA saem da Library e ficam só no Following (aba Subscribed collections)
- Só o badge de verificado aparece no card do feed — nenhuma outra badge. Motivo dele: o foco do feed é a arte, não quantas badges o criador tem

## Correções ao documento de contexto de 19/set/2026
- A sidebar é 72px de largura, não 64 como o documento diz
- A sidebar deslogada é IDÊNTICA à logada — não perde os itens que exigem conta, ao contrário do que o documento afirma
- Existe a página "Final Screens" no arquivo 3ZAMekpucqKTvLAlSbIJoi, com as telas 1.1 Sign Up, 1.2 Log In, 1.3 Code, 5.1 Interests, 5.2 Wondx Pro, 7.1 Feed logged out (8505:2) e 7.2 Feed logged in (8517:2)
- A masonry medida no Figma é 1320 começando em x=96, não 1328 — confirmar com ele

## Adiados por escolha dele, não resolvidos
- Recuperação de conta sem acesso ao e-mail — adiado, não é foco do lançamento
- Badge de assinatura como sinal público de valor de conta — adiado, pensar no futuro
- O curtir com fundo no site (divergência da variação A) — fica para quando o [[nedddz]] implementar as mudanças no site ao vivo; a revisão das páginas vem primeiro

## Rota vs overlay do post — nota para o documento do [[nedddz]] (20/set/2026)
- Hoje a Wondx usa ROTA de verdade quando alguém clica num card do feed. Ele PREFERE overlay, mas a decisão de implementação é do [[nedddz]]
- Testou o Pinterest ao vivo e concluiu que lá também parece ser rota — eu tinha afirmado overlay sem verificar e retirei a afirmação (idem sobre o Dribbble)
- O padrão que dá os dois (SEO + posição preservada) é rota de interceptação do Next.js, que a stack Vercel já suporta: /post como página real indexável, e @overlay/(.)post renderizando em overlay quando a navegação vem de dentro do app. Com overlay o feed nunca desmonta, então restaurar posição deixa de ser trabalho
- Defeito conhecido a vigiar: rotas de interceptação disparam com mudança só de hash ou só de query string e podem renderizar página e overlay ao mesmo tempo
- Se for por rota: history.scrollRestoration = "manual" (Baseline desde jan/2020), NUNCA restaurar por coordenada Y (a masonry muda de tamanho), a URL precisa carregar quantos lotes foram abertos, cards placeholder do tamanho certo para evitar o jank de restaurar antes de renderizar, e não quebrar o bfcache
- Consequência de desenho: com overlay a tela do post passa a ter DUAS apresentações — overlay com fundo escurecido, fechar e Esc; e página cheia para quem entra direto ou vem do buscador

## Fim do feed e faixa de tópicos (20/set/2026)
- Cartão de fim de feed aprovado em duas versões: logado ("Change your topics" + "Back to top") e deslogado (Sign up preenchido + "Back to top"). Frames 8560:6 e 8560:18
- A copy "New work lands here every day" fica como está — o plano é postar diariamente, com posts de artistas e da própria Wondx
- A faixa de primeira sessão deixa de ser TIRA acima da grade e vira CÉLULA DA GRADE, 251 de largura, na PRIMEIRA POSIÇÃO DA COLUNA 3. Comparou coluna 1 contra coluna 3 e fechou na 3
- "Change topics" dentro da célula é LINK em texto, não botão — o botão branco era o único elemento branco sólido da tela e competia com a arte
- Dispensar com Phosphor X Bold 16, área clicável de 24 (critério 2.5.8, mesmo truque do botão de curtir)
- Recusou escrever exceção na regra de iconografia para ícones sem Fill: acha que documentar isso é óbvio demais para valer a regra
- Vida da célula: sai na primeira curtida ou salvamento, ou no fim da primeira sessão — o que vier primeiro. Sempre dispensável e sem informação exclusiva
- Segundo uso do mesmo componente: reaparece uma vez como CONFIRMAÇÃO quando a pessoa troca os tópicos
- Base da decisão: NN/g 2026 mede que banners são pulados de forma reflexa, com filtro no nível do FORMATO (contêiner, posição, borda) antes da atenção consciente; NN/g 2024 mediu tooltips sem gatilho contextual dispensados 82% das vezes em 1,2s; Amplitude em 1.247 apps achou 11,2% de ação sobre tooltip estático. Por isso o formato de tira foi descartado, não a duração
- Nodes: célula de origem 8564:14, tira descartada 8564:2, variantes de teste do feed 8565:2 (coluna 1) e 8566:2 (coluna 3, a escolhida)
- Aberto nessa célula: o hover dos ícones de traço (X, setas, chevron — não têm Fill, então o estado ativo é cor ou fundo), se o chip "+6" fica órfão na segunda linha, e desenhar o estado de confirmação

## Onboarding por categorias (21/set/2026)
- O [[nedddz]] mudou o onboarding para escolher CATEGORIAS em vez de tópicos, porque personalização por tópico não funciona até haver muito conteúdo
- O [[nedddz]] confirmou: é PESO, não filtro — o que a pessoa escolhe aparece mais, o resto continua aparecendo; com o tempo, as ações dela adaptam o feed. Na visão dele, uma função de preferência de verdade precisa de centenas de milhares de posts
- O onboarding ao vivo tem o mesmo layout da 5.1 do Figma, só que com categorias
- Seguiu com e aplicou: 5.1 (e 4.2) com as 5 categorias e mínimo de 1, texto de peso no lugar de "build your feed from them"; a célula de primeira sessão da 7.3 lista as categorias escolhidas; a fileira de tags da home logada passa a ser as tags mais usadas dentro das categorias escolhidas (substitui "tópicos do onboarding primeiro")
