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


Signature:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| lineWidth | 线条的宽度 | number | 3 |  |
| strokeStyle | 绘图笔触颜色 | string | #000 |  |
| type | 图片格式 | string | png |  |
| unSupportTpl | 不支持 Canvas 情况下的展示文案 | string | 对不起，当前浏览器不支持 Canvas，无法使用本控件！ |  |
| onConfirm | 点击确认按钮触发事件回调函数 | canvas 和签名图片展示的 data uri |  |  |
| onClear | 点击重签按钮触发事件回调函数 | - |  |  |
| visible | 是否显示弹层 | 是 | boolean | 建议重新review |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

