# Controle de Recibos — RM Estruturas Pré-Fabricadas

App de página única (PWA) para lançar e imprimir recibos de **pagamento** e
**adiantamento** dos funcionários. Sai **2 recibos por folha A4**, com a logo
acima da palavra RECIBO. Sincroniza na nuvem (Firebase) igual ao Contas a Pagar.

## Sincronização (Firebase)
- Usa o **mesmo projeto** do Contas a Pagar (`rm-contas`), gravando num nó
  separado chamado **`recibos`** — não mistura com as contas a pagar.
- Login por **e-mail e senha**. Crie/edite os usuários no console do Firebase em
  **Authentication → Users** (os mesmos usuários do Contas a Pagar já servem).
- A pílula no topo mostra **“sincronizado”** quando está na nuvem.
- Para usar **só neste aparelho** (sem nuvem), abra o `index.html`, ache o bloco
  `CONFIG` e deixe `apiKey` em branco — aí o login vira local (admin / rm1234).

## Recursos
- 31 funcionários já cadastrados (CPF/CNPJ, Ativo/Afastado).
- Lançamento por tipo, mês de referência e data de emissão.
- Marcar/desmarcar quem entra na impressão (afastado já vem desmarcado).
- Valores lembrados por funcionário e por tipo, sincronizados.
- Impressão 2 por folha A4 com linha de recorte.
- Exportar/restaurar backup em `.json`.
- Instalável como app (PWA).

## Publicar no GitHub Pages
1. Crie um repositório (ex.: `recibos-rm`) e suba **todos os arquivos** na raiz.
2. **Settings → Pages → Deploy from a branch → main / root**.
3. Em ~1 min fica em `https://SEU-USUARIO.github.io/recibos-rm/`.
4. No Firebase, em **Authentication → Settings → Authorized domains**, confirme
   que o domínio `SEU-USUARIO.github.io` está liberado (o github.io costuma já
   estar; se der erro de domínio no login, adicione lá).

## Atualizar depois de publicado
Ao trocar o `index.html`, suba a versão do cache no `service-worker.js`
(`recibos-rm-v2` → `v3`) para os aparelhos pegarem a nova versão.
