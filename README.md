<p align="right"> <img src="https://komarev.com/ghpvc/?username=RamakrishnaTanam&label=Profile%20views&color=0e75b6&style=flat" alt="RamakrishnaTanam" /> </p>
<h1 align="center">
    <img src="https://readme-typing-svg.herokuapp.com/?font=Righteous&size=35&center=true&vCenter=true&width=500&height=70&color=blue&duration=3000&lines=Hi+There!+👋;+Myself++Ramakrishna!;" />
</h1>

<h3 align="center">A passionate Software Developer</h3>

<div align="center"> 
  <a href="https://www.linkedin.com/in/ramakrishnatanam" target="_blank">
    <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" target="_blank" />
  </a>
  <a href="https://calm-cat-d8c98f.netlify.app/#" target="_blank">
     <img src="https://img.shields.io/badge/Portfolio-FF5722?style=for-the-badge&logo=todoist&logoColor=white" target="_blank" /> 
  </a>
</div>

<hr/>

<h2 align="center"> Languages - Frameworks - Tools </h2>
<br/>
<div align="center">
    <img src="https://skillicons.dev/icons?i=react,html,css,vscode,github,git" /><br>
    <img src="https://skillicons.dev/icons?i=express,mongodb,nodejs,python,javascript,mysql" /><br>
    <img src="https://skillicons.dev/icons?i=sqlite,numpy,pandas,openai,jupyter,redux" /><br>
    <img src="https://skillicons.dev/icons?i=jenkins" />
    <img src="https://img.shields.io/badge/CI%2FCD-00C853?style=for-the-badge&logo=gitlab&logoColor=white" alt="CI/CD" />
    <img src="https://img.shields.io/badge/Data%20Structures%20and%20Algorithms-FF5722?style=for-the-badge&logo=google&logoColor=white" alt="Data Structures and Algorithms" />
</div>

<br/>
<hr/>

<h2 align="center"> Stats </h2>
<br>
<div align="center">
    <img src="https://github-readme-stats.vercel.app/api?username=RamakrishnaTanam&show_icons=true&theme=radical" alt="RamakrishnaTanam's GitHub stats" />
    <br>
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=RamakrishnaTanam&layout=compact&theme=radical" alt="Top Langs" />
</div>

<hr/>

## 🐍 Generate Snake Animation

```yaml
name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - master

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5

    steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark

      - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
