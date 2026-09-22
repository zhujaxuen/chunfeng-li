# 春风里 chūnfēng lǐ

> *"na brisa da primavera"* — 花儿开在春风里, a florzinha desabrocha na brisa da primavera.

Um diário público de aprendizado de mandarim, começando pelo HSK1. Sem app, sem plataforma de terceiros — só um site estático que evolui junto com o estudo, uma entrada por vez.

**🔗 [zhujaxuen.github.io/chunfeng-li](https://zhujaxuen.github.io/chunfeng-li/)**

---

## A ideia

Aprender um idioma é um processo lento e não-linear — muito mais parecido com uma planta crescendo do que com uma barra de progresso enchendo. Esse projeto é uma tentativa de registrar esse processo honestamente: o que foi estudado, quando, e como as palavras aparecem em uso real, não só como itens soltos numa lista.

Cada entrada do diário registra um dia de estudo — nível do HSK, um caractere em destaque (exibido dentro do 田字格, a grade tradicional de prática de caligrafia), e o vocabulário aprendido naquele dia, cada palavra acompanhada de uma frase de exemplo com contexto e tradução.

## Como funciona

O site inteiro é HTML/CSS/JS puro, sem build step, sem framework, hospedado de graça no GitHub Pages. As entradas moram num único `entries.json`, e existe um painel (`admin.html`) que escreve nesse arquivo diretamente pela API do GitHub — ou seja, dá pra adicionar uma entrada nova só pelo navegador, do celular inclusive, sem precisar abrir editor de código ou dar commit manual.

```
zhujaxuen/chunfeng-li
├── index.html      diário público — lê entries.json e renderiza as entradas
├── admin.html       painel de escrita — form → commit direto no repo via GitHub API
├── entries.json      os dados: cada entrada com data, nível, texto e vocabulário
└── README.md
```

## Estrutura de uma entrada

```json
{
  "date": "2026-09-21",
  "level": "HSK1",
  "title": "Cumprimentos e família",
  "hanzi": "家",
  "pinyin": "jiā",
  "content": "o que foi estudado naquele dia...",
  "vocab": [
    { "word": "谢谢", "pinyin": "xièxie", "phrase": "谢谢你！— Obrigado(a)!" }
  ]
}
```

## Rodando/configurando o seu próprio

<details>
<summary>Passo a passo pra clonar esse formato pro seu próprio diário</summary>

1. Faça um fork ou copie os 3 arquivos (`index.html`, `admin.html`, `entries.json`) pra um repositório novo.
2. Em **Settings → Pages**, defina a branch `main` e pasta `/ (root)`. O site sobe em `https://SEU-USUARIO.github.io/SEU-REPO/`.
3. Gere um **Personal Access Token** (fine-grained) em GitHub → Settings → Developer settings, com acesso **Read and write** em **Contents**, restrito ao seu repositório.
4. Abra `admin.html`, preencha usuário/repositório/branch/token (fica salvo só no seu navegador) e comece a escrever.

</details>

## Uma nota sobre o token

`admin.html` guarda o token só no `localStorage` do seu navegador — ele nunca é commitado nem enviado a nada além da API do GitHub. Ainda assim, evite linkar essa página a partir do site público e não compartilhe o token com ninguém: quem tiver a URL do admin *e* o token consegue editar o repositório.

---

*四季常在，学无止境 — as estações sempre voltam, o aprendizado nunca termina.*
