---
layout: post
title: Deploy Hugo static site using Github Actions on Github pages
summary: "If you already have static site built using Hugo, 
and whenever you need to update or add new post on website you have to build the site locally and push the changes to github. 
then you might consider using Github Actions. It is free for public repository use"
date:   2021-11-14
tags: [CICD, Github-Pages, Github-Actions, Hugo]
---

<style>
  .green{
    color:#1A7F37;
  }
  .blue,.blue>a{
   color:#0969DA;
   }
  
</style>


If you already have static site built using Hugo, 
and whenever you need to update or add new post on website you have to build the site locally and push the changes to github. 
then you might consider using Github Actions. It is free for public repository use.

I have Two branches 
- master (This branch I deploy on github pages) 
- <span class="green">code</span> (where I keep Development code, I will create deployment build from this branch and store into master)

All you need to do is 
 - create a Github access token from here <span class="blue"> [https://github.com/settings/tokens/new](https://github.com/settings/tokens/new) </span>
 - add access token value as repository secret at ```<repository-url>/settings/secrets/actions``` 
   where key is```TOKEN``` this key we are going to use in Action
 - create Action

## Create Action
- To create Action go to actions tab of your repository and select <span class="blue"> set up a workflow yourself → </span>

![image](https://user-images.githubusercontent.com/28999685/141675680-a372065c-a343-48e7-8ea9-5316cf05bd39.png)

copy and paste this action 

```yml
    name: hugo CI

    on:
      push:
        branches: [ code ]

    jobs:
      deploy:
        environment: github-pages
        runs-on: ubuntu-18.04
        steps:
          - name: Git checkout
            uses: actions/checkout@v2

          #(Optional) If you have the theme added as submodule and Update theme step(next step) is not working then delete themes directory  
          - name: Clone theme
            run: git submodule add <theme's github repo> themes/<theme name> --depth=1
                # e.g git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod --depth=1

          #(Optional) If you have the theme added as submodule, you can pull it and use the most updated version
          - name: Update theme
            run: git submodule update --init --recursive

          - name: Setup hugo
            uses: peaceiris/actions-hugo@v2
            with:
              hugo-version: "0.87.0"

          - name: Build
            run: hugo --minify
          
           # just for logging the Repo name and branch 
          - name: Log Repo
            run: echo "💡 The ${{ github.repository }} repository has been cloned to the runner."
          - name: Log Branch
            run: echo " current branch  is ${{ github.ref }} "

          - name: Deploy
            uses: peaceiris/actions-gh-pages@v3
            with:
              personal_token: ${{ secrets.TOKEN }}
              external_repository: <username>/<reponame> # e.g whoami-shubham/hugo-blog
              publish_dir: ./public
              publish_branch: master
            #   cname: example.com

```
make sure branch you are choosing are correct.
after editing click on start commit button to commit changes and 
<br> <br>
 ![image](https://user-images.githubusercontent.com/28999685/141676785-2a8bdf4c-c910-4156-b55e-2bc8034c9e79.png)

<br><br>
That's all we need to setup a GitHub Action. 
