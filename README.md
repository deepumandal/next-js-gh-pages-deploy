step-1 first create next app in local directory
step-2 initiliase git repo 
step-3 create .github/workflows/node.js.yml file 
step-4 type below
ste- 5 npm i

# This workflow will do a clean install of node dependencies, build the source code and run tests across different versions of node
# For more information see: https://help.github.com/actions/language-and-framework-guides/using-nodejs-with-github-actions

name: GitHub Pages deploy

on:
  push:
    branches: [main]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout 🛎️
        uses: actions/checkout@v2.3.1
      - name: Use Node.js 18.x
        uses: actions/setup-node@v1
        with:
          node-version: '18.x'

      - name: Installing my packages
        run: npm ci

      - name: Build my App
        run: npm run build && npm run export && touch ./out/.nojekyll

      - name: Deploy 🚀
        uses: JamesIves/github-pages-deploy-action@v4.3.3
        with:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          BRANCH: public # The branch the action should deploy to.
          FOLDER: out # The folder the action should deploy

step-2 push in your repo
step-2 
step-2 
step-2 