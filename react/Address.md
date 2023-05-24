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


Address:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| modelValue | 是否打开地址选择 | string | - | 改为 visible，备注：考虑每个地址项的禁用 |
| modelSelect | 设置默认选中地址 | string[] | number[] | [] | 改为 defaultValue |
| type | 地址选择类型 exist/custom/custom2 | string | custom | 是否有必要提供这么多？ |
| province | 省，每个省的对象中，必须有 name 字段，如果类型选择 custom2，必须指定 title 字段为首字母 | array | [] |  |
| city | 市，每个市的对象中，必须有 name 字段，如果类型选择 custom2，必须指定 title 字段为首字母 | array | [] |  |
| country | 县，每个县的对象中，必须有 name 字段，如果类型选择 custom2，必须指定 title 字段为首字母 | array | [] |  |
| town | 乡/镇，每个乡/镇的对象中，必须有 name 字段，如果类型选择 custom2，必须指定 title 字段为首字母 | array | [] |  |
| height | 弹层中内容容器的高度，仅在type="custom2"时有效 | string | number | 200px | 删掉改成 css 变量 |
| existAddress | 已存在地址列表，每个地址对象中，必传值provinceName、cityName、countyName、townName、addressDetail、selectedAddress（字段解释见下） | array | [] | 改为existList |
| defaultIcon | 已有地址列表默认图标，type='exist' 时生效 | string | - |  |
| selectedIcon | 已有地址列表选中图标，type='exist' 时生效 | string | - | 改为 selectIcon，看下 类型是不是 reactNode |
| closeBtnIcon | 自定义关闭弹框按钮图标 | string | - | 改为 closeIcon |
| backBtnIcon | 自定义地址与已有地址切换时，自定义返回的按钮图标 | string | - | 改为 backIcon |
| isShowCustomAddress | 是否可以切换自定义地址选择，type='exist' 时生效 | boolean | true | custom |
| customAddressTitle | 自定义地址选择文案，type='custom' 时生效 | string | 请选择所在地区 | custom， 合并成一个对象，名字是 title，类型：{custom:'', exist:'', other:''} |
| existAddressTitle | 已有地址文案 ，type='exist' 时生效 | string | 配送至 | 改为 exist,合并成一个对象，名字是 title，类型：{custom:'', exist:'', other:''} |
| customAndExistTitle | 自定义地址与已有地址切换按钮文案 ，type='exist' 时生效 | string | 选择其他地址 | 合并成一个对象，名字是 title，类型：{custom:'', exist:'', other:''} |
| onChange | 自定义选择地址时，选择地区时触发 | 参考 onchange |  |  |
| onSelected | 选择已有地址列表时触发 | 参考 selected |  | onSelect |
| onClose | 地址选择弹框关闭时触发 | 参考 close |  |  |
| closeMask | 点击遮罩层或点击右上角叉号关闭时触发 | `closeway: 'mask' | 'cross'` |  | 改为 onCancel, 加一个 onOverlayClick |
| switchModule | 点击'选择其他地址'或自定义地址选择左上角返回按钮触发 | `type: 'exist' | 'custom' | 'custom2'` |  | 改为 onSwitch |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

