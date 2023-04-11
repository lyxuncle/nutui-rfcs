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


Notify:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| type | 提示的信息类型（primary，success ，danger，warning） | string | danger |  |
| message/msg | 展示文案，支持通过\n换行 | string | - | 组件使用：children  函数调用：作为第一个参数，不需要名字 |
| duration | 展示时长(ms)，值为 0 时，notify 不会消失 | string | 3000 |  |
| color | 字体颜色 | string | - | 删，样式控制 |
| background | 背景颜色 | string | - | 删，样式控制 |
| className | 自定义类名 | string | number | 1 |  |
| position | 自定义位置 (top, bottom) | string | top |  |
| onClick | 点击事件回调 | 无 |  |  |
| onClosed | 关闭事件回调 | 无 |  | 改成 onClose |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

