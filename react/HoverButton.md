- 开始日期：2024-05-30
- 目标主要版本：NutUI-React 2.0 / NutUI-React-Taro 2.0
- 参考问题 Issues：

# 概括

若干功能按钮，通常出现在页面右下角，悬浮且位置固定，不随页面滚动出现位置的偏移；
可根据实际功能替换图标。

# 基本示例

- 基础用法
- 多个按钮
- 有底部导航栏的情况
- 自定义层级

# 动机

业务需要，规范化样式。

# 详细设计

HoverButton:

| 属性         | 描述                               | 类型      | 默认值 |
| ------------ | ---------------------------------- | --------- | ------ |
| zIndex       | 设置组件页面层级                   | number    | 10     |
| tabbarHeight | 底部导航栏高度（不包含安全区高度） | number    | -      |
| icon         | 设置按钮图标                       | ReactNode | -      |
| onClick      | 按钮点击时触发事件                 | Function  |        |

HoverButton.Item:

| 属性    | 描述               | 类型      | 默认值 |
| ------- | ------------------ | --------- | ------ |
| icon    | 设置按钮图标       | ReactNode | -      |
| onClick | 按钮点击时触发事件 | Function  |        |

样式变量：

| 名称                                        | 说明                     | 默认值                |
| ------------------------------------------- | ------------------------ | --------------------- |
| \--nutui-hoverbutton-spacing                | 按钮垂直间距             | `16px`                |
| \--nutui-hoverbutton-position-bottom        | 按钮区域距离屏幕底部距离 | `48px`                |
| \--nutui-hoverbutton-position-right         | 按钮区域距离屏幕右侧距离 | `16px`                |
| \--nutui-hoverbutton-item-border-color      | 按钮边框色               | `rgba(0, 0, 0, 0.06)` |
| \--nutui-hoverbutton-item-background        | 按钮背景色-正常态        | `#FFFFFF`             |
| \--nutui-hoverbutton-item-background-active | 按钮背景色-点击态        | `#F6F6F6`             |
| \--nutui-hoverbutton-item-icon-color        | 图标色-正常态            | `#1A1A1A`             |
| \--nutui-hoverbutton-item-icon-color-active | 图标色-点击态            | `#595959`             |

# 缺点

# 备择方案

# 采用策略

# 未解决的问题
