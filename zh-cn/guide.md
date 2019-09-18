## 包管理工具

> 首选使用 yarn，请先搭建 yarn :https://yarnpkg.com/zh-Hans/

已经装了 node 下，可以直接执行以下命令安装 yarn ：

```
 npm i yarn -g
```

## 首次启动前准备

```
yarn
```

## 启动

```
yarn start
```

## 打包构建

```
yarn build
```

## 文档生成 (后续集成到webpack, 目前库有bug)

```
yarn docs
```

## 项目目录

```json
- .vscode              —— vsCode 设置
- app
  - components         —— 组件目录(子目录大驼峰命名)
    - Base                —— 基础组件(UI组件, 组件示例,其他组件参考此处)
      -BaseCompName          —— xx组件目录
        - less                —— xx组件样式目录
          + baseCompName.less    —— xx 组件样式名称(小驼峰组件名命名)
        - images              —— xx组件静态图片
        - data                —— 其他静态数据(不常用)
        + index.js            —— xx组件导出文件
        + BaseCompName.js     —— xx组件代码
    - Commom              —— 通用组件(轻逻辑, 低耦合组件， Q为前缀)
    - HOC                 —— 高阶组件
    - CompontsName        —— 业务组件(不可复用, 高耦合)
  + config           —— 本地服务配置目录
    + api.js             —— 接口地址配置
    + index.js           —— 接口域名配置
  + static           —— 静态资源目录
  + test             —— 单元测试目录
  + redux            —— redux
    - reducers.js        —— 组合模块化reducer
    - sagas.js           —— saga 运行参数
  + store            —— redux store
    - configureStore.dev.js   —— stroe 开发配置
    - configureStore.js        —— stroe 开发配置
    - configureStore.prod.js    —— stroe 开发配置
  - utils            —— 公用工具类
    +ReduxReqs.js    —— 异步请求封装(reducer, saga, action 等)
+ configs         —— webpack 配置
+ .editorconfig   ——  部分格式化规则
- test            ——  测试目录
- package.json    ——  项目配置(热启动, 打包等)
- yarn.lock       ——  依赖版本控制
- CHANGELOG.md    ——  更新日志
```

## 项目规范

### 目录规范

> 请参考项目目录

### 组件规范

#### 组件目录

- Base 放置基础组件, 特点是 UI 为主, 无业务逻辑(Base前缀); Common 通用组件, 轻业务逻辑,低耦合, 可以复用（Q前缀）;HOC 高阶组件; ComponentName 业务组件, 不可复用
- 组件目录下需要写`index.js`导出该组件, `组件名.js`写组件业务逻辑, less 作为样式目录,less 下文件用小驼峰`组件名.less`文件, images 放置图片等静态文件, 如果需要子组件,则直接在该目录下写子`组件名.tsx`

#### 命名规范

- 采用 Pascal(大驼峰)命名组件, 例如`ComponentName`, 除组件名之外其他均采用小驼峰命名
- 组件内 事件方法使`hanleXxxx`, 组件属性方法使用 onXxxxxx
- 有意义的名词、简短、具有可读性

#### 组件顺序

1.  静态方法 和 属性
2.  生命周期方法顺序: `displayName`, `propTypes`, `contextTypes`, `childContextTypes`, `mixins`, `statics`, `defaultProps`, `constructor`, `getDefaultProps`, `state`, `getInitialState`, `getChildContext`, `getDerivedStateFromProps`, `componentWillMount`, `UNSAFE_componentWillMount`, `componentDidMount`, `componentWillReceiveProps`, `UNSAFE_componentWillReceiveProps`, `shouldComponentUpdate`, `componentWillUpdate`, `UNSAFE_componentWillUpdate`, `getSnapshotBeforeUpdate`, `componentDidUpdate`, `componentDidCatch`, `componentWillUnmount` (按照此顺序).
3.  自定义方法
4.  `render` 方法

> 组件属性需要提前声明(命名,类型), 并设置默认值.

#### 其它

- 组件通过数组遍历 dom 时,需要添加 key 属性作为唯一标识,优化性能.
- 代码格式相关(缩进, 换行, 对齐等),参考 ESLint 规范.

#### 组件样式

- 使用 less 书写组件样式
- 使用命名空间,避免全局变量污染

## 相关文档

> [ESLint 规则文档](./eslint.md)

> [VsCode 插件目录](./vscodePlugin.md)
