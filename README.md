<h1 align="center">Hi 👋, I'm Deepak mandal</h1>
<h3 align="center">i will tell you how you can eseally deploy next applicaion via gh-pages</h3>

<h3 align="left">follow the steps and enjoy 😋</h3>
<p align="left">
</p>

 <h3> step-1  </h3>

first create next app in local directory

<h3> step-2  </h3>
steps: initiliase git repo
<h3> step-3  </h3> steps:create .github/workflows/node.js.yml file
<h3> step-4  </h3> steps:
type below
<h3> step-5  </h3> steps: npm i
<h3> step-6  </h3> steps: add "export": "next export"
<h3> step-7  </h3> 
steps: 
    Change the next.config.js file to next.config.mjs, and replace everything inside with the following:

steps : 
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
         # This workflow will do a clean install of node dependencies, build the source code  and  run tests across       different versions of node

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
<h3>step - 8 </h3> steps:push in your repo
<h3>step - 9</h3> steps:go to setting in github
<h3>step - 10</h3> steps:go to setting in github
<h3>step - 11</h3> steps: go in pages
 under Build and deployment -> branch part

 go to select none to public and /root and save
<h3>step - 12</h3> steps: make some changes and push to github




