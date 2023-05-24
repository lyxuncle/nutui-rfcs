- 开始日期：2023-05-24
- 目标主要版本：NutUI-React 2.0 / NutUI-React-Taro 2.0
- 参考问题Issues：

# 概括

制定统一的规范，提高组件的使用体验，优化或扩展组件的功能。


# 基本示例

代码示例基本和 NutUI-React 网站给出的一致。


# 动机

- 组件 Props 的指向性不强，从直接感受上不能很好的理解其用途。
- 存在一些冗余的 Props，多个 Props 实现类似的功能。
- 组件之间的 Props 名称不统一，组件 Props 记忆成本高，使用体验不流畅。
- 组件并未清晰划分受控和非受控。
- 样式文件存在冗余内容。


# 详细设计


OverLay:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| visible | 当前组件是否显示 | boolean |  |  |
| zIndex | 遮罩层级 | number | 2000 | 统一看全局组件，给出z-index层级关系。 |
| duration | 动画时长，单位秒 | number | 0.3 |  |
| overlayClass | 自定义遮罩类名 | string | - | 改成 className，统一处理 |
| overlayStyle | 自定义遮罩样式 | cssproperties | - | 改成 style，统一处理 |
| lockScroll | 背景是否锁定 | boolean |  | 默认值改为 true |
| closeOnClickOverlay | 是否点击遮罩关闭 | boolean | true | 改成 closeOnOverlayClick |
| onClick | 点击时触发 | `event: event` |  |  |
|  |  |  |  | 增加这两个回调处理  afterClose 完全关闭后触发 () => void -  afterShow 完全展示后触发 () => void - |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

