# vue3
## 初始化项目
- vite

## 从vue2的迁移
1. composition API
    - setup 
    - reactive
    创建响应式的变量
    - computed
    计算属性
    - ref 
    声明一个单值的变量
    - onMounted,
    - onUnmounted,
    - watch,
    侦听器
    - toRefs,

2. Teleport

3. Fragments
    vue3中组件可以拥有对个根

4. 自定义事件 Emits Component Option
    vue3 中组件发送的自定义事件需要定义在emits选项中：
    - 原生事件会触发两次,比如click
    - 更好的指示组件工作
    - 对象形式事件校验

5. 自定义渲染器 custom renderer
    vue3.0中支持自定义渲染器（Renderer):这个API可用来自定义渲染逻辑。比如下面的案例我们可以把数据渲染到canvas上。
    首先创建一个组件描述要渲染的数据，我们想要渲染一个叫做piechart的组件，我们不需要单独声明该组件，因为我们只是想把它携带的数据绘制到canvas上。创建CanvasApp.vue



