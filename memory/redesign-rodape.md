---
name: "redesign-rodape"
description: "Rodapé da Wondx no redesign — painel na sidebar (referência Pinterest/Unsplash), NCII público sem login, e a regra de âncoras para crawler"
---

- Decidiu tirar o rodapé do fim da página e colocá-lo num painel aberto por botão na sidebar, com Unsplash e Pinterest como referência, porque a rolagem infinita deixa o rodapé inalcançável
- Argumenta que isso não é esconder navegação: categorias, following, upload e busca seguem visíveis, e o que vai para o painel é utilitário
- Prefere o enquadramento do Pinterest ("Settings & Support", gatilho rotulado) ao hambúrguer pelado da Unsplash
- O formulário público de NCII da Wondx já existe e NÃO exige login — feito assim de propósito, porque a vítima provavelmente nem usa a plataforma
- Pediu para guardar e levar ao documento do Nedddz: os links do painel precisam ser âncoras <a href> reais no HTML inicial, escondidas por CSS, nunca inseridas no clique — senão /help/ncii e /help/dmca nascem órfãs, já que a Wondx não tem grafo de links de entrada como Pinterest e Unsplash têm
- Considera essa parte de crawler fora da área dele hoje — é para ter em mente, não para ele executar

## Decisão final de colocação (19/set/2026)
- O painel do rodapé fica na SIDEBAR, nos dois estados (logado e deslogado) — não na topbar. Motivo: Pinterest e Unsplash põem na sidebar porque têm sidebar; VGen e Mobbin põem na topbar porque não têm. A Wondx tem sidebar de 64 nos dois estados.
- Topbar deslogada: "Log in" em texto + "Sign up" preenchido, e nada além disso — sem botão de menu ali, para o log in não sumir como sumiu no VGen
- Topbar logada: o menu do avatar cuida só de conta; o rodapé não se repete lá
- Sem ícone de pessoa no estado deslogado (o slot do avatar prometeria uma conta que não existe)
- Não precisa de link "NCII" no menu — a cadeia menu → Help → página de NCII é a forma que o próprio TIDA nomeia; Discord faz assim (artigo no support center + formulário público em discord.com/report). O que importa é a redação da entrada no índice de ajuda, em linguagem de vítima, e a página ser indexável

## Forma e gatilho (19/set/2026)
- Escolheu a direção B do painel: mini-rodapé de duas colunas (Support | Wondx) com faixa jurídica no pé, 440 de largura — descartou a direção A (lista com ícones, no estilo do menu de conta)
- O gatilho na sidebar são TRÊS PONTOS, decidido contra a recomendação de ponto de interrogação
- A sidebar é a mesma nos dois estados, logado e deslogado — não se mexe nela; o documento de contexto que diz que ela perde os itens com conta está errado

## Help center e páginas (20/set/2026)
- DECIDIDO: help center PRÓPRIO, não serviço externo tipo Zendesk. As páginas de DMCA e NCII ficam no domínio da Wondx, então a conta de SEO feita aqui continua valendo
- Já existem os FORMULÁRIOS de terms, privacy e copyright — o que NÃO existe são as páginas explicando cada um
- Não existem: a página de License nem a tela inicial do help center
- Achou o primeiro protótipo do help center sem personalidade e escolheu (1/out/2026) o topo A: arte da comunidade em destaque com crédito do criador, em vez do topo B (só a marca); depois pediu que essa arte seja um BANNER na faixa inteira, e não uma obra ao lado do título
- Aprovou (1/out/2026) a tela inicial do help center, o modelo de artigo e as frases propostas para eles
- A Wondx atende os usuários por ticket no Discord (confirmado em 1/out/2026) — é um dos canais de contato do help center
- Revisão aprovada depois (1/out/2026): no banner, "How can we help?" e a busca ficam no CENTRO, com a arte escurecida como nos primeiros protótipos (substitui o esmaecido lateral e a obra ao lado); cards de tema alinhados, com título e descrição de uma linha e a mesma altura (resolvido pela copy); "Still need help?" numa linha só, sem bloco grande; artigos mais limpos (In short como abertura, no máximo um quadro, sem coluna lateral, Related articles no fim); "Tip" e "In short" em sunken, não em accent; "Was this article helpful?" com ícone + texto, não emoji
- O help center está no Figma como Bloco 22 (22.1 a 22.6); ele mesmo editou a 22.1 (trocou a arte do banner) e pediu que Claude tire capturas e procure os erros antes de entregar

## Links legais e celular (15/out/2026)
- Aprovou (15/out/2026) as recomendações do brief de navegação no celular e dos links legais ("Cancel contracts here" e "Withdraw from contract"): faixa fixa com os dois links só para quem tem contrato (plano ativo ou compra nos últimos 14 dias), os dois links no topo do painel, barra embaixo no celular com o More abrindo o painel como folha, e consulta ao advogado da Wondx, pelo [[nedddz]], antes do lançamento
- Decidiu (21/out/2026) não seguir por agora com o protótipo da faixa, da barra do celular e da nova ordem do painel
