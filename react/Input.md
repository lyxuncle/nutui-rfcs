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


Input:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| slotButton | 自定义输入框尾部按钮 |  |  | 删 |
| slotInput | 自定义输入框，使用此插槽后，与输入框相关的属性和事件将失效 |  |  | 删 |
| onChange | 输入框内容变化时触发 | `val, event` |  |  |
| onFocus | 输入框聚焦时触发 | `val, event` |  |  |
| onBlur | 输入框失焦时触发 | `val, event` |  |  |
| onClear | 点击清除按钮时触发 | `val, event` |  |  |
| onClick | 点击组件时触发 | `val, event` |  | 点击输入区域时触发 |
| onClickInput | 点击输入区域时触发 | `val, event` |  | 删 |
| onClickLeftIcon | 点击左侧图标时触发 | `val, event` |  | 删 |
| onClickRightIcon | 点击右侧图标时触发 | `val, event` |  | 删 |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

