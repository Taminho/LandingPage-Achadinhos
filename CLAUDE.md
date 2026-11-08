# CLAUDE.md — Achadinhos da Rebeca (link na bio)

Página estática publicada em https://www.achadinhosdarebeca.com.br via GitHub Pages. É o **link na bio do Instagram** da Rebeca: quase todo o tráfego chega de lá.

Detalhes de edição da página (botões, cupons, logos, medição de cliques, `CNAME`) estão no `README.md` — ler antes de mexer no `index.html`.

- **Origem do tráfego:** a página lê `?src=` ou `?utm_source=` do link (ex.: `?src=ig_bio`). Manter esse parâmetro nos links publicados no Instagram, senão a origem do clique se perde.
- **Medição:** `GA4_ID` e `PIXEL_ID` no fim do `index.html`. Vazio = desligado.

## Conexões de Instagram

Duas conexões de Instagram no ambiente Claude, que devem ser usadas juntas.

### 1. Supermetrics (conector MCP) — métricas, análises e relatórios

- `IGI` — insights da conta própria: posts, Reels, Stories, alcance, seguidores, demografia.
- `IGPD2` — dados públicos de perfis e concorrentes, hashtags.
- `FA` — performance de anúncios Meta (Facebook e Instagram). Dimensão `publisher_platform` para isolar as colocações do Instagram.
- **Sempre** chamar `accounts_discovery` antes de qualquer consulta, para obter o ID da conta.
- Usar `field_discovery` para descobrir field IDs e report types. Nunca inventar field ID nem setting key, nunca responder métrica de memória.

### 2. Plugin `instagram` do Claude Code — relacionamento com o público

- Ler e responder comentários e mensagens diretas (DMs) pela Instagram Graph API oficial.
- Configuração: `/instagram:configure`. Controle de acesso: `/instagram:access`.
- Playbook para mensagens de entrada: skill `instagram:qualification`.

### Como trabalhar com as duas

1. Para entender um resultado ou uma tendência, começar pelo Supermetrics.
2. Para responder comentários ou DMs, usar o plugin `instagram`.
3. Quando uma análise indicar um tipo de conteúdo que funciona, sugerir a ação de resposta ou de engajamento correspondente.
4. **Nunca responder comentário nem enviar DM sem aprovação explícita do usuário**, caso a caso. Apresentar o rascunho e esperar o "ok".
5. Se a conta ou a conexão necessária não estiver disponível, dizer qual falta em vez de improvisar com outra fonte. Em particular: o Supermetrics também oferece `manage_social_media` (comentários em `IGI`); relacionamento é responsabilidade do plugin `instagram`, e essa alternativa só com autorização explícita.

### Ligação com esta página

O que o Instagram manda para cá só aparece junto se o link carregar `?src=`. Ao cruzar desempenho de post (Supermetrics `IGI`) com cliques na página (GA4/Pixel), conferir primeiro se o link daquele post estava marcado.
