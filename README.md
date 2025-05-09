### Olá! Eu sou o Guilherme 👋

### Tecnologias que eu utilizo para desenvolvimento de softwares:
<div style="display: inline_block"><br/>
        <img aling="center" alt="Python" height="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/python.png">
        <img aling="center" alt="Java" height="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/java.png">
        <img aling="center" alt="Mysql" height="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/mysql.png">
        <img aling="center" alt="godot" height="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/godot.png">
        <img aling="center" alt="arduino" height="50" src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/arduino.png">
        <img aling="center" alt="" height="50" src="">
</div>
<p>

</p>

![GuilhermeDeMedeirosBif's GitHub stats](https://github-readme-stats.vercel.app/api?username=GuilhermeDeMedeirosBif&show_icons=true&theme=radical)

![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=GuilhermeDeMedeirosBif&layout=compact&theme=radical)

### Onde me encontrar:
<div>
        
[![Instagram](https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white)](https://www.instagram.com/guilhermebif_/)
[![Linkedin](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/guilherme-de-medeiros-bif-b3a0b2302/)
[![TikTok](https://img.shields.io/badge/TikTok-000000?style=for-the-badge&logo=tiktok&logoColor=white)](https://www.tiktok.com/@justdev.py?lang=pt-BR)

</div>

<h2 align="left">Hi 👋! My name is Guilherme </h2>

###

<div align="center">
        
  ![GuilhermeDeMedeirosBif's GitHub stats](https://github-readme-stats.vercel.app/api?username=GuilhermeDeMedeirosBif&show_icons=true&theme=radical)
  <img src="https://github-readme-stats.vercel.app/api/top-langs?usarname=GuilhermeDeMedeirosBif&locale=en&hide_title=false&layout=compact&card_width=320&langs_count=5&theme=dracula&hide_border=false" height="150" alt="languages graph"  />
        
</div>

###

###

<div align="left">
  <img src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/python.png" height="30" alt="python logo"  />
  <img width="12" />
  <img src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/java.png" height="30" alt="java logo"  />
  <img width="12" />
  <img src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/mysql.png" height="30" alt="mysql logo"  />
  <img width="12" />
  <img src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/godot.png" height="30" alt="godot logo"  />
  <img width="12" />
  <img src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/arduino.png" height="30" alt="arduino logo"  />
  <img width="12" />
  <img src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/eclipse.png" height="30" alt="eclipse logo"  />
  <img width="12" />
  <img src="https://raw.githubusercontent.com/marwin1991/profile-technology-icons/refs/heads/main/icons/visual_studio_code.png" height="30" alt="vscode logo"  />
</div>

###

<div align="left">
  <img src="https://img.shields.io/static/v1?message=Youtube&logo=youtube&label=&color=FF0000&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="youtube logo"  />
  <img src="https://img.shields.io/static/v1?message=Instagram&logo=instagram&label=&color=E4405F&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="instagram logo"  />
  <img src="https://img.shields.io/static/v1?message=Twitch&logo=twitch&label=&color=9146FF&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="twitch logo"  />
  <img src="https://img.shields.io/static/v1?message=Discord&logo=discord&label=&color=7289DA&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="discord logo"  />
  <img src="https://img.shields.io/static/v1?message=Gmail&logo=gmail&label=&color=D14836&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="gmail logo"  />
  <img src="https://img.shields.io/static/v1?message=LinkedIn&logo=linkedin&label=&color=0077B5&logoColor=white&labelColor=&style=for-the-badge" height="35" alt="linkedin logo"  />
</div>

###

<br clear="both">

<img src="https://raw.githubusercontent.com/GuilhermeDeMedeirosBif/GuilhermeDeMedeirosBif/output/snake.svg" alt="Snake animation" />

###

name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - main

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


