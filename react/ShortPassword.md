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


ShortPassword:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| modelValue | 内容 | string | number | - | value受控值，defaultValue默认值  需要搭配 NumberKeyboard 使用，只增加 value，不增加 defaultValue @裴新宇  |
| visible | 是否展示短密码框 | boolean |  |  |
| title | 标题 | string | 请输入密码 |  |
| desc | 密码框描述 | string | 您使用了虚拟资产，请进行验证 | description |
| tips | 提示语 | string | 忘记密码 |  |
| closeOnClickOverlay | 是否点击遮罩关闭 | boolean | true | 改为：closeOnOverlayClick |
| noButton | 是否隐藏底部按钮 | boolean | true | hideFooter |
| length | 密码长度，取值为4~6 | string | number | 6 |  |
| errorMsg | 错误信息提示 | string | - | 这个属性目前是直接传入代码里的，传这个值就展示，不传就不展示，  与实际含义相违背     改成error    1.比如在onChange的时候来控制error信息，然后进行值的赋值  const [error, setError] = useState(false)  <ShortPassword       error={error}       onChange={(value) => setError(value.length >= 6)}  />  2.改成error?还是新增一个onError的回调？ |
| autoFocus | 自动聚焦 | boolean |  |  |
| plain | 是否展示明文？ | boolean |  | 新增属性 |
| onChange | 输入密码时触发事件 | 当前输入框值value |  |  |
| onOk | 点击确认时触发事件 | 当前输入框值value |  | onConfirm |
| onCancel | 点击取消时触发事件 | - |  |  |
| onClose | 点击关闭图标和遮罩时触发事件 | - |  |  |
| onTips | 点击忘记密码时触发事件 | - |  |  |
| onComplete | 输入完成的回调 | 当前输入框值value |  |  |
| onBlur/onFocus |  |  |  | nutui-react新增 |
| seperated | 格子间距 |  |  | 在css变量来控制 |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

