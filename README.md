# 前端开发规范
---
[TOC]
---
## 代码规范

### `统一编码风格`
$\color{red}{强制}$使用[ESLint](https://eslint.org/)进行代码检查

采用严格标准的[Airbnb](https://github.com/airbnb/javascript)配置

### `命名规范`
*规范及准确的命名是代码重要的组成部分，代码可读性的基石，更是程序员最要的编码习惯。好的命名，可以使我们代码读起来像文章一样，行云流水。*
##### 变量
采用驼峰命名法，使用`let`, `const` 声明
使用`xxxxs` 或 `xxxList` 表示复数
e.g.

```js
let currentUser = null
const maxTagSelect = tags.length

let users = []
// or
let userList = []
```
##### 常量
单词大写并以下划线连接，使用常量代替代码中的`魔法数字`
e.g.
```js
// bad
if(status === '1') {
  // do sth when status '1'?
}

// good
const LIVE_STATUS = {
  START: '1',
  STOP: '2',
  REPLAY: '3'
}

if(status === LIVE_STATUS.START) {
  // logic with live is started
}

// bad
if(now - startTime > 86400) {
  // logic
}

//good
const ONE_DAY = 60 * 60 * 24

if(now - startTime > ONE_DAY) {
  //we know logic here is startTime passed one day
}

```
##### 方法、函数
采用驼峰命名规则，应准确表达方法内容
- 一般命名形如：`doSth`
- 事件监听形如: `onEventName` `handleEventName`
- 返回布尔值时，命名规则遵循布尔值变量命名
- `getter` `setter` 固定使用`getXxxx` `setXxxx` 

##### 类，构造函数，React组件
采用大写驼峰命名(Pascal Case)
略

##### 布尔值
- 通常使用`is + xxxx`形式
- 有时组件或配置参数使用`xxx + able`表达更贴近含义
- 与动词配合： ` can + verb` ` has + verb`
##### 文件及目录


### `JS规范`

##### 使用简洁的语法
##### 使用声明式语句
##### 避免嵌套


### `Style规范 `
##### Less
- `主题颜色`、`系统边距`等应统一定义和使用`全局变量`
- 类命嵌套保持一定的`HTML`结构，但避免嵌套过深，一般小于三层
- 尽量使用`类`作为选择器，$\color{red}{禁止}$使用`id`, 避免使用元素标签`div` `p` `span` 等,特殊情形如对表格,列表等循环结构，修饰可以使用`td` `th` `thead` `li` 等标签，但也必须包裹外层样式

##### 全局样式
- 管理中台规范相对统一及固定，尽量使用全局样式系统(flex, 边距，字号，颜色等)，少写样式。
- 移动端页面设计变化相对较多，尽量通过Mixin方法样式复用
- $\color{red}{禁止}$页面内对全局样式直接覆盖，可以通过包裹外层样式避免全局污染

##### 页面使用Css Module
- 统一使用`webpack`提供的`module` 方案
- 类名使用驼峰命名规则
- 不嵌套或浅层嵌套(2层)
- `标签选择器`必须包裹外层类名(标签名不会进行哈希处理)

##### 公共组件样式
- 不使用`css module`, 使用组件样式进行包裹
- 尽量使用css、less, 避免`inline style`, 方便使用者覆盖
- 外部传入的`class` `style` 通常应作用于组件最外层元素

e.g.

```js

  class SomeComponennt extends Component {
    render () {
      const { className, style } = this.props
      return (
        <div
          style={style}
          className={classnames('some-function-comp', className)}
        >
          {/* */}
        </div>
      )
    }
  }

```
style.Less

```less

  .some-function-comp {
    .some-part {
      // style
    }
    .other-part {
      // style
    }
  }

```

### `React风格`

### `公共方法及公共组件`
*逻辑复用，减少重复代码是软件开发的基本原则之一，提取公共方法，复用组件则是这个原则最常见的实践，不仅提升我们的开发效率，更是代码维护性的要求*

### `注释规范`


```js

```

## 工作流规范
---

### `工作流程`

### `Git规范`

### `Code Review`