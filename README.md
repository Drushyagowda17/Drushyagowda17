## Hi  I'm Drushya 



## 🌐 Socials:
[![LinkedIn](https://img.shields.io/badge/LinkedIn-%230077B5.svg?logo=linkedin&logoColor=white)](https://linkedin.com/in/Drushya Gowda) [![email](https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white)](mailto:drushyagmgowda@gmail.com) 

# 💻 Tech Stack:
![Flask](https://img.shields.io/badge/flask-%23000.svg?style=plastic&logo=flask&logoColor=white) ![C](https://img.shields.io/badge/c-%2300599C.svg?style=plastic&logo=c&logoColor=white) ![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=plastic&logo=c%2B%2B&logoColor=white) ![Canva](https://img.shields.io/badge/Canva-%2300C4CC.svg?style=plastic&logo=Canva&logoColor=white) ![Flask](https://img.shields.io/badge/flask-%23000.svg?style=plastic&logo=flask&logoColor=white) ![Python](https://img.shields.io/badge/python-3670A0?style=plastic&logo=python&logoColor=ffdd54) ![C](https://img.shields.io/badge/c-%2300599C.svg?style=plastic&logo=c&logoColor=white) ![C++](https://img.shields.io/badge/c++-%2300599C.svg?style=plastic&logo=c%2B%2B&logoColor=white) ![Java](https://img.shields.io/badge/java-%23ED8B00.svg?style=plastic&logo=openjdk&logoColor=white) ![HTML5](https://img.shields.io/badge/html5-%23E34F26.svg?style=plastic&logo=html5&logoColor=white) ![Flask](https://img.shields.io/badge/flask-%23000.svg?style=plastic&logo=flask&logoColor=white) ![Canva](https://img.shields.io/badge/Canva-%2300C4CC.svg?style=plastic&logo=Canva&logoColor=white)
# 📊 GitHub Stats:
![](https://github-readme-stats.vercel.app/api?username=Drushyagowda17&theme=one_dark_pro&hide_border=false&include_all_commits=false&count_private=false)<br/>
![](https://nirzak-streak-stats.vercel.app/?user=Drushyagowda17&theme=one_dark_pro&hide_border=false)<br/>
![](https://github-readme-stats.vercel.app/api/top-langs/?username=Drushyagowda17&theme=one_dark_pro&hide_border=false&include_all_commits=false&count_private=false&layout=compact)

---
[![](https://visitcount.itsvg.in/api?id=Drushyagowda17&icon=2&color=13)](https://visitcount.itsvg.in)

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
