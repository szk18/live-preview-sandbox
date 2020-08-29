# live-preview-sandbox

Nuxt.js の [preview mode](https://nuxtjs.org/guides/features/live-preview#previewing-pages-that-are-not-yet-generated)をどうにか試してみる

## やったこと

microcms で適当にコンテンツを作成して API を叩く。

ドキュメントの通りにコマンドを叩く

```
$ yarn generate
$ yarn start
```

`/blog/:id` で記事が表示される。
ここで microcms のコンテンツを書き換えてリロードしても、変化はない。

次に`/blog/:id?preview=true` で microcms の記事を書き換え、リロードすると差分が更新された。

これが preview mode なのか? なにが嬉しいのかわからん

## その他

API_KEY を `privateRuntimeConfig` に設定するとうまくいかなかったので、 `publicRuntimeConfig` に設定した。

## Build Setup

```bash
# install dependencies
$ yarn install

# serve with hot reload at localhost:3000
$ yarn dev

# build for production and launch server
$ yarn build
$ yarn start

# generate static project
$ yarn generate
```

For detailed explanation on how things work, check out [Nuxt.js docs](https://nuxtjs.org).
