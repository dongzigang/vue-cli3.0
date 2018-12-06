# vue-cli3.0
vue-cli3.0 使用教程

妈呀一眨眼居然到3.0了，不会用了，呵呵呵

## 全局安装

```
npm install -g @vue/cli
```

## 构建项目

windows用自带的powershell 别用gitBash！！要不然不能上下键切换选项！

1.第一步
```
vue create hello-world
```
2.选第二个
<image src="https://cli.vuejs.org/cli-new-project.png" >
  
3.按上下键选择哪一个，按空格键确定，所有的都选择好后，按enter键进行下一步
<image src="https://cli.vuejs.org/cli-select-features.png" >


4.这个是问你选择哪个自动化代码格式化检测
<image src="https://img-blog.csdn.net/20180619215127768?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NDA3NzQ4/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" >
  
  
5.这里第一个选项是问你是否保存刚才的配置，选择确定后你下次再创建新项目

就有你以前选择的配置了，不用重新再配置一遍了
<image src="https://img-blog.csdn.net/20180619215500708?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NDA3NzQ4/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" >


6.这里第一个选项是问你是否保存刚才的配置，选择确定后你下次再创建新项目

就有你以前选择的配置了，不用重新再配置一遍了
<image src="https://img-blog.csdn.net/20180619215733315?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NDA3NzQ4/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" >
 
 
7.倒数第二行问你是否将以上这些将此保存为未来项目的预配置吗？

最后一个是描述项目，你随意选择，点击确定就开始下载模板了
<image src="https://img-blog.csdn.net/20180619215957399?watermark/2/text/aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L3FxXzM2NDA3NzQ4/font/5a6L5L2T/fontsize/400/fill/I0JBQkFCMA==/dissolve/70" >

## 配置

完事之后要自己新建一个vue.config.js在根目录下，之前webpack的相关配置现在都写在这里！


这个版本也没有.babelrc 这个文件了！babeld的配置现在在babel.config.js里面配置！

## 配置css预编译处理的公用文件（如variables.less）

直接执行这个，选择你的预编译处理器

```
 vue add style-resources-loader
 
```
然后在vue.config.js里面就会多几行代码

```js
// vue.config.js
const path = require('path');
module.exports = {
    // 这里配置根目录
    baseUrl: process.env.NODE_ENV === 'production' ? '/' : '/',
    // 这里就是安装成功后多出来的代码
    pluginOptions: {
      'style-resources-loader': {
        preProcessor: 'less',
        patterns: [
            // 这个路径自己手动配的
            path.resolve(__dirname, './src/assets/css/variables.less'),
        ]
      }
    }
}
```
