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


ImagePreview:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| show | 是否展示预览图片 | boolean |  | 改为 visible |
| videos | 预览的视频数组（视频自动放到图片之前、taro场景暂不支持） | array<object> | [] | 删，作为children，可写入demo支持 |
| images | 预览图片数组 | { src: string }[] | [] |  |
| autoplay | 自动轮播时长，0表示不会自动轮播 | number | string | 3000 | 改为 autoPlay |
| initNo | 初始页码 | number | 1 | 改为 defaultValue，增加value 支持受控 |
| paginationVisible | 分页指示器是否展示 | boolean |  | 改为 indicator，并使用 Indicator 组件 |
| paginationColor | 分页指示器选中的颜色 | string | #fff | 使用 Indicator 属性 |
| contentClose | 点击图片可以退出预览 | boolean |  | 改为 closeOnContentClick  popup的onclick事件和这个属性初始值设置冲突 |
| onClose | 点击遮罩关闭图片预览时触发 | 无 |  |  |
|  |  |  |  | 增加：手动缩放图片  增加：等比例缩放 |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

