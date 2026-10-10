# devlog.play() — Blog de Jogos Digitais

Blog estático para registrar as atividades da disciplina de Jogos Digitais (ADS — UFC), hospedado no GitHub Pages.

## Estrutura

- `index.html` — site público (somente leitura). Carrega o conteúdo de `posts.json`.
- `posts.json` — todo o conteúdo do blog: perfil e atividades.
- `admin.html` — editor local. **Não deve ser usado como página do site publicado** — é só uma ferramenta para gerar o `posts.json` atualizado. Abra sempre pelo seu computador, nunca dependa dele estar público (embora não tenha problema em deixá-lo no repositório, já que ele não grava nada sozinho).

## Como publicar pela primeira vez

1. Crie um repositório novo no GitHub (pode ser público), por exemplo `devlog-jogos-digitais`.
2. Envie os arquivos `index.html`, `posts.json` e `admin.html` para a raiz do repositório.
3. Vá em **Settings → Pages**.
4. Em "Source", selecione a branch `main` e a pasta `/ (root)`. Salve.
5. Aguarde 1–2 minutos. O GitHub mostrará o link do site, algo como `https://SEU-USUARIO.github.io/devlog-jogos-digitais/`.

## Postando uma atividade em vídeo

O blog não hospeda arquivos de vídeo (seriam pesados demais para hospedagem estática). Em vez disso:

1. Suba o vídeo no YouTube (pode marcar como "não listado" — só quem tem o link acessa) ou no Vimeo.
2. No `admin.html`, ao criar/editar a atividade, cole o link do vídeo no campo **"Vídeo (link do YouTube ou Vimeo)"**.
3. O player aparece incorporado automaticamente na página da atividade, e um selo "vídeo" aparece no card.

## Como publicar uma nova atividade

1. Abra `admin.html` no seu computador (duplo clique, ou sirva localmente — veja abaixo).
2. Se o arquivo `posts.json` estiver na mesma pasta, o editor carrega os dados automaticamente.
3. Clique em **"Nova atividade"**, preencha e salve.
4. Clique em **"exportar posts.json"** — isso baixa o arquivo atualizado.
5. Substitua o `posts.json` da pasta do repositório pelo arquivo baixado.
6. Envie a alteração ao GitHub (`git add`, `git commit`, `git push`, ou pelo próprio site do GitHub em "Add file → Upload files").
7. Em cerca de 1 minuto o site publicado é atualizado automaticamente.

## Observação sobre abrir os arquivos localmente

Alguns navegadores bloqueiam o carregamento de `posts.json` quando o arquivo `index.html` é aberto direto por duplo clique (protocolo `file://`). Para testar localmente antes de publicar, rode um servidor simples na pasta do projeto:

```bash
python3 -m http.server 8000
```

E acesse `http://localhost:8000` no navegador.

## Sobre acesso e edição

Como o site é estático, **qualquer pessoa que acessar o link só consegue ler** — não existem botões de criar, editar ou excluir na página pública. A única forma de alterar o conteúdo é editando o `posts.json` e publicando (fazendo commit) no repositório, algo que só quem tem acesso de escrita ao repositório consegue fazer.
