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


Swipe:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| name | 标识符，可以在事件参数中获取到 | number | string | - |  |
| leftWidth | 指定左侧滑动区域宽度，单位为 `px` | number | string |  | 删掉 |
| rightWidth | 指定右侧滑动区域宽度，单位为 `px` | number | string |  | 删掉 |
| leftAction | 左侧滑动区域的内容 | reactnode | - |  |
| rightAction | 右侧滑动区域的内容 | reactnode | - |  |
| beforeClose | 关闭前的回调函数，返回 `position` | string | left |  |
| disabled | 是否禁用滑动 | boolean |  |  |
| onOpen | 打开单元格侧边栏 | `name: string, position: 'left' | 'right'` |  | 滑动方向给用户的有问题，看看 |
| onClose | 收起单元格侧边栏 | `name: string, position: 'left' | 'right'` |  |  |
| onActionClick | 点击左侧或者右侧时触发 | `event: event, position: 'left' | 'right'` |  |  |
| onTouchStart | onTouchStart | `event: event` |  |  |
| onTouchMove | onTouchMove | `event: event` |  |  |
| onTouchEnd | onTouchEnd | `event: event` |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

