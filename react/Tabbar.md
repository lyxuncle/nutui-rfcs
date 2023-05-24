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


Tabbar:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| visible | 默认选中的标签的索引值 | number |  | 改为 defaultValue |
| activeVisible | 选中的标签的索引值 | number | - | 改为 value |
| bottom | 是否固定在页面底部 | boolean |  | 改为 fixed？ |
| unactiveColor | icon未激活的颜色 | string | #7d7e80 | 改为 inactiveColor |
| activeColor | icon激活的颜色 | string | #1989fa |  |
| size | icon的统一尺寸 | string | boolean | 20 | 删 |
| safeAreaInsetBottom | 是否开启iphone系列全面屏底部安全区适配 | boolean |  | 改为 safeArea |
| style | 组件样式 | cssproperties | {} |  |
| clsssName | 组件类名 | string | - |  |
| onSwitch | 切换页签时触发事件 | 点击的数据和索引值 |  |  |

tabbar:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| tabTitle | 标签页的标题 | string | - | 改为 title |
| icon | 标签页显示的[图标名称](#/icon) 或图片链接 | string | - | 改成 reactNode |
| href | 标签页的跳转链接； | string | - |  |
| num | 页签右上角的数字角标，超出99之后为99+ | number | - | 删 |
| iconClassPrefix | 自定义 icon 类名前缀，用于使用自定义图标 | string | nut-icon | 删 |
| iconFontClassName | 自定义 icon 字体基础类名 | string | nutui-iconfont | 删 |
| dot | 是否显示图标右上角小红点 | boolean |  | 改为 badge？ |
| iconSize | icon的单个尺寸 | string | boolean | 20 | 删，和icon合并 |
|  |  |  |  | 增加一个禁用？ |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

