### Olá! Bem Vindo

# 👨🏽‍💻 Eduardo M. Santos

**`DESENVOLVEDOR`**

# Github Breakout

Generate a Breakout game SVG from a GitHub user's contributions graph

This project will grab your contribution graph through the GitHub API and generate images for light and dark mode:

<picture>
  <source
    media="(prefers-color-scheme: dark)"
    srcset="example/dark.svg"
  />
  <source
    media="(prefers-color-scheme: light)"
    srcset="example/light.svg"
  />
  <img alt="Breakout Game" src="example/light.svg" />
</picture>

## Usage

### GitHub Action

You can use the provided GitHub Action to build the SVGs so you can display them like on my profile ([github.com/cyprieng](https://github.com/cyprieng)):

Generate the SVGs every day and commit them to your repository:

```yaml
name: generate breakout svg

on:
  schedule:
    - cron: "0 */24 * * *"
  workflow_dispatch:

jobs:
  generate-svg:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: Checkout repository
        uses: actions/checkout@v4

      - name: generate SVG
        uses: cyprieng/github-breakout@v1.0.0
        with:
          github_username: ${{ github.repository_owner }}

      - name: Move generated SVGs
        run: |
          mkdir -p images
          mv output/light.svg images/breakout-light.svg
          mv output/dark.svg images/breakout-dark.svg

      - name: Configure git
        run: |
          git config user.name "github-actions[bot]"
          git config user.email "github-actions[bot]@users.noreply.github.com"

      - name: Commit and push SVGs
        run: |
          git add images/breakout-light.svg images/breakout-dark.svg
          git commit -m "chore: update breakout SVGs" || echo "No changes to commit"
          git push
```

Add them to your README.md:

```html
<picture>
  <source
    media="(prefers-color-scheme: dark)"
    srcset="images/breakout-dark.svg"
  />
  <source
    media="(prefers-color-scheme: light)"
    srcset="images/breakout-light.svg"
  />
  <img alt="Breakout Game" src="images/breakout-light.svg" />
</picture>
```

### CLI

You need to get a GitHub Token, then you can run the following command:

`node dist/cli.js {username} {github token} {dark mode: true/false}`

### Library

The package is currently not available on npm, so you can install it with:

`npm i --save git+ssh://git@github.com:cyprieng/github-breakout.git`

And then you can use it like this:

```javascript
import { generateSVG } from "github-breakout";

await generateSVG(username, token, false);
```

### Try it

You can try it here: [www.cyprien.io/projects/github-breakout](https://www.cyprien.io/projects/github-breakout/#try-it)


Me chamo Eduardo Mathias, tenho 18 anos e sou de Curitiba/PR.
Estou cursando o 2º período de Engenharia de Software e busco uma oportunidade de estágio na área de programação para ganhar experiência prática, evoluir como desenvolvedor e contribuir com projetos reais.
Tenho muita vontade de aprender e crescer na área de tecnologia. 🚀

<p align="left">
    <a href="https://api.whatsapp.com/send/?phone=5541991498368&text&type=phone_number&app_absent=0">
        <img 
            alt="Whatsapp" 
            title="Entre em Contato!" 
            src="https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white"
        />
    </a>
    <a href="https://www.google.com/maps/place/curitiba+parana/data=!4m2!3m1!1s0x94dce35351cdb3dd:0x6d2f6ba5bacbe809?sa=X&ved=1t:155783&ictx=111">
        <img 
            alt="Localização" 
            title="Curitiba"
            src="https://custom-icon-badges.demolab.com/badge/CUritiba-PR-black?style=for-the-badge&logo=location&logoColor=red"
        />
    </a> 
    <a href="https://www.instagram.com/eduu.zxs/">
        <img 
            alt="Instagram" 
            title="Instagram" 
            src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white"
        />
    </a>
    <a href="mailto:eduardomathias450@gmail.com?subject=Assunto do email&cc=copia@provedor.com.br&bcc=copiaoculta@provedor.com.br&body=Conteúdo do email que será preenchido automaticamente">
        <img 
            alt="Gmail" 
            title="eduardomathias450@gmail.com" 
            src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white"
        />
    </a>
</p>


## Sobre mim

- Repositório em obras 🚧 — cada commit é um tijolinho no meu castelo de código.
- Atualmente estou Estudando na área de **Engenharia de Software**
- Me contate no email eduardomathias450@gmail.com 📫
- Acesse [meu perfil no Linkedin]((https://www.linkedin.com/in/eduardo-mathias-070288379/)) para saber mais de mim 📄
- Fun fact: Meu código nunca dá erro… ele só cria funcionalidades inesperadas.

---

### 🤖 Linguagens e Tecnologias

<img 
    align="left" 
    alt="HTML"
    title="HTML" 
    width="30px" 
    style="padding-right: 10px;" 
    src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/html5/html5-original.svg" 
/>
<img 
    align="left" 
    alt="CSS" 
    title="CSS"
    width="30px" 
    style="padding-right: 10px;" 
    src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/css3/css3-original.svg" 
/>
<img 
    align="left" 
    alt="JavaScript" 
    title="JavaScript"
    width="30px" 
    style="padding-right: 10px;" 
    src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/javascript/javascript-original.svg" 
/>
<img 
    align="left" 
    alt="JQuery" 
    title="JQuery"
    width="30px" 
    style="padding-right: 10px;" 
    src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/jquery/jquery-original.svg" 
/>
<img 
    align="left" 
    alt="Python" 
    title="Python"
    width="30px" 
    style="padding-right: 10px;" 
    src="https://cdn.jsdelivr.net/gh/devicons/devicon@latest/icons/python/python-original.svg" 
/>

<br/>
<br/>

### 📊 Estatísticas

<p>
  <img 
    align="left" 
    alt="GitHub Stats" 
    height="200" 
    style="padding-right: 10px;" 
    src="https://github-readme-stats.vercel.app/api?username=EduardoMathiasDEV&show_icons=true&theme=tokyonight&include_all_commits=true&locale=pt-br" 
  />

<img 
      align="left" 
      alt="GitHub Stats" 
      height="200" 
      src="https://github-readme-stats.vercel.app/api/top-langs/?username=EduardoMathiasDEV&theme=tokyonight&layout=compact&custom_title=Tecnologias&langs_count=9" 
  />

</p>

