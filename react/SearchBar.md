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


SearchBar:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| value | 当前输入的值 | string | - |  |
| placeholder | 输入框默认暗纹 | string | 请输入 |  |
| className | 自定义class类名 | string | - |  |
| shape | 搜索框形状，可选值为 `round` | string | square | 1.现在并不生效，如果要加的话，需要加到nut-searchbar__content属性上  2.border-radius的值可以用css变量来控制，不需要传shape属性 |
| disabled | 是否禁用输入框 | boolean |  | 透传到input上，和input同理 |
| readonly | 输入框只读 | boolean |  | 透传到input上，和input同理 |
| maxLength | 最大输入长度 | number | 9999 | 透传到input上，和input同理 |
| clearable | 是否展示清除按钮 | boolean | true |  |
| clearIcon |  |  |  |  |
| clearIconSize | 清除按钮尺寸大小，同Icon的size | string | number | 12px | 删除，icon上的属性 |
| background | 搜索框外部背景色 | string | - | css变量控制 |
| inputBackground | 搜索框背景色 | string | - | css变量控制 |
| inputAlign | 对齐方式，可选 `center` `right` | string | left | css变量控制文本的对其方向 |
| autofocus | 是否自动聚焦 | boolean |  | 1.文档书写错误，应该写成autoFocus，代码里是正确的 |
| label | 搜索框左侧文本 | string | - | left |
| actionText | 取消按钮文本 | reactnode | - | right??修改描述 |
| leftinIcon | 输入框内，左icon | reactnode | <Icon name="search" size="12" /> | leftIn??不仅是图标 |
| rightinIcon | 输入框内，右icon | reactnode | - | rightIn??不仅是图标 |
| leftoutIcon | 输入框外，左icon | reactnode | - | 删icon图标方式传入 |
| rightoutIcon | 输入框外，右icon | reactnode | - | 删icon图标方式传入 |
| onChange | 输入内容时触发 | `val: string, event: event` |  |  |
| onFocus | 聚焦时触发 | `val: string, event: event` |  |  |
| onBlur | 失焦时触发 | `val: string, event: event` |  |  |
| onClear | 点击清空时触发 | `event: event` |  |  |
| onCancel | 点击取消按钮时触发 | - |  | ？？可以改成 ref 的 方法，在实现的时候看一下是否可以通过键盘的确认，  取消实现 |
| onSearch | 确定搜索时触发 | `val: string, event: event` |  | ？？可以改成 ref 的 方法，在实现的时候看一下是否可以通过键盘的确认，  取消实现 |
| onClickInput | 点击输入区域时触发 | event: event |  | 删除，使用onFocus |
| onClickLeftinIcon | 点击输入框`内左侧`图标时触发 | `val: string, event: event` |  | 删除 |
| onClickLeftoutIcon | 点击输入框`外左侧`图标时触发 | `val: string, event: event` |  | 删除 |
| onClickRightinIcon | 点击输入框`内右侧`图标时触发 | `val: string, event: event` |  | 删除 |
| onClickRightoutIcon | 点击输入框`外右侧`图标时触发 | `val: string, event: event` |  | 删除 |
| onlyShowClearWhenFocus | 如果 true，那么只有输入框聚焦时才会显示清除按钮；如果为 false，那么输入框失去焦点后依旧会显示清除按钮 | boolean |  | 新增 |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

