- 开始日期：2023-04-11
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


TextArea:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| defaultValue | 初始默认值，支持双向绑定 | string | - | value受控 |
| placeholder | 设置占位提示文字 | string | 请输入内容 |  |
| maxlength | 限制最长输入字符 | string | number | - | maxLength |
| rows | textarea 的高度 | string | number | 2 | 可以理解为行数 |
| limitshow | textarea 是否展示输入字符。须配合`max-length`使用 | boolean |  | ?showCount? |
| autosize | 高度是否可拉伸 | boolean |  | autoSize |
| textAlign | 文本位置,可选值`left`,`center`,`right` | string | left | css变量控制 |
| readonly | 只读属性 | boolean |  | 原生属性textarea：理论上都支持用户传入   autoComplete autoFocus disabled readOnly onFocus   onBlur onCompositionStart onCompositionEnd onClick |
| disabled | 禁用属性 | boolean |  |  |
| onChange | 输入内容时触发 | `val` |  |  |
| onFocus | 聚焦时触发 | `val` |  |  |
| onBlur | 失焦时触发 | `val` |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

