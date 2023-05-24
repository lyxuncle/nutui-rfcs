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


InfiniteLoading:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| hasMore | 是否还有更多数据 | boolean | true |  |
| threshold | 距离底部多远加载 | number | 200 |  |
| useWindow | 将滚动侦听器添加到 window 否则侦听组件的父节点 | boolean | true | 改为 target, id 选择器 |
| useCapture | 是否使用捕获模式 true 捕获 false 冒泡 | boolean |  | 改为 capture |
| containerId | 在 useWindow 属性为 false 的时候，自定义设置节点ID | string | - | 改为 target  支持选择器 or 仅 id 选择器 |
| loadMoreTxt | “没有更多数”据展示文案 | string | 哎呀，这里是底部了啦 | 改为 loadMoreText ReactNode |
| isOpenRefresh | 是否开启下拉刷新 | boolean |  | 改为 pullRefresh ? refresh  剥离出 pullrefresh，加一个demo |
| pullIcon | 下拉刷新[图标名称](#/icon) | string | - | 改为 pull ReactNode |
| pullTxt | 下拉刷新提示文案 | string | 松手刷新 | 改为 pull ReactNode |
| loadIcon | 上拉加载[图标名称](#/icon) | string | - | 改为 loadingText ReactNode |
| loadTxt | 上拉加载提示文案 | string | 加载中... | 改为 loadingText ReactNode |
| onLoadMore | 继续加载的回调函数 | done 函数，用于关闭加载中状态 |  |  |
| onScrollChange | 实时监听滚动高度 | 滚动高度 |  | 改为 onScroll |
| onRefresh | 下拉刷新事件回调 | done 函数，用于关闭加载中状态 |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

