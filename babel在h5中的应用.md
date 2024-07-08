# babel在h5中的应用

在一些浏览器版本比较低的场景中，不支持ES最新的语法，比如：ES2020中的：
- 可选链操作符（Optional Chaining）
```js
let nestedProp = obj?.first?.second;
```
- 空位合并操作符（Nullish coalescing Operator）
```js
let c = a ?? b;
// 等价于let c = a !== undefined && a !== null ? a : b;
```

## 如何处理

```js
// 只处理 node_modules/pixi.js 目录下的 .mjs 文件 
{
  test: /\.mjs$/, 
  include: /node_modules\/pixi\.js/,
  use: {
    loader: 'babel-loader',
    options: {
      presets: [
        [
          '@babel/preset-env',
          {
            targets: {
              esmodules: true,
            },
          },
        ],
      ],
      plugins: [
        '@babel/plugin-transform-nullish-coalescing-operator',
      ],
    },
  },
},
```
因为涉及到大部分的库打包出来的产物对应到es2020，如果需要适配低版本的浏览器需要babel单独处理node_modules里库对应的源代码。



## 参考
- [ES2020新特性](https://juejin.cn/post/6844904080955932679#heading-7)
