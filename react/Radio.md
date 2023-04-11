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


Radio:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| disabled | 是否禁用选择 | boolean |  | 增加 checked 和 defaultChecked |
| iconSize | [图标尺寸](#/icon) | string | number | 18 | 删 |
| iconName | [图标名称](#/icon)，选中前(建议和`iconActiveName`一起修改) | string | check-normal | icon 函数？？ |
| iconActiveName | [图标名称](#/icon)，选中后(建议和`iconName`一起修改) | string | check-checked | activeIcon |
| value | 携带的标识值，用于 Group 模式 | string | number | boolean | - |  |
| shape | 形状，可选值为 button、round | string | round |  |

Radio:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| value | 当前选中项的标识符，与label值一致时呈选中状态 | string | number | boolean | - | 增加 defaultValue，增加受控和非受控 |
| textPosition | 文本所在的位置，可选值：`left`,`right` | string | right | labelPostion |
| direction | 使用横纵方向 可选值 horizontal、vertical | string | vertical |  |
| options | 配置 options 渲染单选按钮 | array | Array<{ label: string value: string disabled?: boolean } |  |
| onChange | 值变化时触发 | 当前选中项值（label）【设置label后有值、默认为空】 |  |  |
|  |  |  |  | 增加 disabled |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

