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


Navbar:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| title | 标题名称 | string | - | 改为 children，ReactNode |
| desc | 右侧描述 | string | - | 改为 right，React.Node   并且增加 left，ReactNode |
| leftShow | 是否展示左侧箭头 | boolean | true | 改为 back，React.Node |
| leftText | 左侧文案 | string | - | 改为 back，React.Node |
| fixed | 是否固定 | boolean |  |  |
| safeAreaInsetTop | 是否适配安全区 | boolean |  | 改为 safeArea |
| border | 是否显示底部边框 | boolean |  | 删 |
| placeholder | 固定在顶部时，是否在标签位置生成一个等高的占位元素 | boolean |  |  |
| zIndex | 导航栏层级 | number | string | 10 |  |
| style | 容器样式 | cssproperties | {} |  |
| className | 容器类名 | string | - |  |
| onClickTitle | 点击标题事件 | `event: event` |  | 删除 |
| onClickRight | 点击右侧事件 | `event: event` |  | 删除 |
| onClickBack | 点击返回事件 | `event: event` |  |  |
| onClickIcon | 点击标题右侧icon事件 | `event: event` |  | 删掉 |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

