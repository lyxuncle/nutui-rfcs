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


InputNumber:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| modelValue | 初始值 | string | number | - | 改成 value，增加 defaultValue |
| inputWidth | 输入框宽度 | string | 40px | 删，通过 css 变量实现 |
| buttonSize | 操作符+、-尺寸 | string | 20px | 删，通过 css 变量实现 |
| min | 最小值限制 | string | number | 1 |  |
| max | 最大值限制 | string | number | 9999 |  |
| step | 步长 | string | number | 1 |  |
| decimalPlaces | 设置保留的小数位 | string | number |  | digits |
| disabled | 禁用所有功能 | boolean |  |  |
| readonly | 只读状态禁用输入框操作行为 | boolean |  | 改为 readOnly |
| isAsync | 支持异步修改 | boolean |  | async |
| onAdd | 点击增加按钮时触发 | `event: event` |  | 改一下 onPlus ？onIncrement ? |
| onReduce | 点击减少按钮时触发 | `event: event` |  | onMinus ？onDecrement ? |
| onOverlimit | 点击不可用的按钮时触发 | `event: event` |  |  |
| onChangeFuc | 值改变时触发 | `value: number, event: event` |  | onChange |
| onBlurFuc | 输入框失去焦点时触发 | `event: event` |  | onBlur |
| onFocus | 输入框获得焦点时触发 | `event: event` |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

