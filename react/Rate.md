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


Rate:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| modelValue | 当前 star 数不能大于count | number | - | value受控值，defaultValue默认值 |
| count | star 总数 | number | 5 |  |
| minimizeValue | 最少选中star数量 | number |  | min |
| iconSize | star 大小 | number | 18 | 删除 |
| activeColor | 图标选中颜色 | string | #fa200c | 删除 这里activeColor是设置icon的color |
| voidColor | 图标未选中颜色 | string | #ccc | 删除 这里voidColor是设置icon的color |
| uncheckedIcon | 使用图标(未选中) | string | star-n |  |
| checkedIcon | 使用图标(选中) | string | star-fill-n |  |
| allowHalf | 是否半星 | boolean |  |  |
| readonly | 是否只读 | boolean |  | readonly改成readOnly |
| disabled | 是否禁用 | boolean |  |  |
| spacing | 间距 | number | 20 | 删除、css 变量 |
| onChange | 当前分值修改时时触发的事件 | 当前值 |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

