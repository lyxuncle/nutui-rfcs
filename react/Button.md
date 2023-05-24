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


Button:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| type | 类型，可选值为 `primary` `info` `warning` `danger` `success` | string | default | 1. 改为 antd 的 color  2. type 改为 button 的 type值，参考 antd mobile    5. 添加Ref nativeElement   原始 button 元素 HtmlButtonElement | null  参考 antd    增加 formType 默认值  button ？@裴新宇   适用于 H5 以及 Taro-H5，避免一些 form 内使用的 bug |
| size | 尺寸，可选值为 `large` `small` | string | normal |  |
| shape | 形状，可选值为 `square` | string | round |  |
| color | 按钮颜色，支持传入 linear-gradient 渐变色 | string | - |  |
| plain | 是否为朴素按钮 | boolean |  | 3.删除 plain，改为 fill 模式，参考antd |
| disabled | 是否禁用按钮 | boolean |  |  |
| block | 是否为块级元素 | boolean |  |  |
| loading | 按钮loading状态 | boolean |  |  |
| icon | 按钮图标，同Icon组件name属性 | string | - |  |
| onClick | 点击按钮时触发 | `event: mouseevent` |  |  |
|  |  |  |  | 5. 添加Ref nativeElement   原始 button 元素 HtmlButtonElement | null  参考 antd |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

