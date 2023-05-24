# eject
eject 暴露配置项，不可逆
* npm run eject 
* yarn eject

# 常见配置修改

## 预编译语言处理
create-react-app 默认安装sass
如需要less,先安装less,在移除sass
* npm add less less-loader @8
* npm remove sass
修改webpack中的预编译处理语言
* config\webpack.config.js中73-74行、508-509行、531行、520行、543行

## create-react-app脚手架默认webpack规则修改
* 直接去暴露的源码中修改，需具有一定的webpack能力
* 改完需要重启vscode

### 修改域名端口号 ->start.js -> 端口号 POST 第47行、域名HOST 第48行
如果想要基于修改环境变量的方式来改(安装cross-env)
* npm/yarn add cross-env 
* package.json 中 scripts中的start改为 "start": "cross-env POST=8080 node scripts/start.js"

### 修改浏览器兼容
* package.json 中 修改"browserslist" ->对postcss-loader生效，控制css前缀，对babel-loader生效，控制es6转换
遗留问题：无法处理es6内置api兼容，需要@babel/polyfill对常见内置的api重写

