# MicroFrame

基于[@micro-zoe/micro-app](https://www.npmjs.com/package/@micro-zoe/micro-app)的`iframe`模式结合[comlink](https://www.npmjs.com/package/comlink)的通信方案实现的高效、轻量级微前端框架。

## 使用方式

### 主应用

1. 安装依赖
```sh
pnpm add micro-frame
```

2. 在入口文件引入
```ts
// main.js
import microFrame from 'micro-frame'

microFrame.start()
```

3. 在页面中嵌入微前端应用
```html
<!-- 👇 name为应用名称，url为应用地址 -->
<micro-frame name="my-app" url="http://localhost:3000/"></micro-frame>
```

### 子应用
> 若是子应用不关心是否使用页面文档全部区域则无需进行任何设置！

1. 在入口文件引入
```ts
// main.js
import microFrame from 'micro-frame/micro'

let micro: microFrame.MicroApp | null = null
microFrame.init().then((app) => {
  micro = app
  // 启动子应用
})
```
