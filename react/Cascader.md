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


Cascader:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| value | 选中值 | array | - | 增加 defaultValue |
| options | 级联数据 | array | - |  |
| poppable | 是否弹窗状态展示 | boolean | true | popup |
| visible | 级联显示隐藏状态 | boolean |  |  |
| activeColor | 选中激活颜色（选中面板中项的颜色） | string | - |  |
| checkedIcon | 标记选中的Icon（选中面板中项的Icon） | string | checklist | ReactNode, activeIcon |
| tabsColor | tabs底部选中激活颜色 | string | - | 控制颜色和线  CSS 变量，tabActiveColor ??? |
| lazy | 是否开启动态加载 | boolean |  |  |
| lazyLoad | 动态加载回调，开启动态加载时生效 | function | - | ??? |
| valueKey | 自定义`options`结构中`value`的字段 | string | - | optionKey : {text: xxx, value: xxx, childern: xxx} |
| textKey | 自定义`options`结构中`text`的字段 | string | - | optionKey : {text: xxx, value: xxx, childern: xxx}  {  text: 'text1',  value: 'value6'  } |
| childrenKey | 自定义`options`结构中`children`的字段 | string | - | optionKey : {text: xxx, value: xxx, childern: xxx} |
| convertConfig | 当options为可转换为树形结构的扁平结构时，配置转换规则 | object | - | formatter  format  需要写明规则的类型 |
| title | 标题 | string | - |  |
| closeIconPosition | 取消按钮位置，继承 Popup 组件 | string | top-right | 以 popup 的名字为准 |
| close-icon | 自定义关闭按钮，继承 Popup 组件 | string | close | closeIcon |
| closeable | 是否显示关闭按钮，继承 Popup 组件 | boolean | true |  |
| onChange | 选中值改变时触发 | `value, pathnodes` |  |  |
| onPathChange | 选中项改变时触发 | `pathnodes` |  |  |
|  |  |  |  | 增加 onTabsChange |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

