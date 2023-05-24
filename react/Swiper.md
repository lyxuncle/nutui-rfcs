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


Swiper:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| width | 轮播卡片的宽度 | number | string | window.innerWidth |  |
| height | 轮播卡片的高度 | string | number |  |  |
| direction | 轮播方向,可选值`horizontal`,`vertical` | string | horizontal |  |
| paginationVisible | 分页指示器是否展示 | boolean |  | 改为 indicator |
| paginationColor | 分页指示器选中的颜色 | string | #fff | 改为 indicator，增加 indicatorProps |
| paginationBgColor | 分页指示器的背景色 | string | #ddd | 改为 indicator，增加 indicatorProps |
| loop | 是否循环轮播 | boolean | true |  |
| duration | 动画时长（单位是ms） | number | string | 500 |  |
| autoPlay | 自动轮播时长，0表示不会自动轮播 | number | string |  | 改成 autoplay |
| touchable | 是否可触摸滑动 | boolean | true |  |
| initPage | 初始化索引值 | number | string |  | defaultIndex，不需要受控，通过 ref.to() 切换 |
| pageContent | 自定义指示器 | string | reactnode | - | 和 indicator 合并 |
| isPreventDefault | 滑动过程中是否禁用默认事件 | boolean | true | 改为 preventDefault |
| isStopPropagation | 滑动过程中是否禁止冒泡 | boolean | true | 改为 stopPropagation |
| isCenter | 是否居中展示，必须传对应的`width` 和 `height` | boolean |  | center ？？ |
| onChange | 卡片切换后的回调 | 当前索引值index |  | 备注：功能待完善 |
| prev | 切换到上一页 | - |  |  |
| next | 切换到下一页 | - |  |  |
| to | 切换到指定轮播 | `index: number` |  |  |
| resize | 外层元素大小或组件显示状态变化时，可以调用此方法来触发重绘 | - |  | 删除 ？ |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

