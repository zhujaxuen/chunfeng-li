# chunfeng-li — diário de mandarim

## Arquivos
- `index.html` — o diário público, lê `entries.json` e mostra as entradas.
- `admin.html` — painel pra adicionar/excluir entradas direto pelo navegador, sem editar código.
- `entries.json` — os dados (2 entradas de exemplo já inclusas).

## Como colocar no ar

1. Crie o repositório no GitHub (ex: `chunfeng-li`), público ou privado.
2. Suba esses 3 arquivos pra raiz do repositório (pode arrastar pela interface do GitHub mesmo, ou via git).
3. Vá em **Settings → Pages**, escolha a branch (geralmente `main`) e pasta `/ (root)`. Salve.
4. Em alguns minutos o site estará em `https://zhujaxuen.github.io/chunfeng-li/`.

## Como gerar o token de acesso

Pra `admin.html` conseguir commitar por você, precisa de um Personal Access Token:

1. GitHub → clique na sua foto → **Settings** → **Developer settings** → **Personal access tokens** → **Fine-grained tokens** → **Generate new token**.
2. Em **Repository access**, escolha **Only select repositories** e selecione o `chunfeng-li`.
3. Em **Permissions → Repository permissions**, dê acesso de **Read and write** em **Contents**.
4. Gere o token e copie (ele só aparece uma vez).

## Como usar o painel

1. Abra `https://zhujaxuen.github.io/chunfeng-li/admin.html`.
2. Preencha usuário, repositório, branch e cole o token.
3. Preencha a entrada (data, nível HSK, título, caractere do dia opcional, conteúdo, vocabulário).
4. Clique em **Salvar entrada** — isso lê o `entries.json` atual, adiciona a nova entrada, e faz um commit direto no repositório.
5. Recarregue `index.html` pra ver a entrada nova.

O token fica salvo só no `localStorage` do seu navegador (nunca é escrito em nenhum arquivo do repo). Guarde `admin.html` só pra você — qualquer pessoa que tenha a URL *e* o seu token conseguiria editar o diário, então não compartilhe o token com ninguém e evite linkar `admin.html` a partir do site público.

## Personalização rápida
- Trocar a paleta de cores: edite as variáveis `--paper`, `--ink`, `--seal`, `--brass` no topo do `<style>` de `index.html` e `admin.html`.
- Adicionar mais campos por entrada (ex: nota de gramática): edite o objeto `entry` em `admin.html` e o template de renderização em `index.html`.
