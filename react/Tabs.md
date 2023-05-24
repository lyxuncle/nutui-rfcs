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


Tabs:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| value | 绑定当前选中标签的标识符 | number | string |  | 增加受控处理和非受控处理  非受控处理的名字使用 defaultValue |
| color | 标签选中色(icon选中颜色) | string | #1a1a1a | activeColor，功能描述：改tab的文字和icon的颜色 |
| background | 标签栏背景颜色 | string | #f5f5f5 | 删除，通过自定 className 来控制。增加 style 支持  通过 css 变量 |
| direction | 使用横纵方向 可选值 `horizontal`、`vertical` | string | horizontal |  |
| type | 选中底部展示样式 可选值 `line`、`smile` | string | line | activeType |
| titleScroll | 标签栏是否可以滚动 | boolean |  | 删，超过宽度默认实现滚动功能 |
| ellipsis | 是否省略过长的标题文字 | boolean | true | 删, |
| animatedTime | 切换动画时长,单位 ms 0 代表无动画 | number | string | 300 | 改成 css 变量  改名字 duration |
| titleGutter | 标签间隙 | number | string |  | 改成 css 变量 |
| titleNode | 自定义导航区域 | reactnode | - | 改成 title，类型 () => reactnode |
| size | 标签栏字体尺寸大小 可选值 `large`、`normal`、`small` | string | normal | 删掉，改成 css 变量，把 large、normal、 small class删掉 |
| leftAlign | 标题左对齐 | boolean |  | align = 'left"| 'right' |
| autoHeight | 自动高度。设置为 true 时，nut-tabs 和 nut-tabs__content 会随着当前 nut-tabpane 的高度而发生变化。 | boolean |  |  |
| tabStyle | 标签栏样式 | cssproperties | {} |  |
| onClick | 点击标签时触发 | `{title, panekey, disabled}` |  | (index: string | number) => void |
| onChange | 当前激活的标签改变时触发 | `{title, panekey, disabled}` |  | (index: string | number) => void |

Tabs:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| default | 自定义内容 |  |  | 删 |

Tabs Children:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| title | 标题 | string | - | 是否需要修改 tab 的实现和组件划分？？ todo |
| paneKey | 标签 Key , 匹配的标识符 | string | 默认索引0,1,2... | value，用于控制选中 |
| disabled | 是否禁用标签 | boolean |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

