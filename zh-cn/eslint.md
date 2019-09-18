# EsLint 规则约定

> [ESlint 配置文件](./.eslintrc)

> [ESlint 忽略文件](./.eslintignore)

> [ESlint 配置文件使用到的 airbnb 扩展](https://github.com/airbnb/javascript)

> [ESlint 配置文件使用到的 prettier 扩展](https://github.com/prettier/eslint-config-prettier/blob/master/index.js)

> [ESlint 配置文件使用到的 prettier/react 扩展](https://github.com/prettier/eslint-config-prettier/blob/master/react.js)

> [ESlint 配置文件使用到的 react 插件](https://github.com/yannickcr/eslint-plugin-react)

> [ESlint 配置文件使用到的 compat 插件](https://github.com/amilajack/eslint-plugin-compat)

> [ESlint 配置文件使用到的 promise 插件](https://github.com/xjamundx/eslint-plugin-promise)

> [ESlint 配置文件使用到的 import 插件](https://github.com/benmosher/eslint-plugin-import)

### 编码中常用的规则

1. 要求 let 或 const 代替 var, 不可重复声明， 需重新赋值的使用 let, 否则使用 const , 优先使用解构语法。
1. 函数需要按照生命周期顺序， 每个函数之间要有空行。
1. props 要提前声明， 非必填需要设置默认值
1. import 需要安顺序引入, React > 第三方库 > 自定义组件 > 样式
1. 变量， porps, state 声明后需要使用，无用的变量需要删除
1. 数组遍历 dom,需要设置`唯一key`, 不建议使用 index。
1. if else 不能写空代码块， if return 之后， 不要在写 else
1. render 函数中 js 中的 html 需要使用（）包裹
1. 空标签需要使用`自闭合标签`
1. 除 html 属性以外，其他地方都需要使用`单引号`
1. 使用 `===` 或 `！==`
1. promise 需要捕捉错误
1. 禁止多个空行

### extends vs pluhin

```js
  extends(扩展)
  //extends属性值可以是一个字符串或字符串数组
  //数组中每个配置项继承它前面的配置
  //可选的配置项如下
  //1.字符串eslint：recommended，该配置项启用一系列核心规则，这些规则报告一些常见问题，即在(规则页面)中打勾的规则
  //2.一个可以输出配置对象的可共享配置包，如eslint-config-standard
    //可共享配置包是一个导出配置对象的简单的npm包，包名称以eslint-config-开头，使用前要安装
    //extends属性值可以省略包名的前缀eslint-config-
  //3.一个输出配置规则的插件包，如eslint-plugin-react
    //一些插件也可以输出一个或多个命名的配置
    //extends属性值为，plugin：包名/配置名称
  //4.一个指向配置文件的相对路径或绝对路径
  //5.字符串eslint：all，启用当前安装的ESLint中所有的核心规则
    //该配置不推荐在产品中使用，因为它随着ESLint版本进行更改。使用的话，请自己承担风险
```

```js
plugin(插件);
// ESLint 支持使用第三方插件
// 在使用插件之前，你必须使用 npm 安装它
// 全局安装的 ESLint 只能使用全局安装的插件
// 本地安装的 ESLint 不仅可以使用本地安装的插件还可以使用全局安装的插件
//plugin 与 extend 的区别：extend 提供的是eslint 现有规则的一系列预设
//而 plugin 则提供了除预设之外的自定义规则，当你在 eslint 的规则里找不到合适的的时候就可以借用插件来实现了
```
