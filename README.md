# vuetifyjs-nuxt-init

這個專案是從 vuetifyjs/nuxt 這個 template init 的

```bash
$ vue init vuetifyjs/nuxt
```

-----

Vuetifyjs 使用 1.0.0 beta 版

package.json
```
"vuetify": "> 1.0.0-beta"
```

-----

修改了 layouts/default.vue

- 移除一些奇怪的東西（可能是舊 vuetifyjs 的東西？）
- 例如 v-navigation-drawer 有個 router 的 property，移除並改成 nuxt


## Build Setup

``` bash
# install dependencies
$ npm install # Or yarn install

# serve with hot reload at localhost:3000
$ npm run dev

# build for production and launch server
$ npm run build
$ npm start

# generate static project
$ npm run generate
```

For detailed explanation on how things work, check out the [Nuxt.js](https://github.com/nuxt/nuxt.js) and [Vuetify.js](https://vuetifyjs.com/) documentation.
