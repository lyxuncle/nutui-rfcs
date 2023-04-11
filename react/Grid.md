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


Grid:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| columnNum | 列数 | number | string | 4 | 改成 columns |
| iconSize | 图标大小，如 `20px` `2em` `2rem` | number | string | 28px | 删 |
| iconColor | 图标颜色 | string | - | 删 |
| border | 是否显示边框 | boolean | true | 删, item classname 设置 |
| gutter | 格子之间的间距，默认单位为`px` | number | string |  |  |
| center | 是否将格子内容居中显示 | boolean | true |  |
| square | 是否将格子固定为正方形 | boolean |  |  |
| reverse | 内容翻转 | boolean |  |  |
| direction | 格子内容排列的方向，可选值为 `horizontal` | string | vertical |  |
| onClick | 宫格子项点击事件 | 点击当前项, 索引 |  |  |

Grid:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| text | 文字 | string | reactnode | - |  |
| fontSize | 文字大小 | string | number | - | 删 |
| color | 文字颜色 | string | - | 删 |
| icon | [图标名称](#/icon) 或图片链接 | string | reactnode | - | 删 |
| iconSize | 图标大小，如 `20px` `2em` `2rem` | number | string | 28px | 删 |
| iconColor | 图标颜色 | string | - | 删 |
| onClick | 点击格子时触发 | `event: event` |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

