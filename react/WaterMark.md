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


WaterMark:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| width | 水印的宽度 | number | 120 |  |
| height | 水印的高度 | number | 64 |  |
| rotate | 水印绘制时，旋转的角度 | number | -22 |  |
| image | 图片源，建议导出 2 倍或 3 倍图，优先使用图片渲染水印 | string | - | ？？？ |
| imageWidth | 图片宽度 | number | 120 |  |
| imageHeight | 图片高度 | number | 64 |  |
| zIndex | 追加的水印元素的 z-index | number | 2000 |  |
| content | 水印文字内容 | string | - |  |
| fontColor | 水印文字颜色 | string | rgba(0, 0, 0, .15) | color，检查全局修改点 |
| fontSize | 文字大小 | string | number | 16 |  |
| gapX | 水印之间的水平间距 | number | 24 |  |
| gapY | 水印之间的垂直间距 | number | 48 |  |
| fullPage | 是否覆盖整个页面 | boolean | true |  |
| fontFamily | 水印文字字体 | boolean | true |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

