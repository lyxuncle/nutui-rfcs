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


Popup:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| visible | 当前组件是否显示 | boolean |  |  |
| zIndex | 遮罩层级 | string | number | 2000 |  |
| duration | 遮罩动画时长，单位秒 | number | 0.3 |  |
| overlayClass | 自定义遮罩类名 | string | - | 改成 overlayClassName，统一处理 |
| overlayStyle | 自定义遮罩样式 | cssproperties | - | 改成 overlayStyle，统一处理 |
| lockScroll | 背景是否锁定 | boolean | true |  |
| overlay | 是否显示遮罩 | boolean | true |  |
| closeOnClickOverlay | 是否点击遮罩关闭 | boolean | true | 改为：closeOnOverlayClick |
| position | 弹出位置（top,bottom,left,right,center） | string | center |  |
| transition | 动画名 | string | - |  |
| style | 自定义弹框样式 | cssproperties | - |  |
| popClass | 自定义弹框类名 | string | - | 改成 className |
| closeable | 是否显示关闭按钮 | boolean |  |  |
| closeIconPosition | 关闭按钮位置（top-left,top-right,bottom-left,bottom-right） | string | top-right |  |
| closeIcon | 自定义 Icon | string | close |  |
| destroyOnClose | 组件销毁后是否关闭 | boolean | true | 改为：不可见时卸载内容 |
| round | 是否显示圆角 | boolean |  | 改为 radius |
| teleport | 指定节点挂载 | htmlelement | (() => htmlelement) | null | null | 改成 portal，与react保持一致 |
| onClick | 点击弹框时触发 | `event: mouseevent` |  |  |
| onClickCloseIcon | 点击关闭图标时触发 | `event: mouseevent` |  | 修改 调用 onClickCloseIcon 的方法  返回值 改为 boolean  () => boolean     |
| onOpen | 打开弹框时触发 | - |  | 删 |
| onClose | 关闭弹框时触发 | - |  |  |
| onOpend | 遮罩打开动画结束时触发 | `event: htmlelement` |  | afterClose 完全关闭后触发 () => void -  afterShow 完全展示后触发 () => void - |
| onClosed | 遮罩关闭动画结束时触发 | `event: htmlelement` |  |  |
| onClickOverlay | 点击遮罩触发 | `event: mouseevent` |  | 修改 调用 onclickoverlay的方法  返回值 改为 boolean  () => boolean     |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

