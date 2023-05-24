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


SideNavBar:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| visible | 组件是否显示 | boolean |  |  |
| title | 整体标题 | string | - |  |
| width | 遮罩宽度百分比 | string | 0.8 |  |
| position | 弹出位置 | 'left' | 'right' | left |  |
| offset | 缩进宽度 | number | 20 | 改为 indent |
| onClose | 关闭遮罩时触发, handleClose 事件从 1.3.8 之后改为 onClose | - |  |  |

SideNavBar:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| ikey | 导航唯一标识 | string | number |  | 改为 key  功能实现不依赖，可改为 value，描述文案改为每一项的值 @王备  |
| title | 整体标题 | string | - |  |
| open | 导航是否默认展开 | boolean | true |  |
| onClick | 导航点击, titleClick 事件从 1.3.8 之后改为 onClick | `data: {title: string, ikey: string | number, isshow: boolean}` |  |  |

SubSideNavBar:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| ikey | 导航唯一标识 | string | number |  | 改为 key  功能实现不依赖，可改为 value，描述文案改为每一项的值 @王备  |
| title | 整体标题 | string | - |  |
| onClick | 导航点击, click 事件从 1.3.8 之后改为 onClick | `data: {title: string, ikey: string | number}` |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

