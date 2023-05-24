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


Form:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| required | 必填表单项 label 的红色星标 | boolean |  |  |
| name | 在使用表单校验功能的情况下，该属性是必填的 | string | - |  |
| labelWidth | 表单项 label 宽度，默认单位为`px` | number | string | 90px | css 变量 |
| errorMessageAlign | 错误提示文案对齐方式，可选值为 `center` `right` | string | left |  |
| initialValue | 设置子元素默认值 | string | - |  |

Form.Item Props:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| required | 是否为必选字段 | boolean |  |  |
| message | 错误提示文案 | string |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

