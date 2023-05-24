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


FixedNav:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| fixednavClass | 自定义类名 | string | fixednav | 改为 className，统一处理 |
| visible | 是否打开 | boolean |  |  |
| navList | 悬浮列表内容数据 | array | [] | 改为 list |
| activeText | 收起列表按钮文案 | string | 收起导航 |  |
| unActiveText | 展开列表按钮文案 | string | 快速导航 | 改为 inactiveText |
| type | 导航方向,可选值 left right | string | right |  |
| overlay | 展开时是否显示遮罩 | boolean | true |  |
| position | fixed 垂直位置 | object | {top: 'auto', bottom: 'auto'} |  |
| slotList | 自定义展开列表内容 | htmlelement | - | 改为 children |
| slotBtn | 自定义按钮 | htmlelement | - | 改为 content |
| onChange | 展开收起按钮回调 | `value: boolean` |  |  |
| onSelected | 选择之后触发 | `item, event: mouseevent` |  | 改为 onSelect |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

