[![Deploy to GitHub Pages](https://github.com/jithinolickal/svelte-todo-app/actions/workflows/deploy.yml/badge.svg)](https://github.com/jithinolickal/svelte-todo-app/actions/workflows/deploy.yml)

# Svelte Todo App

This repo shows how to deploy a svelte app to github pages using automated github actions
## Deploy Svelte app to Github Pages using Github Actions

### Create Svelte App

1. Create a sample project using Svelte template from https://github.com/sveltejs/template
2. Install dependencies ```npm install```
3. Start project ```npm run dev```
4. Make necessary changes to your app

### Setup Github Actions - Deploy to Github Pages

1. Create a folder .github/workflows
2. Add a new file with .yml extension (Example: deploy.yml)
3. Copy scripts from https://github.com/jithinolickal/svelte-todo-app/blob/master/.github/workflows/deploy.yml
    - Make sure to create a personal token and connect it to your repo (repo > settings > Secretc > New repository secret)
    - Update the secret name inside your workflow *.yml file
4. Update all paths in /public/index.html file to relative path [reference](https://github.com/jithinolickal/svelte-todo-app/commit/4038c6fc8a927425b98fe788629e378675f735b5)
    - Example : ```href='/build/bundle.css'``` to ```href='./build/bundle.css'```
5. Create a branch named ```gh-pages``` in the current repository
6. Commit all the changes and wait github acions to deploy your changes
