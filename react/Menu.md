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


Menu:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| activeColor | 选项的选中态图标颜色 | string | #F2270C |  |
| closeOnClickOverlay | 是否在点击遮罩层后关闭菜单 | boolean | true | 改为：closeOnOverlayClick |
| lockScroll | 背景是否锁定 | boolean | true | 增加方法：  closeOnClickAway 是否在点击外部区域后自动隐藏 boolean FALSE |
| scrollFixed | 滚动后是否固定，可设置固定位置 | boolean | string | number | true |  |
| titleIcon | 自定义标题图标 | string | - | 改为 icon |

Menu:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| title | 菜单项标题 | string | 当前选中项文字 | 文档缺失 当前值（默认激活状态的值） 的说明，如 value 值 |
| options | 选项数组 | array | - |  |
| disabled | 是否禁用菜单 | boolean |  |  |
| columns | 可以设置一行展示多少列 options | number | 1 |  |
| optionsIcon | 自定义选项图标 | string | Check | 改为 icon |
| direction | 菜单展开方向，可选值为up | string | down |  |
| activeClassName | 选项选中时自定义标题样式类 | string | - | 没有用到，删除，验证后删除 |
| inactiveClassName | 选项非选中时自定义标题样式类 | string | - | 没有用到，删除，验证后删除 |
| fontClassName | 自定义icon 字体基础类名 | string | nutui-iconfont | 删 |
| iconClassPrefix | 自定义icon 类名前缀，用于使用自定义图标 | string | nut-icon | 删 |
| onChange | 选择 option 之后触发 | 选择的 value |  |  |
| toggle | 切换菜单展示状态，传 true 为显示，false 为隐藏，不传参为取反 | `show?: boolean` |  | 为api，不用动 |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

