---
title: 'Automação de feed do seu blog no perfil do github 🤖'
date: '2020-08-08'
---

## Que tal linkar seus novos posts de conteúdo no perfil do github de forma automática?

![Alt imagem exemplo no perfil do github](https://dev-to-uploads.s3.amazonaws.com/i/de1f6g3icujra84gpmfd.png)

Funciona com a maioria das plataformas de blogs como DEV, Wordpress, Mediume até playlist de youtube. Assim que você publicar um conteúdo novo, através do github actions, irá verificar de tempos em tempos se há uma atualização de FEED, com isso fará um update no readme do seu perfil.

Caso não saiba como fazer um readme para o seu perfil, [clique aqui](https://dev.to/leoyassuda/um-readme-para-o-seu-user-do-github-27pf). 👈

Então bora lá! 🦾

Na imagem, tem como exemplo meu único post feito no [dev.to](http://dev.to) 😜, mas assim que publicar esse conteúdo, teremos dois links na lista. 🤟

Passo a passo:

- No seu arquivo `REAMDE.md` vamos inserir duas tags de marcação.

```yaml
# Lastest Blog posts
<!-- BLOG-POST-LIST:START -->
<!-- BLOG-POST-LIST:END -->
```

- Agora na raiz criaremos duas pastas a primeira `.github` e dentro a pasta `workflows` .
- Dentro da pasta `workflows` , criaremos o arquivo de configuração yaml `blog-post-workflow.yml` com o seguinte conteúdo.

```yaml
name: Latest blog post workflow
on:
  schedule:
    # Runs every hour
    - cron: '0 * * * *'

jobs:
  update-readme-with-blog:
    name: Update this repo's README with latest blog posts
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - uses: gautamkrishnar/blog-post-workflow@master
        with:
          feed_list: "https://dev.to/feed/seu_usuario,https://medium.com/feed/@seu_usuario"
```

Obs.: no atributo `feed_list` passamos uma String separadas por vírgula dos links dos feeds que vocês queiram, nesse caso um exemplo para linkar o dev.to e o medium.

- Agora podemos fazer o commit e push, e esperar pelo github actions ser rodado. ✌️

Para mais customizações ou opções avançadas, segue o link do autor dessa automação.

[blog-post-workflow](https://github.com/gautamkrishnar/blog-post-workflow#options)

---