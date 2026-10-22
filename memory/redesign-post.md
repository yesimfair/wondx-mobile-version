---
name: "redesign-post"
description: "Página do post no redesign Wondx — trilha ao lado da arte, palco atrás da imagem, comentários dentro da trilha, a gaveta de comentários (um nível de respostas) e o More like this como continuação da masonry"
---

- Layout fechado: trilha AO LADO da arte (rail beside), não empilhado — ele viu os dois no protótipo HTML e escolheu a trilha
- O "More like this" da página do post É a continuação da masonry infinita do feed — nada pode vir depois dele, por isso os comentários não podem ficar abaixo
- Atrás da arte há um PALCO (fundo sunken) preenchendo o slot; ele achou o palco "muito grande e desproporcional" quando tinha altura fixa e quer só bordas pequenas em volta da arte, como nos frames iniciais dele (node 2749:1101)
- Está desenhando a tela no Figma como "8.1 Post open" (node 8608:3): palco 896 de largura, trilha 400, pílula de curtir com contagem mais botões redondos (salvar, compartilhar, martelo de moderação, ···), card do criador com tinta e badge, Follow em accent
- Comentários vão DENTRO da trilha, embaixo das tags, com a trilha presa à altura do palco e o campo de escrever fixo no pé; "More like this" abaixo do palco como masonry com os cards do feed
- Regra do palco implementada e aceita no protótipo: altura = clamp(arte + 64, mínimo da trilha ~330, orçamento vertical); preenche o slot na horizontal sempre, segue a arte só na vertical
- Consequência medida: no 16:9 a região de comentários fica pequena (83px no Figma a 1080); fallback proposto é gaveta lateral (<dialog> já no DOM) quando a região cai abaixo de ~240
- Protótipo HTML publicado com os modos de comparação: https://claude.ai/artifact/2TbPLkLfbA6sUgnsgkzCyE

## Ordem dos comentários — regra fechada para o [[nedddz]] (21/set/2026)
- DECIDIDO: nada de segmentado Top/Newest na gaveta. Ele observou que Instagram e TikTok não fazem isso e pediu a regra real; o seletor saiu e virou um overflow discreto no cabeçalho
- DECIDIDO: existe comentário FIXADO pelo criador, acima do ranqueamento, com etiqueta "Pinned by the creator". Fixar é permissão do autor do post e entra no menu ··· do comentário
- Como Instagram e TikTok realmente ordenam, e é a base da regra: (1) a ordem padrão NÃO tem rótulo e não é cronológica nem por curtidas — é relevância por espectador; (2) o Instagram declarou que comentários em posts de contas maiores priorizam as interações mais relevantes para quem vê, e a transparência da Meta diz que cronológico é opt-in por "Most recent" num menu suspenso; (3) o Mosseri sobre ranqueamento em geral: "recência importa muito, por isso ficam aproximadamente em ordem cronológica, mas não estritamente cronológica"; (4) no TikTok os comentários do topo são ranqueados por engajamento — curtidas no comentário e cadeias de resposta —, com relevância para o espectador e filtragem de spam, e a ordem pode diferir entre duas pessoas; fixados ficam acima de tudo (TikTok permite até 3, Instagram 1)
- Tradução para a Fase 1 da Wondx, sem ML: fixado primeiro (1 por post), depois pontuação = curtidas no comentário + respostas com peso + bônus se o criador respondeu ou curtiu, com decaimento por recência; bônus para quem o espectador segue (o grafo já existe); comentário recém-enviado pelo próprio espectador aparece no topo na hora; spam e moderado ficam fora; "Most recent" como opção explícita no overflow
- A parte cara é o "relevância por espectador" — dá para lançar sem ela e ainda ficar correto; o resto é aritmética simples
- Aprovou (27/set/2026) o rótulo do comentário fixado "Pinned by [nome do criador]", com alfinete, como no YouTube — no lugar de "Pinned by the creator". O teaser da trilha mostra o fixado primeiro; sem fixado, o primeiro da ordem padrão
- Nodes: gaveta = 8.2 Comments · side sheet (8623:2), 480 × 1016

## Galeria de várias imagens (25/set/2026)
- Palco com várias imagens: foi de "Fits the tallest" (o palco se mede uma vez pela imagem mais alta do post), porque no Figma a arte preenche as laterais por completo (imagem em FIT na 8.1)
- Tags na página do post: contorno sem "#", o chip do kit
- Guias da Steam (os "steam guide showcases" que sobem na Wondx) costumam ter o mesmo formato de PFP, 1:1
- Showcases a ~80% do tamanho real no palco está ok; clicar abre tela cheia com fundo escurecido na mesma página
- Download de post Steam (25/set/2026): é um ZIP só com os arquivos que o criador subiu; nada de lista "What's in the ZIP" nem guia de instalação na página — o criador pode pôr isso na descrição. Quer menos texto nessas páginas: muita gente não lê e só clica em Download
- Steam Profile (25/set/2026): os itens da Steam saem da trilha; no lugar, um botão "Recreate this Steam profile" (ou parecido) abre um modal com os itens — ideia deles, espelhando um recurso que a equipe já faz no servidor do Discord
- O "Recreate this Steam profile" já existe no site ao vivo (25/set/2026): modal com os itens agrupados por onde se compram, um ícone por tipo porque a Wondx não consegue puxar a imagem do item da Steam, e "Copy links". O botão fica AO LADO do Download, não embaixo
- Pelo que a equipe vê no Discord, as pessoas abrem os itens do Recreate um por um (25/set/2026)
- Aprovou (26/set/2026) os rótulos curtos "Download ZIP" e "Recreate this profile", lado a lado, no lugar dos do site ao vivo ("Download assets (ZIP)" e "Recreate this Steam profile"), e as frases "Download all · ZIP · …" (link embaixo do Download nos posts de várias imagens) e "Wondx doesn't sell these items." (nota do modal do Recreate)
- Altura do palco (26/set/2026): a galeria e a trilha formam um bloco só — a altura máxima do palco, com as miniaturas embaixo, vai até o fim da trilha (o campo de comentário), como se fosse um frame apenas; exemplo dele no frame 8.4 (trilha de 659 px, palco de 579)
- Modal do Recreate sem marca de item aberto (26/set/2026): ele achou o check que aparece depois do clique confuso — quem vê não entende o que aconteceu

## Editar e apagar post (26/set/2026)
- Apagar um post estorna todos os pontos que o post rendeu
- Depois de apagar, Undo de 8 segundos; sem lixeira de 30 dias no lançamento, sem saber se os usuários vão querer isso
- Aprovou (26/set/2026) o "More info" no menu ··· do post, que abre o modal "About this post" (Published, Category, Files, License; nos posts de link, "Opens"): a linha de arquivo sai de baixo do Download e vai para o modal, e nos posts de Steam o modal também leva a linha do ZIP ("ZIP · 2 showcases, 7 pieces · 4.3 MB") e a de nível
- Os PFPs e banners da Wondx são feitos para qualquer plataforma que aceite PFP e banner animados, não só o Discord — aviso de animado não pode falar só do Discord (26/set/2026)
- Aprovou (26/set/2026) o aviso de animado novo: chip "Animated" no palco e, no "About this post", a linha "Moves only in apps that support animated profiles. Some, like Discord, need a subscription." — só em posts de PFP & Banner; a mesma frase substitui a do Discord no upload
- Modal de compartilhar no site ao vivo (26/set/2026): "Share this post", prévia do post, "Copy link" como ação principal e "Share to" com X, Reddit, WhatsApp, Telegram, Pinterest, Facebook e More; a equipe decidiu tirar o Discord, porque o botão dele era o mesmo que copiar o link e não levava ao Discord

## Gaveta de comentários (8.2 Comments · side sheet, 21/out/2026)
- Decidiu (21/out/2026): respostas com um nível só, sem linhas de thread como as do YouTube e do Reddit
- Decidiu (21/out/2026): a fileira rápida de emoji só aparece quando a pessoa está escrevendo e clica no emoji; botão de enviar em ink; contador de caracteres só a partir de 400 de 500
- Aprovou (21/out/2026) e mandou levar ao Figma: ··· e × do cabeçalho como círculos com contorno de 36; comentário com 0 curtidas mostra só o coração, sem número; Enter quebra linha e Ctrl/⌘ + Enter envia (e salva ao editar). Pediu no board uma nota explicando por que as respostas não têm linhas de thread
