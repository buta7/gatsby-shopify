# README

## はじめに

* [Shopify](https://www.shopify.jp/)というECプラットフォームと[Gatsby](https://gatsbyjs.com/)を組み合わせたオンラインショップのサンプル
* ソース元のGithubに`SHOPIFY_ACCESS_TOKEN`が付与されているのでトークンは発行しなくてよい

## Setup

サイト作成

```shell
npx gatsby new gatsby-shopify https://github.com/AlexanderProd/gatsby-shopify-starter
```

サーバ起動

```
cd gatsby-shopify
gatsby develop
```

## Github pagesとの連携

gatsby-config.js(リンクのprefixを付加:githubのレポジトリ名に設定すること)

```js
//...
  pathPrefix: "/gatsby-shopify",
//}
```

gatsby-config.js(上記prefixを付加してbuildしpublicディレクトリをgh-pagesブランチにプッシュ)

```js
//...
"scripts": {
  ...
  "develop": "gatsby develop",
  "deploy": "gatsby build --prefix-paths && gh-pages -d public",
  "clean": "gatsby clean",
  //...
```

gh-pagesのインストール

```shell
npm install gh-pages --save-dev
```

GithubにRepository"gatsby-shopify"を作成後

```shell
git remote add origin git@github.com:higebobo/gatsby-shopify.git
git add -A
git commit -m 'init'
git push -u origin master
```

デプロイ

```
npx run deploy
```

reactが無いというエラーが出た場合

```
rm -fr package-lock.json node_modules
npm i
```

## Link

* [ https://github\.com/AlexanderProd/gatsby\-shopify\-starter
](https://www.gatsbyjs.org/starters/AlexanderProd/gatsby-shopify-starter/)
* [How Gatsby Works with GitHub Pages \| GatsbyJS](https://www.gatsbyjs.org/docs/how-gatsby-works-with-github-pages/)
* [Can I change build directory path from public to anything else? · Issue \#14703 · gatsbyjs/gatsby](https://github.com/gatsbyjs/gatsby/issues/14703)
* [VSCodeでgatsbyのデバッグをする \- Qiita](https://qiita.com/3S_Laboo/items/8a963cd87d917a8bd3c9)
