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


Checkbox:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| checked | 是否处于选中状态 | boolean |  | 增加 defaultChecked |
| disabled | 是否禁用选择 | boolean |  |  |
| textPosition | 文本所在的位置，可选值：`left`,`right` | string | right | labelPostion |
| iconSize | [图标尺寸](#/icon) | string | number | 18 | 删 |
| iconName | [图标名称](#/icon)，选中前(建议和`iconActiveName`一起修改) | string | check-normal | icon 和 activeIcon 、indeterminateIcon 合并成函数 ？？ |
| iconActiveName | [图标名称](#/icon)，选中后(建议和`iconName`一起修改) | string | checked | activeIcon |
| iconIndeterminateName | [图标名称](#/icon)，半选状态 | string | check-disabled | indeterminateIcon |
| iconClassPrefix | 自定义 icon 类名前缀，用于使用自定义图标 | string | nut-icon | 删 |
| iconFontClassName | 自定义 icon 字体基础类名 | string | nutui-iconfont | 删 |
| label | 复选框的文本内容 | string | - | 增加 value ，用于 group 模式 |
| onChange | 值变化时触发 | `state, label`,`state`代表当前状态，`label`表示当前选中的值 |  |  |

Checkbox:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| checkedValue | 当前选中项的标识符，和 `label` 相对应 | string | - | value，增加 defaultValue |
| disabled | 是否禁用选择,将用于其下的全部复选框 | boolean |  |  |
| max | 限制最大可选数 | undefined | number | undefined |  |
| textPosition | 文本所在的位置，可选值：`left`,`right` | string | right | labelPosition |
| direction | 使用横纵方向 可选值 horizontal、vertical | string | vertical |  |
| options | 配置 options 渲染复选按钮 | array | Array<{ label: string value: string disabled?: boolean } |  |
| onChange | 值变化时触发 | label,`label`返回一个数组，表示当前选中项的集合 |  |  |
| toggleAll | 全选/取消 | `f`,传 `true`,表示全选，传 `false`,表示取消全选 |  | toggle |
| toggleReverse | 反选 | - |  | reverse |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

