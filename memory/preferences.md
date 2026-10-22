---
name: "preferences"
description: "How the user wants Claude to work in this Project"
---

- A partir de 20/set/2026, e daqui em diante: quer que Claude faça o design primeiro em HTML, para ele ir revisando aos poucos, e só depois desenhe no Figma
- Ao montar no Figma, tudo segue o grid do kit — espaçamento, avatar, botão, frame, chip em múltiplos de 4 (sem 14, 10, 6 e afins). Correção que ele teve que fazer depois de ver o erro repetido em vários frames
- Quer que eu use como base a construção dos elementos que ele refaz no Figma, principalmente como o elemento é montado e o auto layout
- Ao montar no Figma, NÃO usar linha ou frame espaçador para afastar elementos que ficam distantes um do outro ou nos cantos (exemplos que ele deu: as tags e o botão Relevant; People e o "See all"). Correção que ele teve que fazer depois de ver o hábito repetido
- Organização dos frames no Figma: páginas principais lado a lado, uma coluna por página; variações da mesma página vão EMBAIXO da página principal, na mesma coluna — é como ele já organiza as outras páginas
- Estados, modais e variações de informação (ex.: as variações da trilha do post) vão DENTRO de um frame (board) de fundo branco, como os outros boards — nunca soltos ou separados no canvas (26/set/2026). Claude deixa o board embaixo da página principal quando criar; ele mesmo move para a seção "Modals & Extras" depois
- Fechamento da moderação (22/set/2026): toda vez que uma fase termina, as decisões dela entram no documento do sistema (MODERATION-SYSTEM.md, o documento para o [[nedddz]]) antes de seguir para a próxima fase
- Correção de método no Figma (22/set/2026): usar os componentes e as peças que já estão em uso nas outras páginas — clonar o sort, o segmentado, os menus e os modais das telas existentes — e só desenhar do zero o que não existe em lugar nenhum. O arquivo tem só dois componentes de verdade (Button e Category tabs), então a consistência entre telas vem de copiar as peças prontas, não de redesenhá-las
- Ícones no Figma (22/set/2026): não usar componentes de ícone criados pelo Claude; usar os ícones direto da biblioteca do Phosphor
- A partir de 25/set/2026, ao construir UI: embasar em NN/g e Baymard para otimizar, sempre trazer números e perguntar se faz sentido num caso real, pensando nas variáveis que distraem ou confundem o usuário
- Não quer ser consultado sobre questões técnicas que Claude consegue responder sozinho — exemplo que ele deu (25/set/2026): a exceção do alt vazio em imagens decorativas dentro de links, por acessibilidade
- Pergunta de caso real (26/set/2026): a Wondx não tem esses dados de uso; em vez de perguntar a ele, Claude pesquisa em fontes externas (outros sites) — por exemplo, quantas pessoas baixam ZIP e o que acham disso (pesa mais, é ruim, é complicado)
- Documento para o [[nedddz]] (26/set/2026): toda decisão entra com dados reais e números — os dados que a embasaram e as medidas que ela usa — em todo o documento
- Quer que os erros bobos do Figma (bordas e sombras cortadas, cor sem token, texto solto fora de frame) não se repitam em chats novos. Para isso pediu (26/set/2026) a skill wondx-figma-qa e depois decidiu transformá-la na skill "wondx" — a definitiva para desenhar qualquer página da Wondx sem ter um template em mente, do protótipo ao Figma (regras, padrões, catálogo de peças e os scripts de auditoria), que absorve a wondx-figma-qa. Em 1/out/2026 aprovou enxugar a skill para guardar só processo: as decisões por bloco, o diário de erros e a copy aprovada saíram dela
- Quer que Claude faça só o que ele pediu, sem trazer o que ele não disse: em 1/out/2026 mandou desfazer uma rodada inteira no Figma porque Claude quebrou coisas e mudou o que não tinha sido pedido
- Escopo do Figma (26/set/2026): o que importa é a página Final Screens — correções de token e varreduras só lá, sem trabalho extra nas outras páginas do arquivo
- Copy de interface da Wondx sem travessão (em dash): apontou os travessões da página de planos como problema a corrigir antes de seguir (27/set/2026)
- Não precisa receber documentos de copy: a copy aprovada fica na memória. O único documento que ele quer receber é a skill wondx, atualizada aos poucos quando for preciso, para os erros não se repetirem (30/set/2026); pediu (1/out/2026) que, daqui em diante, quando ela mudar, venha num arquivo separado, pronto para ele atualizar a skill
- Para os protótipos HTML saírem com menos erros, escolheu (30/set/2026) começar pela verificação automática deles (a outra opção era um Design System da Wondx para a tela Design; o Claude Design foi considerado na conversa)
- Pediu (1/out/2026) que, toda vez que Claude implementar algo no Figma, mande uma captura (screenshot) do frame aqui no chat para ele ver: trabalha pelo celular e é mais fácil assim do que abrir o Figma
- E-mails novos no Resend (3/out/2026): seguir o modelo dos templates que já existem, duplicando um template parecido e trocando só o conteúdo, em vez de montar do zero (a versão feita do zero saiu com os cantos de cima quadrados)
