# nuxt.js引入预处理器和外部css库
> 填坑日记
### 1.引入外部css库
例如：引入**fontAwesome**
##### 1.1. 添加font-awesome依赖
`yarn add font-awesome`
`npm install --save-dev font-awesome`
##### 1.2. 在根目录创建一个 **/modules/css-modules.js**  
```javascript
export default function (moduleOptions) {
  if (moduleOptions.fontAwesome !== false) {
    // Add Font Awesome
    this.options.css.push('font-awesome/css/font-awesome.css')
  }
}
```
##### 1.3. 在**nuxt.config.js**添加配置
```javascript
modules: [
    // Doc: https://github.com/nuxt-community/axios-module#usage
    '@nuxtjs/axios',
    '@/modules/css-modules.js'
  ],
```

### 2. 使用scss预处理器
##### 2.1 引入依赖
`yarn add node-sass sass-loader`
`npm install --save-dev node-sass sass-loader`
##### 2.2 在vue文件中使用
```css
<style lang="sass" scoped>
.posts-wrapper
    h3
        color: blue;
</style>
```
##### 2.3 在引入全局scss文件
在nuxt.config.js中配置
```javascript
/*
  ** Global CSS
  */
  css: [
    'element-ui/lib/theme-chalk/index.css',
    { src: '~assets/css/index.scss', lang: 'scss' }
  ],
```

### 3. 使用less预处理器
##### 3.1 引入依赖
`yarn add less less-loader`
`npm install --save-dev less less-loader`
##### 3.2 在vue文件中使用
```css
<style lang="less" scoped>
.posts-wrapper {
    h3 {
        color: blue;
    }
}
</style>
```
##### 3.3 在引入全局less文件
在nuxt.config.js中配置
```javascript
/*
  ** Global CSS
  */
  css: [
    'element-ui/lib/theme-chalk/index.css',
    { src: '~assets/css/index.less', lang: 'less' }
  ],
```