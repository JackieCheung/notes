**Webpack实现按需打包Lodash的几种方法详解**

*https://www.jb51.net/article/113235.htm*



**在vue-cli中引入lodash.js并使用**

*https://blog.csdn.net/Amanda_wmy/article/details/88638309*



**lodash按需引入**

*https://www.cnblogs.com/fancyLee/p/10932050.html*



Vue-Cli 3.x使用moment.js、lodash打包精简

安装webpack-bundle-analyzer和lodash-webpack-plugin，配置vue.config.js文件

```
let webpack = require('webpack')
let BundleAnalyzerPlugin = require('webpack-bundle-analyzer').BundleAnalyzerPlugin
let LodashModuleReplacementPlugin = require('lodash-webpack-plugin')

module.exports = {
 chainWebpack: config => {
 config.plugin('ignore')
  .use(new webpack.IgnorePlugin(/^\.\/locale$/, /moment$/))
 config.plugin('analyzer')
  .use(new BundleAnalyzerPlugin())
 config.plugin('loadshReplace')
  .use(new LodashModuleReplacementPlugin())
 }
}
```

