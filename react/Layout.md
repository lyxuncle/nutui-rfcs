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


Layout:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| type | 布局方式，可选值为flex | string | - |  |
| gutter | 列元素之间的间距（单位为px） | string | number |  |  |
| justify | Flex 主轴对齐方式，可选值为 start end center space-around space-between | string | start |  |
| align | Flex 交叉轴对齐方式，可选值为 flex-start center flex-end | string | flex-start |  |
| wrap | Flex是否换行，可选值为 nowrap wrap reverse | string | nowrap |  |
| onClick | 点击时触发 | `event: mouseevent, type: 'row' | 'col'` |  |  |

row:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| span | 列元素宽度（共分为24份，例如设置一行3个，那么span值为8） | string | number | 24 |  |
| offset | 列元素偏移距离 | string | number |  |  |
| onClick | 点击时触发 | `event: mouseevent, type: 'row' | 'col'` |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

