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


Toast:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| id | 标识符，相同者共用一个实例<br>loading类型默认使用一个实例，其他类型默认不共用 | string | number | - |  |
| duration | 展示时长（秒）<br>值为 0 时，toast 不会自动消失 | number | 2 |  |
| title | 标题 | string | - | title msg icon 要不要合并 |
| center | 是否展示在页面中部（为false时展示在底部） | boolean | true | 是否改为垂直方向显示位置position：  'top' | 'bottom' | 'center' |
| bottom | 距页面底部的距离（像素），option.center为false时生效 | number | 30 |  |
| textAlignCenter | 多行文案是否居中 | boolean | true | css变量实现? |
| bgColor | 背景颜色（透明度） | string | rgba(0, 0, 0, 0.8) | css变量实现? |
| customClass | 自定义类名 | string | - | 改为className |
| icon | 自定义图标，**支持图片链接或base64格式** | string | - | 替换icon有问题，图标位置展示的文字，  需要修改   |
| iconSize | 自定义图标尺寸 | string | 20 | 删 |
| size | 文案尺寸，**small**/**base**/**large**三选一 | string | base | css变量实现? |
| cover | 是否显示遮罩层 | boolean |  | 改成 overlay |
| coverColor | 遮罩层颜色，默认透明 | string | rgba(0,0,0,0) | 改成 overlay |
| loadingRotate | loading图标是否旋转，仅对loading类型生效 | boolean | true | 删，代码中未实现，现在改为icon传入，是否还要保留 |
| onClose | 关闭时触发的事件 | function | null | afterClose |
| closeOnClickOverlay | 是否在点击遮罩层后关闭提示 | boolean |  | 改为：closeOnOverlayClick |
| Toast.text | 展示文字提示 | message｜ options | toast 实例(message支持传入HTML) |  |
| Toast.success | 展示成功提示 | message｜ options | toast 实例 |  |
| Toast.fail | 展示失败提示 | message｜ options | toast 实例 |  |
| Toast.warn | 展示警告提示 | message｜ options | toast 实例 |  |
| Toast.hide | 关闭提示 | force\: boolean | void |  |
| Toast.loading | 展示加载提示 | message｜ options | toast 实例 |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

