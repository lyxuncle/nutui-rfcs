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


Progress(ProgressBar):

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| percentage | 百分比 | number |  |  |
| isShowPercentage | 是否需要展示百分号 | boolean | true |  |
| fillColor | 进度条填充颜色 | string | #f3f3f3 |  |
| strokeColor | 进度条线条背景色 | string | linear-gradient(135deg, #fa2c19 0%, #fa6419 100%) |  |
| strokeWidth | 进度条宽度 | string | - |  |
| size | 进度条及文字尺寸，可选值`small` `base` `large` | string | base |  |
| showText | 是否显示进度条文字内容 | boolean | true |  |
| textInside | 进度条文字显示位置(`false`外显，`true`内显) | boolean |  |  |
| textColor | 进度条文字颜色设置 | string | 外显`#333` 内显`#fff |  |
| textWidth | 进度条文字宽度 | string | 35px |  |
| textBackground | 进度条文字背景颜色设置 | string | 同进度条颜色 |  |
| textType | 进度条文字类型，`text`(展示文字)/`icon`(展示icon标签) | string | text |  |
| status | 进度条当前状态，`true`展示动画效果 | boolean |  |  |
| iconName | Icon 名称 | string | checked |  |
| iconColor | Icon 颜色 | string | #439422 |  |
| iconSize | Icon 大小 | string | 16px |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

