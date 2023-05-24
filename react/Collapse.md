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


Collapse:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| activeName | 当前展开面板的 name | 手风琴模式：string | number 非手风琴模式：(string | number)[] | - | 改 activeKey  与 item 上的 name 保持一致，activeName 未修改 @裴新宇  |
| accordion | 是否开启手风琴模式 | boolean |  |  |
| icon | 图标链接/或使用 NutUI 的 icon | string | - | 改为 expandIcon，类型改为 ReactNode  已完成状态 |
| iconSize | 图标大小 | string | 16px | 删 |
| iconColor | 图标颜色 | string | - | 删 |
| rotate | 点击折叠和展开的旋转角度,在自定义图标模式下生效 | string | number | 180 |  |
| onChange | 切换面板时触发 | isopen:是否打开状态；name：当前点击的name值 |  |  |

Collapse:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| name | 唯一标识符，必填 | string | number | - | 改为 key？？？待办  key 不合法，未修改 @裴新宇  |
| title | 标题栏左侧内容 | string | - |  |
| disabled | 标题栏是否禁用 | boolean |  |  |
| isOpen | 是否展开 | boolean |  | 改为 opened   变更为函数类型，名称为 isOpen @裴新宇  |
| childnull |  |  |  | 改为 children ？？  已删除 @裴新宇  |
| subTitle | 标题栏副标题 | string | - | 改为 extra |
| titleIcon | 标题图标链接/或使用 NutUI 的 icon | string | - | 改为 expandIcon |
| titleIconColor | 标题图标颜色 | string | - | 删 |
| titleIconSize | 标题图标大小 | string | - | 删 |
| titleIconPosition | 标题图标位置 | string | - | 删 |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

