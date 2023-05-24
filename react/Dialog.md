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


Dialog:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| visible | 对话框是否可见 | boolean | - |  |
| title | 标题 | reactnode | - |  |
| content | 对话框的内容，适用于函数式调用 | reactnode | - |  |
| footer | 自定义页脚，传入 null 则不显示 | reactnode | - | boolean | ReactNode |
| okText | 确认按钮文案 | reactnode | 确定 | 改为 confirmText |
| cancelText | 取消按钮文案 | reactnode | 取消 |  |
| mask | 是否展示遮罩 | boolean | true | 改为 overlay   |
| noOkBtn | 是否隐藏确定按钮 | boolean |  | ?hasConfirmButton, true  ?hideConfirmButton, false |
| noCancelBtn | 是否隐藏取消按钮 | boolean |  | ?hasConfirmButton, true  ?hideCancelButton, false |
| okBtnDisabled | 禁用确定按钮 | boolean |  | ?disableConfirmButton, false |
| noFooter | 是否隐藏底部按钮栏 | boolean |  | 删，footer 传空 |
| closeOnClickOverlay | 点击蒙层是否关闭对话框 | boolean | true | 改为：closeOnOverlayClick |
| cancelAutoClose | 取消按钮是否默认关闭弹窗 | boolean | true | 删，默认关闭，如果自定义 onCancel 则需要自己控制 visible  beforeCancel, () => false  ?beforeClose, (button) => false |
| textAlign | 文字对齐方向，可选值同 css 的 text-align | string | center | 删，样式控制 |
| footerDirection | 使用横纵方向 可选值 horizontal、vertical | string | horizontal | 改为 direction |
| lockScroll | 背景是否锁定 | boolean |  |  |
| onOk | 确定按钮回调 | (e?: mouseevent) => promise |  | 改为 onConfirm |
| onCancel | 取消按钮回调 | () => void |  |  |
| onClosed | 关闭回调，任何情况关闭弹窗都会触发 | () => void |  | 改为 onClose |
| onClickSelf | 点击自身回调 | () => void |  | 改为 onClick |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

