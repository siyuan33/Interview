HTTP 可以优化 ：
减少请求次数
减少单次请求所花费的时间

所以要优化 webpack
所以要解决 ：

webpack 的构建过程太花时间
webpack 打包的结果体积太大

构建提速：
不要让 loader 去处理不必要的文件 比如 node_modules
babel 开启缓存
一些插件

使用 hard-source-webpack-plugin (构建开启缓存)

使用 DllPlugin 如果不配置 每次第三方依赖都会被打包 使用了之后会单独将写入配置的第三方依赖 比如 react react-dom 之类的单独打包到 vender.js 然后通过一个 vendor-manifest.json 配置将 vender.js 进入进来 这样不用每次都打包依赖了。

使用 Happypack 将打包进城从单进程变成多进程

减小体积

使用 webpack-bundle-analyzer 查看各个包的体积
使用 Tree-Shaking 抖掉不用的代码 (webpack5 自带了)
使用 UglifyJsPlugin 删除 console.log debugger 注释之类的(webpack4 自带)
组件按需加载 require('xxxx')
开启 Gzip 静态文件压缩(本来应该是服务器实现 Gzip 但是 webpack 率先压缩可以减轻服务器压力)
