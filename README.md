# 项目介绍

本项目是一个“前端基础知识点练习合集”，以一系列可直接打开运行的 `.html` 示例为主，覆盖 **HTML/CSS 布局练习** 与 **JavaScript 核心语法与浏览器 API（BOM/DOM/事件）**。

项目特点：

- 每个示例文件通常都是“单一主题 + 可运行代码”，适合按主题拆分学习
- 大部分示例依赖浏览器控制台输出（`console.log`），便于观察执行结果
- 文件名采用编号方式组织，天然形成一条从基础到进阶的学习路线

## 目录结构

- `css/`
  - `26.博客前台页面.html`：一个博客前台页面骨架，用于练习导航栏、Banner、卡片布局等
  - `博客后台框架.html`：一个后台管理页面骨架，用于练习侧边栏 + 内容区的经典布局
- `js/`
  - 以编号 `.html` 为主：按知识点拆分的 JavaScript 示例
  - `module/`
    - `m1.js`：ES Module 导出示例（`export` / `export default`）

## 快速开始（怎么运行）

1. 用 VS Code 打开本项目目录。
2. 直接双击打开任意 `.html`，或在 VS Code 中“在默认浏览器中打开”。
3. 打开浏览器开发者工具（DevTools）：
   - `Console`：查看日志输出（大量示例依赖这里）
   - `Elements`：观察 DOM 结构与属性变化（DOM/节点/事件相关示例）

运行注意：

- 涉及 `<script type="module">` 的示例（如 `js/24.模块化.html`）在“真正使用 `import` 导入本地模块”时，通常需要通过本地静态服务器访问（例如 VS Code 的 Live Server），否则可能遇到浏览器对本地文件 `file://` 的模块加载限制。
- `css/26.博客前台页面.html` 使用了外链图片资源；离线环境下图片可能无法加载，但不影响布局学习。

## 学习路线（推荐顺序）

建议以 `js/` 中的编号顺序为主线，从语法基础逐步过渡到浏览器与工程化概念：

1. JavaScript 基础（变量、数据类型、运算、控制流）
2. 函数与作用域、`this`
3. 对象与原型链、`class`
4. 正则、时间与定时器
5. 模块化（ESM）
6. BOM / Window 属性
7. DOM 获取与操作、节点操作
8. 事件、事件委托、默认行为与冒泡
9. 事件循环（宏任务/微任务）

如果你想先做“可视化成就感更强”的内容：可以先看 `css/` 下两个页面，再回到 `js/`。

## 文件索引（明细版：关键概念 + 关键 API/语法）

> 说明：本索引优先列出“文件里实际出现的 API/语法点”，方便你复习时精准定位。

### 1) 入门与数据类型（基础语法与类型转换）

| 文件 | 关键概念 | 关键 API/语法 |
| --- | --- | --- |
| `js/1.引入.html` | HTML 内联事件 + 最小 JS 结构 | `onclick`、`alert()`、`console.log()` |
| `js/2.变量声明和数据类型-number.html` | Number 表示与常用数值处理 | `Number()`、二/八/十六进制字面量、`typeof`、`toFixed()`、`Number.parseInt()`、`Number.isInteger()`、`Math.round/ceil/floor()` |
| `js/3.数据类型-string.html` | 字符串常用操作与查找 | `String()`、索引访问 `s[i]`、`indexOf()`、`split()`、`slice()`、`includes()`、`trim()` |
| `js/4.数据类型-boolean.html` | 真值/假值（truthy/falsy）与显式转换 | `Boolean()`（对 `0/1/""/" "/null/undefined/NaN/[]/{}` 的转换结果） |
| `js/5.数据类型-objec.html` | 对象属性读写、增删、计算属性名 | `obj.x` / `obj["x"]`、新增属性、`delete`、计算属性名 `{ [name]: value }` |
| `js/6.数据类型-null和undefined copy.html` | `null` / `undefined` 差异与类型转换 | 未初始化变量、读取不存在属性得到 `undefined`、`==` vs `===`、`Boolean()`、`Number()` |
| `js/7.数据类型-symbol和bigint.html` | Symbol 作为“不会冲突”的键、BigInt 基础 | `Symbol()`、对象计算属性名 `[sym]`、`===` 比较、`BigInt()`、`1002n`（BigInt 字面量） |

### 2) 数组与数组方法（增删改查 + 高阶函数）

| 文件 | 关键概念 | 关键 API/语法 |
| --- | --- | --- |
| `js/9.数组.html` | 数组访问与遍历、类型判断 | `Array()`、`.length`、`for`、`for...of`、`Array.isArray()`、`instanceof Array` |
| `js/10.数组方法.html` | 数组增删与排序（第一部分） | `push/pop/shift/unshift()`、`join()`、`sort()`（含比较函数）、`reverse()`、`splice()` |
| `js/11.数组方法2.html` | 数组高阶方法（第二部分） | `forEach/map/filter()`、`every/some()`、`find/findIndex()`（回调函数） |

### 3) 运算与流程控制（短路逻辑 / 条件 / 循环）

| 文件 | 关键概念 | 关键 API/语法 |
| --- | --- | --- |
| `js/12.逻辑运算符.html` | 逻辑与 `&&` 的短路判断 | `startsWith()`、`&&`、比较运算（如 `age >= 15`） |
| `js/13.判断语句.html` | “卫语句（Guard Clause）”风格的条件返回 | `function`、`if`、`return`（注意：示例里 `!scope >= 90` 属于容易踩坑的写法，建议写成 `scope >= 90` 或 `!(scope >= 90)`） |
| `js/14.循环语句.html` | 对象与数组的不同遍历方式 | `for...in`（对象 key） 、`for...of`（数组元素） |

### 4) 函数、this、对象与原型（从调用方式到 OOP）

| 文件 | 关键概念 | 关键 API/语法 |
| --- | --- | --- |
| `js/15.函数.html` | 箭头函数、IIFE、默认参数、剩余参数 | `()=>{}`、立即执行函数 IIFE、默认参数 `name = ...`、rest `...list`、`arguments` |
| `js/16.函数2.html` | 函数是一等公民、对象方法、递归扁平化数组 | 函数对象（打印函数 vs 调用）、数组存函数、对象方法三种写法、`this`（普通函数方法）、`instanceof Array`、递归、展开运算符 `...` |
| `js/17.this.html` | `this` 指向与 `call/apply/bind` | 普通函数调用/方法调用、箭头函数的 `this`、`Function.prototype.call/apply/bind`、`arguments`（示例打印） |
| `js/18.对象.html` | 对象创建方式、原型方法、属性枚举与判断 | 字面量、`new Object()`、构造函数 + `new`、`People.prototype`、`Object.create()`、`in`、`hasOwnProperty()`、`for...in`、`Object.keys()` |
| `js/19.对象2.html` | 浅拷贝与属性描述符 | `Object.assign()`（浅拷贝）、`Object.defineProperty()`、`writable/enumerable/configurable`、`Object.keys()`、`Object.getOwnPropertyNames()` |
| `js/20.原形.html` | 原型链、`__proto__`、手写 `new` | 修改 `Object.prototype`、重写 `toString`、`Object.create()`、`__proto__`、构造函数、`apply()`、自定义 `_new(fn, ...args)` |
| `js/23.class.html` | class 语法、继承与静态成员 | `class`、字段、`constructor`、实例方法、`extends/super`、`static` 属性/方法 |

### 5) 常用能力：时间 / 正则 / 模块化

| 文件 | 关键概念 | 关键 API/语法 |
| --- | --- | --- |
| `js/21.时间.html` | Date 常用字段、格式化、时间差计算 | `new Date()`、`getTime/getFullYear/getMonth/getDate/getHours/getMinutes/getSeconds/getDay`、`padStart()`、`setDate/setHours`、`Math.floor()` |
| `js/22.正则表达式.html` | 正则字面量与构造、分组替换、命名分组 | `/.../g`、`new RegExp()`、`search/match`、`replace/replaceAll`、字符类、捕获分组 `$1/$2`、`exec()`、命名分组 `(?<phone>...)` |
| `js/24.模块化.html` | `<script type="module">` 与模块化思路 | `type="module"`、（注释中的）`import` 语法示例、工厂函数返回对象（模拟模块） |
| `js/module/m1.js` | ESM 导出方式（被 `js/24` 引用） | `export function ...`、`export const ...`、`export default ...` |

### 6) 浏览器相关：BOM / 定时器 / 性能小技巧

| 文件 | 关键概念 | 关键 API/语法 |
| --- | --- | --- |
| `js/25.BOM.html` | History 前进/后退/跳转 | `history.forward/back/go`、`onclick` |
| `js/26.定时器.html` | 定时器与清理、循环计数退出 | `setTimeout/clearTimeout`、`setInterval/clearInterval`、箭头函数、`new Date().toLocaleString()` |
| `js/27.防抖和节流.html` | 防抖/节流实现（高频事件） | 闭包保存 `timer/t1`、`clearTimeout`、`setTimeout`、`Date.now()`、`fn.apply(this, arguments)` |
| `js/28.window界面属性.html` | 视口/窗口/屏幕、滚动、浏览器信息 | `window.innerWidth/innerHeight`、`window.outerWidth/outerHeight`、`window.screen`、`scrollTo/scrollBy`、`navigator.userAgent/appName/appVersion/platform` |

### 7) DOM 与事件（获取/属性/样式/节点/事件模型）

| 文件 | 关键概念 | 关键 API/语法 |
| --- | --- | --- |
| `js/29.dom-1.html` | DOM 获取 + 属性读写 | `getElementById/getElementsByClassName`、`querySelector/querySelectorAll`、`tagName`、`getAttribute/setAttribute/removeAttribute` |
| `js/30.dom-2.html` | `data-*` 与 classList | `dataset`、`delete dom.dataset.x`、`getAttribute("data-...")`、`classList.add/remove/toggle/contains/replace` |
| `js/31.dom-3.html` | DOM 内容读写 + 样式读写 | `innerText/innerHTML/outerHTML`、`element.style.xxx`、`getComputedStyle()` |
| `js/32.节点操作.html` | 创建/插入/删除节点与父子关系 | `document.createElement()`、`append/appendChild`、`insertBefore`、`before/after`、`removeChild/remove`、`.children`、`.parentNode` |
| `js/33.事件.html` | 事件绑定、冒泡、默认行为、委托 | `oninput`、`onclick`、`addEventListener/removeEventListener`、`stopPropagation()`、`preventDefault()`、`confirm()`、`event.target` |
| `js/34.事件循环.html` | 宏任务/微任务执行顺序 | `setTimeout`（宏任务）、`Promise.resolve().then(...)`（微任务） |

### 常见坑点（复习时可以顺手改一改验证理解）

1. 条件判断优先级：`!scope >= 90` 会先算 `!scope` 再比较，通常不是你想要的效果；建议写成 `scope >= 90` 或 `!(scope >= 90)`。
2. `bind` 不会立即执行：`fn.bind(obj)` 会返回“新函数”，需要再调用一次才会真正运行。
3. 模板字符串要用反引号：如果写了 `${...}`，外层必须是 `` `...` ``，用普通引号不会插值。

## CSS 页面练习说明

- `css/26.博客前台页面.html`
  - 布局关键词：`flex`、固定导航 `position: fixed`、Banner 覆盖文案（绝对定位 + `transform` 居中）、左右栏布局、卡片样式
  - 适合练习：常见门户/博客首页结构拆分
- `css/博客后台框架.html`
  - 布局关键词：侧边栏 + 主内容区 `flex`、`calc()` 计算高度、内容区 `overflow-y: auto` 可滚动
  - 适合练习：管理后台通用框架搭建

## 适用人群

- 前端零基础/初学者：希望用“可运行示例”理解概念
- 复习者：需要快速定位某个知识点对应的代码
- 有一点基础的同学：可把这些示例当作自己的“知识点回忆录/模板库”

## 建议的使用方式（最高效）

- 每学习一个文件：
  1) 先运行看结果（控制台/页面变化）
  2) 再改动 1~2 行代码验证理解（例如改参数、改选择器、改事件绑定方式）
  3) 最后做小总结：记下“何时用、坑点是什么”
- DOM/事件相关建议配合 DevTools：
  - `Elements` 面板观察属性变化
  - `Console` 面板观察事件对象 `event` 与 `event.target`
