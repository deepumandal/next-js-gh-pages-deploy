<h1 align="center">Hi 👋, I'm Deepak mandal</h1>
<h3 align="center">i will tell you how you can eseally deploy next applicaion via gh-pages</h3>

<h3 align="left">Connect with me:</h3>
<p align="left">
</p>

step-1 first create next app in local directory
step-2 initiliase git repo
step-3 create .github/workflows/node.js.yml file
step-4 type below
step- 5 npm i
step - 6 add "export": "next export"
step -7 2. Change the next.config.js file to next.config.mjs, and replace everything inside with the following:

/\*\*

- @type {import('next').NextConfig}
  \*/
  const nextConfig = {
  images: {
  loader: 'akamai',
  path: '',
  },
  assetPrefix: './',
  };

export default nextConfig;
    steps:
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

step-8 push in your repo
step-9 go to setting in github
step-10 go in pages
step-11 under Build and deployment -> branch part

- go to select none to public and /root and save
  step - 12 make some changes and push to github
