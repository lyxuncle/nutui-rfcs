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


Calendar:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| visible | 是否可见 | boolean |  | 其他备注：是否增加年月切换，禁用日期 |
| type | 类型，日期选择'one'，区间选择'range' | string | one | 默认值改 从 one 为 single |
| poppable | 是否弹窗状态展示 | boolean | true | popup |
| isAutoBackFill | 自动回填 | boolean |  | autoBackfill |
| title | 显示标题（日历标题） | string | 日期选择 |  |
| defaultValue | 默认值，日期选择 string 格式，区间选择 Array 格式 | string | array | - | defaultValue，增加 value 用于受控模式 |
| startDate | 开始日期， 如果不限制开始日期传 null | string | 今天 |  |
| endDate | 结束日期，如果不限制结束日期传 null | string | 距离今天 365 天 |  |
| showToday | 是否展示今天标记 | boolean | true | 删, 值时 true 的时候，默认实现此逻辑 |
| startText | 范围选择，开始信息文案 | string | 开始 | ReactNode |
| endText | 范围选择，结束信息文案 | string | 结束 | ReactNode |
| confirmText | 底部确认按钮文案 | string | 确认 | footer 类型 RectNode ？？？ |
| showTitle | 是否在展示日历标题 | boolean | true | 改成 title，title 支持 boolean 和 reactnode |
| showSubTitle | 是否展示日期标题 | boolean | true | subTitle，支持 boolean 和 ReactNode |
| toDateAnimation | 是否启动滚动动画 | boolean | true | scrollAnimation |
| onBtn | 自定义日历标题下部，可用以添加自定义操作 | (() => string | jsx.element) | undefined | - | renderButton  renderTopButton  renderTop  改成 top 类型 ReactNode  |
| onDay | 日期信息 | ((date: day) => string | jsx.element) | undefined | - | renderDay |
| onTopInfo | 日期顶部信息 | ((date: day) => string | jsx.element) | undefined | - | renderDayTop，是否去掉 |
| onBottomInfo | 日期底部信息 | ((date: day) => string | jsx.element) | undefined | - | renderDayBottom，是否去掉 |

Calendar:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| day | string | number |  |  |  |
| type | string |  |  |  |
| onChoose | 选择之后或是点击确认按钮触发 | 日期数组（包含年月日和星期） |  | ???  onConfirm  onSelect |
| onClose | 关闭时触发 | - |  |  |
| onSelected | 点击/选择后触发 | `day: day` |  | ???  onClickDay |
| onYearMonthChange | 年月子标题到达顶部时触发 |  |  | onPageChange ??? |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

