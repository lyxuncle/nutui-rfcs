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


List:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| sourceData | 获取数据 | array | - | 改 list |
| containerSize | 容器高度 | number | 获取元素的 offsetWidth 或 offsetHeight，需要 css 给出 | 改成 containerHeight |
| ItemRender | virtual 列表父节点渲染的函数 | react.fc | - |  |
| itemSize | item高度，如果不定高，则为首屏单个最大size | string | - | 改成 itemHeight |
| itemEqualSize | item大小是否一致 | boolean | true | itemEqual |
| overscan | 除了视窗里面默认的元素, 还需要额外渲染的item个数 | number | 2 | ？ |
| key | 唯一值 ,Item(sourceData)具体的某个唯一值的字段 | string | index |  |
| horizontal | 决定列表是横向的还是纵向的 | boolean |  | direction |
| onScroll | 滑动到底(右)的事件，可以实现无限滚动 | - |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

