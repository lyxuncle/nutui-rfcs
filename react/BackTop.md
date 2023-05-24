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


BackTop:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| elId | 获取监听元素的父级元素 | string | - | 改为 target  支持选择器 or 仅 id 选择器 |
| bottom | 距离页面底部距离 | number | 20 | 删  style 支持 left、right、top、bottom |
| right | 距离页面右侧距离 | number | 10 | 删 |
| distance | 页面垂直滚动多高后出现 | number | 200 | threshold |
| zIndex | 设置组件页面层级 | number | 10 |  |
| isAnimation | 是否有动画,和 duration 参数互斥 | boolean | true | 删 duration={0} |
| duration | 设置动画持续时间 | number | 1000 |  |
| onClick | 按钮点击时触发事件 | `event: mouseevent` |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

