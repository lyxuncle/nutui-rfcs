- 开始日期：2023-04-11
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


Audio:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| className | 类名 | string | - |  |
| style | css样式 | cssproperties | {} |  |
| url | 语音资源链接 | string | - |  |
| muted | 是否静音 | boolean |  | 改为mute |
| autoplay | 是否自动播放 | boolean |  |  |
| loop | 是否循环播放 | boolean |  |  |
| preload | 是否预加载语音 枚举值：'none'、'metadata'、'auto'、'' | string | auto |  |
| type | 展示形式，可选值：controls 控制面板 progress 进度条 icon 图标 none 自定义 | string | progress |  |
| onFastBack | 语音快退回调,type=progress时生效 | `event：htmlaudioelement` |  | 改为onFastReverse onRewind？ |
| onForward | 语音快进回调,type=progress时生效 | `event：htmlaudioelement` |  | 改为onFastForward？ |
| onPause | 暂停回调 | `event：htmlaudioelement` |  |  |
| onPlayEnd | 语音播放完成，loop=false时生效 | `event：htmlaudioelement` |  | ？ |
| onMute | 静音回调 | `event：htmlaudioelement` |  |  |
| onCanPlay | 可以播放媒体时触发 | `event：htmlaudioelement` |  | ？ |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

