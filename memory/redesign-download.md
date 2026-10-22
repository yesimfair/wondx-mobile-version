---
name: "redesign-download"
description: "Download na Wondx — Download all por aparelho na página do post (26/set, com os números), links externos e leakage"
---

## Fatos do produto (20/set/2026)
- Download é ILIMITADO para todo mundo, pagante ou não — como qualquer plataforma de discovery de arte. Isso remove do fluxo: cota, estado de esgotado e o gatilho de Pro no download
- Não há asset pago na Fase 1; só na Fase 2
- O botão é sempre "Download", mas **alguns posts redirecionam** para guias de showcase da Steam e para sites próprios dos criadores
- Existe arquivo hospedado na Wondx também — não é só link externo
- O card do feed NÃO avisa hoje qual é o tipo do post
- Ele levantou por conta própria a preocupação: alguém publicar algo grátis só para redirecionar e capturar tráfego

## Política a decidir com o [[nedddz]] — decisão de produto
- Isso tem nome: leakage de marketplace / desintermediação. A regra da Etsy que resolve o caso: um anúncio precisa OFERECER o item, e é proibido criar anúncio para compartilhar código de indicação ou atividade similar que não ofereça item à venda. A Etsy também proíbe direcionar transações para fora, incluindo trocar URLs externas para esse fim
- Recomendação minha, ainda não decidida: (1) um post precisa entregar o asset NA Wondx; (2) link externo é ação SECUNDÁRIA, nunca o botão primário; (3) guia de Steam é um TIPO de post próprio, com rótulo próprio e fora da contagem de ativação; (4) paridade de preço na Fase 2 — asset grátis na Wondx não pode ser pago no destino; (5) quem induz leakage demais CAI na descoberta, em vez de ser banido (o artigo de Hagiu e Wright sobre leakage lista "esconder vendedores que induzem leakage demais" entre as estratégias)
- Independente da política: registrar a URL de destino e tratar TROCA de destino como nova submissão, porque moderação não alcança o que está atrás do link e o destino pode ser trocado depois da aprovação
- Rótulo por tipo, não ícone: o design system do governo americano testou ícone de link externo contra selo "Exit" e os usuários não entenderam nem um nem outro de forma consistente — o que funciona é o destino estar no TEXTO. Então "Download" para arquivo hospedado, "View on Steam" e "Get on [domínio]" para externo, com rel="noreferrer"
- (25/set/2026) Os rótulos "View on Steam" e "Get on [site]" já são decisão tomada e estão no ar na plataforma — não tratar como pendente

## Consequências que não são de tela
- A licença da Wondx não cobre arquivo hospedado fora — os termos do destino é que governam. A página de License precisa dizer quais downloads ela cobre
- O evento de ativação (baixar o primeiro asset) não é contável quando o clique sai do site

## Download na página do post — decisão de 26/set/2026, para o documento do [[nedddz]]
- Post com mais de uma imagem: o botão principal baixa a imagem que está no palco, e "Download all" é um botão Outlined AO LADO dele (o mesmo par do Download ZIP + Recreate no post de Steam), não um link embaixo. Medido com a Geist a 16 px: "Download PNG" ocupa 178 px e "Download all" 130 px, dentro das metades de 196 px da trilha de 400 px
- "Download all" muda por aparelho: no computador baixa o ZIP; no celular abre a folha de compartilhar do sistema com todas as imagens (Web Share API: navigator.canShare({ files }) e navigator.share({ files })), e "Salvar N imagens" põe tudo nas Fotos, sem ZIP e sem o app Arquivos; sem suporte, cai no ZIP. Os extras (PSD, fonte) ficam só no ZIP do computador. O rótulo é "Download all" nos dois casos
- A galeria abre na versão feita para a tela de quem visita (no celular, a de celular; no computador, a de desktop). O servidor escolhe o primeiro slide pelo aparelho, para a imagem não trocar depois de carregar
- Dados que embasaram a decisão: em junho de 2026 o celular teve 51,45% das visitas da web no mundo e o desktop 47,15% (StatCounter); a Wondx não tem dado próprio por aparelho, e ele acha provável que a maioria venha do celular. Nos posts do protótipo, "tudo" pesa de 3,1 a 7 vezes a versão que a pessoa quer: desktop + celular 12,1 MB contra 3,9 MB da versão de celular; 4 cores 43,6 MB contra 11,4 MB; com extras 61,3 MB contra 8,8 MB. No iPhone, o Safari aceita só o primeiro de vários downloads e manda os arquivos para o Arquivos/iCloud Drive, e um papel de parede precisa estar nas Fotos; vendedores de pacotes de wallpaper no Gumroad mandam passo a passo para descompactar no celular, e no Android às vezes é preciso instalar um app para descompactar
- Onde os arquivos são usados juntos, o ZIP é o botão principal: posts de Steam ("Download ZIP", com o ZIP só das peças que o criador subiu) e o card do PFP & Banner (os 2 arquivos)
- Post de uma imagem com extras: o botão vira "Download ZIP", com a linha "ZIP · PNG + 2 extras". Post no site do criador: "Get on [site]" abre em aba nova, sem linha de arquivo, e as estatísticas mostram Views e Saves, porque o download não é contável quando o clique sai do site
