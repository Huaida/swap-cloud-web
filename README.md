# swap-cloud-web

> 老虎合约云前端demo

## Build Setup

``` bash
# install dependencies
$ npm install # Or yarn install*[see note below]

# serve with hot reload at localhost:3008
$ npm run dev

# build for production and launch server
$ npm run build
$ npm start
```

>Note: Due to a bug in yarn's engine version detection code if you are
using a prerelease version of Node (i.e. v7.6.0-rc.1) you will need to either:
  1. Use `npm install`
  2. Run `yarn` with a standard release of Node and then switch back

该项目使用了 [Nuxt.js](https://zh.nuxtjs.org/) 框架。有关工作原理的详细说明请查看[Nuxt.js docs](https://github.com/nuxt/nuxt.js).

## Usage  

基本配置
```javascript
cookie.getCookie('tocken'); // secret储存的key为tocken
cookie.getCookie('expired_ts');
cookie.getCookie('access_key');
```

>注意: 站点重度依赖tocken字段为用户登录态判断依据，所以项目方在登录后，要把`secret`、`expired_ts`,`access_key`储存到cookie中。eg:    

```javascript
cookie.setCookie('tocken', '461581496df9211abeaddf3cb108129a', '', '/', 'test.com')
cookie.setCookie('expired_ts', '1544165433', '', '/', 'test.com')
cookie.setCookie('access_key', 'ebb1b16a-3556-45b3-ad00-13d3120ba834', '', '/', 'test.com')
```  

1. 上线需把**api.config.master.js** 的内容覆盖**api.config.js**
2. `isYun` 字段设为`true`  
![]("/static/readme/usage-2.png")
![]("https://github.com/tigercloudproject/swap-cloud-web/blob/master/static/readme/usage-2.png")
3. 需要接入当前平台的用户资产和用户信息，为转账到期货和头部显示做准备  

## Components Intro
1. 用户转账组件  
components\index\submit-entrust-cp\transfer-window.vue
2. 用户信息组件  
components\template\user-info.vue
