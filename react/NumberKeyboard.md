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


NumberKeyboard:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| visible | 是否显示键盘 | boolean |  |  |
| title | 键盘标题 | string | - |  |
| type | 键盘模式 | string | default`：默认样式 `rightColumn`：带右侧栏 |  |
| randomKeys | 随机数 | boolean |  | random |
| customKey | 自定义键盘额外的键 | string[] | 数组形式最多支持添加2个,超出默认取前2项 | custom |
| confirmText | 自定义完成按钮文字，如"支付"，"下一步"，"提交"等 | string | 完成 |  |
| popClass | 自定义弹框类名 | string | - | popupClassName、popupIconPosition？？ |
| onChange | 点击按键时触发 | `value: string` |  |  |
| onDelete | 点击删除键时触发 | - |  |  |
| onClose | 点击关闭按钮或非键盘区域时触发 | - |  |  |
|  |  |  |  | 是不是加 onConfirm？？ |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

