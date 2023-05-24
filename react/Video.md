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


Video:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| source | 视频地址和类型设置 | object | - |  |
| options | 控制视频播放属性 | object | - | 备注：全局修改点 check |
| options.autoplay | 是否自动播放 | boolean |  |  |
| options.poster | 海报设置 | string | - |  |
| options.loop | 是否循环播放 | boolean |  |  |
| options.controls | 是否展示操作栏 | boolean | true |  |
| options.muted | 是否静音 | boolean |  |  |
| options.playsinline | 是否设置为行内播放元素（解决安卓兼容问题） | boolean |  |  |
| onPlayFuc | 播放 | - |  |  |
| onPauseFuc | 暂停 | - |  |  |
| onPlayend | 播放完成回调 | - |  | 改为 onPlayEnd |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

