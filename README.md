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

#### 配置项目

> 1. 配置 `eslint`

`.eslintrc.js` 在这个文件的最后面添加如下规则

```js

// 函数后面不需要加空格
'space-before-function-paren': 'off',
// 强制不加分号
"semi": [2, "never"]

```

> 2. 配置 `package.json`

在这个文件中找到 scripts 块

添加如下配置

```js

// yarn lintfix - 可快速解决 eslint 语法错误
"lintfix": "eslint --ext .js,.vue src --fix",

```

修改如下配置

```js

// 加上 --open 后，可让项目在启动后自动在浏览器中自动打开
"dev": "webpack-dev-server --inline --progress --config build/webpack.dev.conf.js --open",

```


#### nginx 配置

> 1. 让手机可以访问电脑（本地） web 服务（自己的网站）


```nginx

server {
	listen       8080;
	server_name  localhost;

	location / {
		proxy_pass http://127.0.0.1:8080;
	}
}

```

