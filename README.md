# blog

> blog_v1.2

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).

` 基于blog_v1.1 再次开发 `

---

### 2019-07-09 22：40

#### 在vue项目中使用sass的配置方法

> 1. 安装sass的依赖包

```

cnpm install --save-dev sass-loader
cnpm install --save-dev node-sass

```

> 2. 在build文件夹下的webpack.base.conf.js的rules里面添加配置

```js

{
 test: /\.sass$/,
 loaders: ['style', 'css', 'scss']
}

```

> 3. 在 `App.vue` 中修改 `style` 标签 `lang`

```vue

<style lang="scss">
$bac: blue;

#app {
  // font-family: 'Avenir', Helvetica, Arial, sans-serif;
  // -webkit-font-smoothing: antialiased;
  // -moz-osx-font-smoothing: grayscale;
  // text-align: center;
  // color: #2c3e50;
  // margin-top: 60px;
  background-color: $bac;
}
</style>

```

---

#### 
