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


PullToRefresh:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| canReleaseText | 释放的提示文案 | reactnode | 释放立即刷新 |  |
| completeText | 完成时的提示文案 | reactnode | 刷新成功 |  |
| completeDelay | 完成后延迟消失的时间，单位为 ms | number | 500 |  |
| disabled | 是否禁用下拉刷新 | boolean |  |  |
| headHeight | 头部提示内容区的高度，单位为 px | number | 40 |  |
| pullingText | 下拉的提示文案 | reactnode | 下拉刷新 |  |
| refreshingText | 刷新时的提示文案 | reactnode | 加载中⋯⋯ |  |
| renderText | 根据下拉状态，自定义下拉提示文案 | reactnode | - |  |
| threshold | 触发刷新需要下拉多少距离，单位为 px | number | 60 |  |
| onRefresh | 触发刷新时的处理函数 | `() => promise<any>` |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

