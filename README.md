# LiDire MVP 4.8

Atualização da versão 4.4 com suporte funcional a:
- idioma Português (Brasil) e English;
- aparência somente Claro ou Escuro;
- preferência persistida em localStorage;
- versão clara preservando a paleta oficial da LiDire (roxo/ciano);
- manutenção das demais funcionalidades da 4.4.

IA permanece fora desta versão e começa na 4.5.


## Atualização 4.5 — Família, convite e acabamento visual

A versão 4.5 mantém a identidade visual oficial da LiDire e acrescenta:
- refinamento do modo claro, com contraste consistente em campos, cards, textos e navegação;
- permissões familiares reorganizadas em linhas com checkbox + ícone + nome do recurso;
- prévia visual do convite familiar usando exclusivamente `logo-lidire-oficial.png`;
- fluxo separado para convite familiar e link público de divulgação;
- tela de convite acessível por `?convite=TOKEN`, sem expor dados da pessoa que enviou;
- ações de copiar o convite e compartilhar pelo WhatsApp;
- metadados Open Graph para compartilhamento da LiDire;
- proteção para que a tradução da interface não altere valores digitados pelo usuário.

O convite desta versão é uma camada de interface/fluxo do protótipo. A concessão real de acesso e a associação do membro familiar ao D1 continuam dependendo da etapa de backend correspondente.


## Versão 4.6 — compartilhamento social robusto
- Prévia social processada pelo Cloudflare Worker na borda.
- Links `?convite=` usam título, descrição e banner específicos de convite familiar.
- Links públicos usam a prévia institucional.
- Rotas diretas para as imagens sociais com `Content-Type: image/png` e cache público controlado.
- Metadados Open Graph/Twitter usam URLs absolutas do domínio atual.
- Arquivo `logo-lidire-oficial.png` permanece inalterado.


## LiDire MVP 4.7 — compartilhamento social

A 4.7 separa as páginas de compartilhamento das telas da SPA.
- `/convite?token=...` é uma página HTML dedicada ao crawler, com `og:image` absoluto e banner de convite.
- `/divulgacao` é a página pública de compartilhamento institucional.
- As imagens PNG são servidas por rotas explícitas do Worker com `Content-Type: image/png`.
- O convite copiado pelo aplicativo usa `/convite?token=...` e o botão da página de compartilhamento leva para `/?convite=...`.
- O nome do Worker no `wrangler.toml` foi atualizado para `mvp-versao-4-7`.
## LiDire MVP 4.8 — convite visual e idioma

A 4.8 corrige o fluxo visual da página de convite familiar:
- O banner `lidire-invite-preview.png` passa a aparecer em tamanho grande e responsivo dentro da página aberta pelo convidado.
- O banner mantém proporção 1200×630 e a identidade visual oficial.
- A página de convite usa textos completos e consistentes com o idioma selecionado, sem combinar trechos de Português e English na mesma interface.
- O `logo-lidire-oficial.png` continua preservado sem alteração.
- O compartilhamento social da 4.7 permanece separado e funcional.

