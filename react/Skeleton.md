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


Skeleton:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| loading | 是否显示骨架屏(true不显示骨架屏，false显示骨架屏) | boolean | true | 改为 visible，备注：提取一下 css 变量 |
| width | 每行宽度(px单位) | string | 100px | 改成 css 变量 |
| height | 每行高度(px单位) | string | 100px | 改成 css 变量 |
| animated | 是否开启骨架屏动画 | boolean |  |  |
| avatar | 是否显示头像 | boolean |  |  |
| avatarShape | 头像形状：正方形/圆形 | string | round |  |
| avatarSize | 头像大小 | string | 50px |  |
| round | 标题/段落是否采用圆角风格 | boolean |  | 删除，标题和段落的圆角设置通过 css 变量控制 |
| row | 设置段落行数 | string | 1 | 改成 rows |
| title | 是否显示段落标题 | boolean | true |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

