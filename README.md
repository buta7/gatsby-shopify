# README

## Setup

サイト作成

    $ npx gatsby new gatsby-shopify https://github.com/AlexanderProd/gatsby-shopify-starter

サーバ起動

    $ cd higebobo-shopify
    $ gatsby develop

## Github pagesとの連携

gatsby-config.js(リンクのprefixを付加:githubのレポジトリ名に設定すること)

    ...
      pathPrefix: "/gatsby-shopify",
    }

gatsby-config.js(上記prefixを付加してbuildしpublicディレクトリをgh-pagesブランチにプッシュ)

    ...
    "scripts": {
      ...
      "develop": "gatsby develop",
      "deploy": "gatsby build --prefix-paths && gh-pages -d public",
      "clean": "gatsby clean",
      ...

gh-pagesのインストール

    $ npm install gh-pages --save-dev

GithubにRepository"gatsby-shopify"を作成後

    $ git remote add origin git@github.com:higebobo/gatsby-shopify.git
    $ git add -A
    $ git commit -m 'init'
    $ git push -u origin master

デプロイ

    $ npx run deploy

reactが無いというエラーが出た場合

    $ rm -fr package-lock.json node_modules
    $ npm i

## Link

* [ https://github\.com/AlexanderProd/gatsby\-shopify\-starter
](https://www.gatsbyjs.org/starters/AlexanderProd/gatsby-shopify-starter/)
* [GatsbyとNetlifyで簡単にブログを作成 \- Qiita](https://qiita.com/k-penguin-sato/items/7554e5e7e90aa10ae225)
* [How Gatsby Works with GitHub Pages \| GatsbyJS](https://www.gatsbyjs.org/docs/how-gatsby-works-with-github-pages/)
* [Can I change build directory path from public to anything else? · Issue \#14703 · gatsbyjs/gatsby](https://github.com/gatsbyjs/gatsby/issues/14703)
