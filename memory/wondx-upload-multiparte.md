---
name: "wondx-upload-multiparte"
description: "Upload da Wondx — regras de 23/set (caminhos, arquivos, peças Steam, qualidade, extras no zip), limite de tags de 25/set e respostas dos artistas"
---

- Workshop showcases e steam profiles são posts de 5 peças + capa; o [[nedddz]] disse que o backend é fácil e o difícil é o front, e deixou o design com o usuário ("you design it, I just build")
- A plataforma já aplica marca d'água automática no preview, e ela aparece com o nome do artista e o da Wondx
- Set/2026: o usuário abriu uma pergunta no artist chat do Discord perguntando como os artistas lidam com capa, upload de várias partes e o que os faz abandonar um post

## Respostas dos artistas
- O [[stammy]] posta o GIF montado e entrega as 5 peças separadas no download: prévia e entrega são coisas diferentes, e a capa não é uma das cinco peças
- O Chubby (artist chat) pediu envio em lote no padrão da extensão Steam Artwork Hub: soltar vários arquivos, cada um vira um card, e um botão publica tudo

## Decisões do fluxo (tomadas em conversa anterior, trazidas por ele em 23/set/2026)
- Três caminhos a partir da mesma tela de categoria: um arquivo publica na hora, sem etapas; vários arquivos viram fila com "apply to all"; Steam Profile e Showcase Guide entram em etapas de partes. Etapas só onde a tarefa tem pedaços reais (wallpaper não tem). Nas etapas, as partes vêm antes da prévia: quem tem GIF pronto sobe o dele, quem não tem recebe um gerado. O lote fica fora das categorias multi-parte por enquanto. Revisto em 23/set/2026: no lançamento são dois caminhos (ver Regras do upload)
- Existe um protótipo em React (wondx-upload-flow.jsx, da conversa anterior) com os três caminhos: editar por post, tags em chips, categoria por linha (dá para misturar categorias no mesmo lote), desfazer por post depois de publicar e teto de 50 pontos por lote
- As duas questões que estavam em aberto foram resolvidas em 23/set/2026: o "desfazer" é uma espera real de 10 s antes de o post valer; e, quando a categoria de uma linha muda, a validação daquela linha é refeita na hora (vale quando o lote voltar)
- Acha (23/set/2026) que o upload vai virar um sistema complexo e que, como as settings, vai precisar de dados reais além do redesign

## Como a comunidade publica (resposta dele como membro da comunidade, 23/set/2026)
- Os criadores publicam em geral um trabalho novo por vez, raramente mais de 2–3 uploads de uma vez; o que mais se publica hoje são Steam profiles com PFP e banner, e entregam todos os formatos de showcase
- Já têm a prévia pronta (GIF montado); a prévia gerada pela Wondx vale como teste, para formar opinião
- O que faz desistir de publicar: o arquivo não sair com a qualidade que deveria, ou o post não sair como imaginavam — querem ver a prévia antes de publicar
- Praticamente todo artista usa a extensão Steam Artwork Hub ou o inspect element para subir as peças na Steam
- A Wondx ainda não tem dados de upload próprios que respondam essas perguntas; os dados vêm de fora (pesquisa externa e a comunidade)
- Decisão do [[nedddz]] já existente: envio em lote é feature paga, para assinantes e Official Creators
- Aprovou (23/set/2026) começar o upload pelas regras, antes do desenho
- O export do steam-crop (p1ayer4312.github.io/steam-crop) para Workshop dá cinco peças de 143 px de largura, com a altura da imagem enviada, numeradas 1_ a 5_

## Regras do upload — aprovadas em 23/set/2026, para o documento do [[nedddz]]
- Caminhos no lançamento: dois — post de um arquivo numa página só, e post Steam com peças. O lote fica para depois do lançamento. Revisto em 23/set/2026: o fluxo escolhe a categoria primeiro (ver o fim do arquivo); as regras de arquivo continuam valendo
- Arquivos por categoria: Wallpapers = 1 imagem (revisto em 24/set/2026: até 10 por post, ver "Várias imagens por post"), mínimo 1920×1080 na horizontal ou 1080×1920 na vertical; PFPs + Banners = PFP quadrada de no mínimo 512×512 e/ou banner de no mínimo 600×240 (PFP e banner animados: aviso no post, não bloqueio. Corrigido em 26/set/2026: os PFPs e banners não são feitos só para o Discord, mas para qualquer plataforma que aceite PFP e banner animados — o aviso não pode falar só do Discord com Nitro); Photography = mínimo de 4 MP; Digital Art = sem mínimo, e o post mostra as dimensões reais
- Steam Profiles: um modelo de showcase por post — Featured (1 peça de 630 px de largura), Artwork (506 + 100 px, mesma altura) ou Workshop (5 peças de 143 px, mesma altura) —, mais PFP e banner opcionais e os itens da Steam como links. Revisto em 24/set/2026: até 5 capturas do perfil (a primeira é a capa; não entram no download) e vários showcases na ordem do perfil, até dois de cada tipo, como a própria Steam permite; o post avisa o nível necessário (10 níveis por showcase) e o zip leva uma pasta por showcase
- Peça Steam: até 5 MB, em PNG, JPG ou GIF, na largura exata do espaço; fora disso o post não publica
- Download = o arquivo que o artista enviou, byte por byte: sem recompressão, sem conversão de cor, sem mexer em metadado. Marca d'água e versões menores só nas prévias
- Extras no download são opcionais (por exemplo, o original em qualidade total ou o GIF montado). O artista não envia zip: a Wondx monta o zip com os arquivos enviados um a um, cada um conferido pelo conteúdo e não pela extensão. Até 50 MB por arquivo; na Fase 1, extras só em PNG, JPG, GIF e WebP
- No download, as peças Steam saem com prefixo de ordem (1_ … 5_), no mesmo padrão do steam-crop, prontas para o Steam Artwork Hub e o inspect element
- Prévia antes de publicar: o card do feed e a página do post como vão ficar; no post Steam, o showcase montado com as peças enviadas nas larguras reais da Steam, e a lista do que vai no download com o tamanho e se cabe na Steam
- Capa do post Steam: a do criador por padrão; a gerada pela Wondx entra como teste, e dá para trocar
- Declarações: IA obrigatória e lembrada entre posts; Mature conforme a política; título e no mínimo 2 tags
- Publicar: moderação síncrona e o post vai ao ar direto, sem Undo (23/set/2026, substitui a espera de 10 s com Undo); depois disso, só apagando, com estorno dos pontos. A tela seguinte é a Published que o site já tem (check, "Your post is live.", card, link com Copy, compartilhar em X, Reddit e Pinterest, "View Post" e "Create another"), sem o rótulo "Published" no canto
- Rascunho: dá para salvar a qualquer momento depois do primeiro arquivo; aparece no Drafts do perfil, só para o dono
- Preço fica fora da Fase 1
- Controle de volume, sem o lote: cota diária por confiança para contas novas, no modelo do Adobe Stock; os números ficam para decidir com o [[nedddz]]
- Diretrizes: proibido aumentar a imagem artificialmente para passar no mínimo, como no Adobe Stock. Atualizado em 9/out/2026: escolheu que isso não entra como regra da Content Policy por agora; o artigo "File types and sizes" do help center só pede para não aumentar a imagem, sem dizer que é contra as regras
- Próximo passo aprovado: protótipo HTML do upload

## Fluxo de upload do site hoje (prints de 23/set/2026)
- wondx.net/upload é uma página só, "What are you uploading?", com nove tipos em três grupos: Artwork (Wallpaper, Digital Art, Photography), Profile assets (PFP, Banner, PFP + Banner) e Steam (Steam Artwork, Steam Profile, Steam Showcase Guide; os dois últimos abrem páginas próprias). A área de upload só ativa depois de escolher a categoria; a página ainda traz "Create a collection to save posts" e a linha de pontos ("Earns 12 pts per post")
- Steam Artwork só tem Featured (630 px) e Artwork Showcase (506 + 100), sem Workshop; aceita PNG/JPG ou MP4/WebM (máx. 8 s) até 50 MB por peça; título (50), descrição (200) e tags são opcionais, com o aviso "performance might drop"
- Steam Profile pede o screenshot do perfil (obrigatório, vira a capa do post), avatar, artwork opcional, quatro campos fixos de itens (Background, Avatar Border, Profile Theme, Showcase Guide) e quatro badges, todos como link, e diz "the more you add, the more you earn (14–26 pts)"
- Steam Showcase Guide: conecta a conta Steam (só quem está creditado no guia posta; o Steam ID fica privado), cola o link e "Fetch guide" puxa a capa da Steam (191×191); tem Collaborators (até 2; os pontos ficam com quem posta), o toggle "Made with AI" com a consequência ("Viewers can filter AI posts out of their feed") e a barra fixa "Save as draft" + "Publish"
- MP4 e WebM no upload não servem para nada hoje: eram só copy, talvez pensando na capa. Ficam fora das peças (23/set/2026)
- Acha (23/set/2026) o fluxo de upload atual, do site e do protótipo, confuso: texto e opções demais no Steam Profile, seleção de categorias e layout confusos. Quer um upload simples de entender para quem vem de outra plataforma, como o DeviantArt, mas eficiente e apoiado em dados reais, como os de abandono de formulário

## Modelo do upload (23/set/2026)
- Rejeitou o modelo "arquivo primeiro" (a tela abria com um campo só, sem chips de categoria, e a Wondx deduzia o tipo pelos arquivos): não gostou do estilo sem escolher a categoria antes. Pediu refazer o fluxo do zero, com a categoria escolhida primeiro e mais dados reais
- Antes disso tinha aprovado, no mesmo modelo, peças que a rejeição não alcançou: três campos obrigatórios (título, tags, toggle de IA) e o resto atrás de "+ Add" (descrição, capa própria, avatar, itens da Steam, extras, colaboradores, Mature); a prévia montada ao lado na mesma tela (card do feed, showcase na Steam, resumo do download), sem tela de conferência separada; "Publish" no fim com os 10 s de Undo; pontos, coleções e login na Steam fora da tela (o login só ao colar um link de guia); e a capa dos showcases gerada por padrão, com "Your own cover" como "+ Add". No fluxo categoria primeiro, a prévia virou uma só e o Mature virou toggle (ver abaixo)
- Gostou (23/set/2026) do fluxo refeito do zero com a categoria escolhida primeiro (uma tela de tipos em cards, depois um formulário curto do tipo) e seguiu com ele. Pediu três mudanças: o conteúdo sensível (Mature) vira um toggle igual ao de IA; só uma prévia, de como o post vai ficar na plataforma; e a frase do Made with AI mais curta
- Achou o upload bom por agora (23/set/2026) e mandou seguir

## Colaboradores
- Colaboradores no post e no feed não tinham sido planejados (23/set/2026); o site hoje só diz que dá para creditar até 2 pessoas, que aparecem sob o nome de quem postou, e que os pontos ficam com quem posta
- Decidiu (23/set/2026) que as curtidas de um post em colaboração somam no total de curtidas do perfil de todos os creditados

## PFP & Banner, capa e marca d'água (23/set/2026)
- O site hoje, no PFP + Banner com os dois arquivos, monta um card de perfil pronto para publicar (banner, PFP sobreposta, nome, @, badges, números, "Member Since" e a marca Wondx) com fundo Light, Dark ou Custom num seletor de cor completo, e tem o toggle "Wondx watermark"
- Aprovou: com os dois arquivos, o card de perfil é a capa padrão, trocável pela capa própria; a cor do card vem do banner, com o texto sobre uma camada escura (como o degradê do Discord, que escurece o perfil independente da cor); o toggle "Wondx watermark" volta, ligado por padrão e lembrado entre posts, fora do guia
- Quer manter o seletor de cor completo no card, como ferramenta para o artista trabalhar em cima; "From the banner" continua o padrão
- Aprovou (23/set/2026) o seletor de cor completo atrás do "+ Card color": "From the banner" como padrão, ou Custom com duas cores (Top e Bottom, como o tema de perfil do Discord), troca de ordem, quadrado de saturação/brilho, hue, hex e as oito cores prontas como atalho; a camada escura de 60% fica por cima de qualquer combinação
- Números no card (seguidores, curtidas, "Member Since") não voltam. O [[nedddz]] defendia seguidores e o nome da Wondx na imagem pelo SEO no Google Imagens; ele vai levar a proposta abaixo, e ela entra no documento completo do redesign de produto, não num documento separado (23/set/2026)
- Não gostou do desenho anterior do card (24/set/2026) e aprovou o card no modelo do perfil do Discord: um só degradê no card inteiro, com a primeira cor sólida atrás do banner; borda de 2 px com o degradê puro; o corpo inteiro sob uma camada preta uniforme de 60% (o banner fica sem ela); e o logo da Wondx (o vetor da página de Components) no lugar do texto "WONDX"
- Apontou (25/set/2026) que o anel da PFP, pintado numa cor fixa, não acompanhava o degradê sob os 60% quando a cor mudava; quer o anel mostrando o próprio fundo do card em cada altura, como no Discord
- Aprovou (25/set/2026) as versões do PFP & Banner como recomendado: só PFPs ou só banners, até 10 por post; os pares (cada versão com PFP e banner) ficam para depois do lançamento

## SEO do card de PFP + Banner — proposta para o documento completo do redesign (23/set/2026)
- O card mostra o nome da Wondx, o nome e o @ do criador e as badges; seguidores, curtidas e data de entrada ficam de fora
- A capa gerada pela Wondx sai com metadados IPTC, que o Google Imagens exibe ao lado da imagem: Creator = o artista, Credit Line = "via Wondx", aviso de copyright e o link do post como página de licença. Alt text, nome de arquivo e título da página descrevem a obra; o arquivo de download não é tocado
- Motivos registrados: o Google não usa o texto dentro da imagem para ranquear (usa alt text, conteúdo da página e nome do arquivo); número baixo gera desconfiança (teste do Taloon: sem os contadores, 11,9% mais cliques); o número indexado envelhece; e quem esconde a contagem nas settings teria o número exposto

## Várias imagens por post (24/set/2026)
- Levantou o caso de um post com mais de uma imagem, como um wallpaper, e aprovou montar no protótipo posts com várias imagens (até 10) em Wallpaper, Digital Art e Photography, com as versões juntas no mesmo post (desktop e celular, outras cores) e cada imagem passando pela regra da categoria. É diferente do envio em lote, que segue adiado para depois do lançamento

## Ajustes aprovados em 24/set/2026
- Aprovou: cada arquivo começa a subir assim que entra, com progresso na própria linha, e o Publish espera o envio terminar antes da checagem; o título vem do nome do arquivo quando o nome não é genérico, com aviso e editável; tags sugeridas pela categoria e pelo título; "Reuse details from your last post" copia tags, colaboradores (de novo como convite) e toggles, nunca o título
- Aprovou a linha "Missing a category? Suggest one ↗" abaixo dos cards de tipo, no lugar da sugestão do [[nedddz]] de caixas vazias esmaecendo com link para a caixa de sugestões
- Aprovou (25/set/2026) alinhar os tipos de item da Steam do upload aos nomes da própria Steam; pelo que ele sabe, "Avatar border" não existe na Steam

## Tags — decisão aprovada em 25/set/2026, para o documento do [[nedddz]]
- Referência que ele trouxe: o Instagram, que limitou as hashtags a 5 por post
- Dado real da Wondx: a maioria dos posts passa de 5 tags, e muitas delas só repetem a categoria e o tipo do post
- Tag que repete a categoria ou o tipo do post ("wallpaper", "pfp", "photography", "desktop", "phone", "showcase") não é aceita no upload nem na edição, e as sugestões nunca a oferecem; tag de resolução ("4k", "1080p", "hd") também sai, e a busca passa a achar a resolução pelo próprio arquivo. A lista de palavras bloqueadas sai do dado: as tags mais usadas em cada categoria que só repetem a categoria ou o tipo
- Limite de 5 tags por post para o que sobra (assunto, estilo, cor), com o mínimo de 2 que já existia e um contador "3/5" no campo, que mostra o limite antes de chegar nele
- Frase aprovada para quando a pessoa digita uma palavra bloqueada: "Already covered by the category."
- Posts existentes: uma limpeza única tira as tags repetidas de todos os posts (nada se perde, porque categoria, tipo e resolução continuam como campos); post que ainda passar de 5 depois da limpeza mantém as tags até o criador editar, e na edição ele escolhe as 5; nenhuma tag de verdade é apagada sem o criador saber
- Página de tag que duplica uma categoria redireciona (301) para a categoria, por exemplo /tag/wallpaper para /wallpapers
- Antes de fixar o número, o [[nedddz]] roda a consulta de tags por post antes e depois de tirar as palavras de categoria, tipo e resolução (mediana e porcentagem acima de 5); se, depois da limpeza, muitos posts legítimos ainda tiverem 6 a 8 tags, o limite começa em 8 e baixa depois
- Aprovou (26/set/2026) a frase para tag de resolução: "The file already says the resolution."

## Decisões de 1/out/2026 (respostas no FAQ do help center)
- Posts aceitam PNG, JPG e GIF; cada arquivo vai até 50 MB no grátis, 250 MB no Lite e 1 GB no Pro, e os arquivos extras seguem o mesmo limite do plano (substitui o teto fixo de 50 MB por arquivo dos extras)
- Não existe troca de arquivo depois de publicar: para adicionar, remover ou trocar uma imagem, é preciso apagar o post e subir de novo
- Quer (21/out/2026) a escolha de categoria do upload numa página só, com todas as categorias (o site no ar separou o Steam num segundo passo), e vão entrar mais categorias de Steam

## Página única de tipos (21/out/2026)
- O Steam tem 5 categorias no upload: Full Steam Profile, Artwork Showcase, Featured Artwork Showcase, Guide Showcase e Workshop Showcase ("sendo 3 delas showcases", nas palavras dele)
- Na página única de tipos, o grupo Images vem primeiro e o Steam depois
- Corrigiu (22/out/2026): as peças do Workshop têm 122 px de largura cada (não 143), e o mínimo do Wallpaper é 1280×720 (ou 720×1280), não 1920×1080 — valem sobre as regras de 23/set acima

## Fim do upload sem a tela Published (21/out/2026)
- Aprovou trocar a tela Published por voltar ao feed da home: o Publish fica em "Publishing…" no formulário até a checagem passar; no feed, o post novo aparece primeiro (só nessa visita) e um cartão no canto inferior direito traz "Your post is live.", o título, "+{n} contribution points", "Copy link" (vira "Copied" por 2 s), X/Reddit/Pinterest, "View post" e "Create another" (abre o upload com a mesma categoria); o cartão só fecha no X, no Esc ou ao ir para outra página; no sino fica "Your post “{title}” is live."; a Published antiga ficou marcada como substituída no Figma (15.11 e 15.12)
