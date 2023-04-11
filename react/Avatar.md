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


Avatar:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| size | 设置头像的大小，可选值为：large、normal、small，支持直接输入数字 | string | normal | css变量实现? avatarGroup也有 |
| shape | 设置头像的形状，可选值为：square、round | string | round | css变量实现? |
| bgColor | 设置 Icon、字符类型头像的背景色 | string | #eee | 删，Icon自定义 |
| color | 设置 Icon、字符类型头像的颜色 | string | #666 | 删，Icon自定义 |
| url | 设置图片类型头像的地址 | string | - |  |
| alt | 设置图片类型头像无法显示时的替代文本 | string | - |  |
| icon | 设置 Icon 类型头像图标, 类似 Icon 组件的 name 属性 | string | - | 改为ReactNode类型 |
| iconSize | [图标尺寸](#/icon) | string | number | 16 | 删，Icon自定义 |
| onActiveAvatar | 点击头像触发事件 | function | event | 改为onClick？ |
| onError | 图片加载失败的事件 | function | event |  |

Avatar:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| maxCount | 显示的最大头像个数 | number | string | - |  |
| maxContent | 头像数量超出时，会出现一个头像折叠元素。该元素内容可为...、more、+N。默认为 +N |  |  | ? |
| size | 设置头像的大小，可选值为：large、normal、small，支持直接输入数字 | string | +N | css变量实现? |
| shape | 设置头像的形状，可选值为：square、round | string | round | css变量实现? |
| maxBgColor | 设置 Icon、字符类型头像的背景色 | string | #eee | 删，Icon自定义 |
| maxColor | 设置 Icon、字符类型头像的颜色 | string | #666 | 删，Icon自定义 |
| span | 设置头像之间的间距 | string | -8 | css变量实现? 改为space？ |
| zIndex | 头像之间的层级关系，可选值为：left、right | string | left |  |
|  |  |  |  | 需要加fit吗？ |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

