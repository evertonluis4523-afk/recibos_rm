# Controle de Recibos — RM Estruturas Pré-Fabricadas

App de página única (PWA) para lançar e imprimir recibos de **pagamento** e **adiantamento**
dos funcionários. Sai **2 recibos por folha A4**, com a logo acima da palavra RECIBO.

## Recursos
- Cadastro de funcionários (CPF/CNPJ, situação Ativo/Afastado) — os 31 já vêm cadastrados.
- Lançamento por tipo (pagamento/adiantamento), mês de referência e data de emissão.
- Marcar/desmarcar quem entra na impressão (afastado já vem desmarcado).
- Valores lembrados por funcionário e por tipo.
- Impressão 2 por folha A4 com linha de recorte.
- Dados salvos no próprio navegador (localStorage) + exportar/restaurar backup.
- Instalável como app (PWA) e funciona offline depois de aberto.

## Publicar no GitHub Pages
1. Crie um repositório (ex.: `recibos-rm`) e suba **todos os arquivos desta pasta** na raiz.
2. No GitHub: **Settings → Pages → Source: Deploy from a branch → Branch: `main` / `/root`**.
3. Aguarde ~1 minuto. O endereço fica `https://SEU-USUARIO.github.io/recibos-rm/`.

## Atualizar depois de publicado
Ao trocar o `index.html`, edite o `service-worker.js` e suba a versão do cache
(`recibos-rm-v1` → `recibos-rm-v2`) para os dispositivos pegarem a nova versão.

## Arquivos
- `index.html` — o app.
- `manifest.json` — dados do PWA.
- `service-worker.js` — cache/offline.
- `icon-192.png`, `icon-512.png`, `apple-touch-icon.png`, `favicon.png` — ícones.
- `.nojekyll` — desliga o processamento Jekyll do GitHub Pages.
