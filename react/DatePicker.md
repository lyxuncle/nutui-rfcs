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


DatePicker:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| modelValue | 初始值 | date | null | value，增加 defaultVlaue |
| visible | 是否可见 | boolean |  |  |
| type | 类时间类型，可选值 date time year-month month-day datehour datetime | string | date |  |
| minuteStep | 分钟步进值 | number | 1 |  |
| isShowChinese | 每列是否展示中文 | boolean |  | showChinese |
| title | 设置标题 | string | null |  |
| minDate | 开始日期 | date | 十年前 | startDate |
| maxDate | 结束日期 | date | 十年后 | endDate |
| formatter | 选项格式化函数 | (type: string, option: pickeroption) => pickeroption | - |  |
| filter | 选项过滤函数 | (type: string, option: pickeroption) => pickeroption[] | - |  |
| threeDimensional | 是否开启3D效果 | boolean | true |  |
| onConfirmDatePicker | 点击确定按钮时触发 | `values, options` |  | onConfirm |
| onCloseDatePicker | 关闭时触发 | - |  | onClose |
| onChange | 选项改变时触发 | `columnindex, values, options` |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

