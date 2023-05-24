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


NoticeBar:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| list | 纵向滚动数据列表 | array | [] |  |
| speed | 滚动的速度 | number | 50 |  |
| standTime | 停留时间(毫秒) | number | 1000 | 改为 duration |
| complexAm | 稍复杂的动画，耗能会高 | boolean |  | 建议废弃 |
| height | 每一个滚动列的高度(px)，注意：在使用 slot 插槽定义滚动单元时，按照实际高度修改此值 | number | 40 | 该属性需要与closeable的样式同步。 |
| closeMode | 是否启用右侧关闭图标，可以通过slot[name=rightIcon]自定义图标 | boolean |  | 改为 closeable |

direction=vertical:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| default | 通知文本的内容 |  |  | 删 slots，暂无使用该属性，文档中删除，代码里直接使用 children。 |
| rightIcon | 自定义右侧图标 |  |  |  |
| leftIcon | 自定义左侧图标，垂直滚动模式下默认无左侧图标，配置后展示，配置为"close" |  |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

