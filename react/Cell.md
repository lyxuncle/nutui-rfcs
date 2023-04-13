- 开始日期：2023-04-11
- 目标主要版本：NutUI-React 2.0 / NutUI-React-Taro 2.0
- 参考问题Issues：

# 概括

制定统一的规范，提高组件的使用体验，优化或扩展组件的功能。


# 基本示例

代码示例基本和 NutUI-React 网站给出的一致。


# 动机


- 因使用率低，开发者改动成本低：
    - 去掉点击效果 isLink、单元格大小 size；
    - 去掉可由CSS变量设定的样式属性，并保留之前的默认值，如 roundRadius等；
- 修改属性为更通用、易记忆属性名，如desc改为 description，如center改为 align，支持更多值；
- 支持title、description、extra 自定义内容，整合现在的定制化很强的属性，如linkslot，使组件更加灵活通用。


# 详细设计


Cell(Card):

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| title | 分组标题 | string | - | 保留，改为 string | React.Node 类型 |
| desc | 分组描述 | string | - | 7. desc 改为 description |
| titleSlot | 自定义`title`标题区域 | reactnode | - | 8. title 和 description 改为 React.Node 类型，去掉 titleSlot 和 descSlot |
| descSlot | 自定义`desc`描述区域 | reactnode | - | 删 |

CellGroup:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| title | 标题名称 | reactnode | - |      |
| subTitle | 左侧副标题 | reactnode | - | 4. subTitle 改为 description |
| desc | 右侧描述 | string | - | 1. desc 改为 extra  2. extra 改为 React.Node 类型，去掉 isLink、url、linkSlot、replace   |
| descTextAlign | 右侧描述文本对齐方式 [text-align](https://www.w3school.com.cn/cssref/pr_text_text-align.asp)，只展示
desc 时可用 | string | right | 5. descTextAlign 改为 extraAlign，还是直接去掉呢？  结论是：直接去掉 |
| isLink | 是否展示右侧箭头并开启点击反馈 | boolean |  | 删 |
| replace | 是否在跳转时替换当前页面历史 | boolean |  | 删 |
| roundRadius | 圆角半径 | string | 6px | 3. 改为 radius |
| url | 点击后跳转的链接地址 | string | - | 删 |
| icon | 左侧 [图标名称](#/icon) 或图片链接 | string | - | 删，放在title 节点中 |
| center | 是否使内容垂直居中 | boolean |  | 6. center 去掉，改为 align，默认 flex-start。 |
| size | 单元格大小，可选值为 `large` | string | - | 删 |
| linkSlot | 自定义右侧`link`区域 | reactnode | - | 删 |
| onClick | 点击事件 | `event: react.mouseevent<htmldivelement, globalthis.mouseevent>` |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

