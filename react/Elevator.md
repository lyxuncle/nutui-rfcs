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


Elevator:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| height | 电梯区域的高度 | number | string | 200px |  |
| acceptKey | 索引 key 值 | string | title | 改为 floorKey |
| indexList | 索引列表 | array（item 需包含 id、name 属性, name 支持传入 html 结构） | [{id: 0, name: ''}] | 改为 list |
| isSticky | 索引是否吸顶 | boolean |  | 改为 sticky |
| spaceHeight | 右侧锚点的上下间距 | number | 23 |  |
| titleHeight | 左侧索引的高度 | number | 35 |  |
| onClickItem | 点击内容 | `key: string, item: { id: 0, name: '' }` |  |  |
| onClickIndex | 点击索引 | `key: string` |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

