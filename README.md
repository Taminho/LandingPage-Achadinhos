# Rebeca Costa Sancho — Achadinhos (link na bio)

Página publicada em https://www.achadinhosdarebeca.com.br via GitHub Pages.

- `index.html`: a página. Cada botão é um `<a ... data-id="...">`: `grupo-vip`, `shopee`, `amazon`, `mercadolivre`, `shein`, `colaedecora`, `tiktok`, `contato`. Para trocar um link, edite o `href` do botão.
- Para esconder um botão, acrescente o atributo `data-pendente` no link.
- Botões com `data-cupom="CODIGO"` copiam o cupom ao tocar.
- `banner-preto.jpg`: foto do topo. `rebeca-og.jpg`: imagem da prévia quando o link é compartilhado.
- `logos/`: logos dos botões (enviadas pelo Tamer).
- Medição de cliques: no fim do `index.html`, preencha `GA4_ID` (Google Analytics 4) e/ou `PIXEL_ID` (Meta Pixel). Vazio = desligado. Eventos: `clique_botao` (GA4); `Lead` no Grupo VIP, `Contact` no contato e `CliqueLoja` nas lojas (Pixel). A origem vem de `?src=` ou `?utm_source=` no link (ex.: `?src=ig_bio`).
- `CNAME`: domínio personalizado. Não apagar.
