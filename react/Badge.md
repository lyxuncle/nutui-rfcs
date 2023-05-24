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


Badge:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| value | 显示的内容 | string | - | icon和value合并，类型改成ReactNode |
| max | value 为数值时，最大值 | number | 10000 | 默认值改为99，接近常用用户场景 |
| zIndex | 徽标的 z-index 值 | number | 10 | 删除 |
| dot | 是否为小点 | boolean |  |  |
| top | 上下偏移量，支持单位设置，可设置为：5 等 | number |  |  |
| right | 左右偏移量，支持单位设置，可设置为：5 等 | number |  |  |
| color | 徽标背景颜色 | string |  | 删，与antd保持一致，不删除。 |
| icon | 徽标自定义 | string | - | icon和value合并，类型改成ReactNode |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

