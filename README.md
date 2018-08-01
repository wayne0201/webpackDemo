# webpack 4

### webpack 4主要改动

- mode
- 零配置(zero configration)
- optimization.splitChunks(废弃CommonsChunkPlugin)
- optimization.minimizer(废弃uglifyjs)

## 安装
1. 使用`npm`安装`webpack`与`webpack-cli`
2. 对于大多数项目，建议本地安装。这可以使我们在引入破坏式变更(breaking change)的依赖时，更容易分别升级项目
3. **不推荐全局安装**,这会将你项目中的`webpack`锁定到指定版本，并且在使用不同的`webpack`版本的项目中，可能会导致构建失败。

## 零配置
1. webpack 4默认不需要配置文件
2. 默认的入口默认值为`./src/index.js`
3. 默认的导出路径为`./dist/main.js`

## mode
1. `webpack4`中提供的`mode`有三个值：`development`、`production`和`none`，默认值是 `production`
2. 使用`development`和`production`的时候，`webpack`会提供一些默认配置,使用`none`表示不使用这些默认配置

#### 方式一
通过配置`package.json`里的启动命令后的参数

``` json
"scripts": {
  "dev": "webpack --mode development",
  "build": "webpack --mode production"
}
```

#### 方式二
在`webpack`的配置文件中添加mode属性

``` javascript
module.exports = {
	mode: 'production' // development
};
```