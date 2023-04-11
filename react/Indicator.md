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


Indicator(PageIndicator):

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| current | 当前步骤 | number | 1 |  |
| size | 步骤长度 | number | 3 | 改为 total |
| block | 是否启用块级布局 | boolean |  | 删 |
| align | 对齐方式，仅在block为true时生效, 可选值 'left', 'right', 'center' | string | left | 删 |
| fillZero | 单数前面是否补0 | boolean | true | 改为 方法，返回 可扩展的node节点 |
| vertical | 是否竖向展示 | boolean |  | 改成 direction，默认horizontal，可选 'horizontal' | 'vertical' |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

