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


Uploader:

| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| autoUpload | 是否在选取文件后立即进行上传，false 时需要手动执行 ref submit 方法进行上传 | boolean | true |  |
| name | `input` 标签 `name` 的名称，发到后台的文件参数名 | string | file |  |
| url | 上传服务器的接口地址 | string | - |  |
| defaultFileList | 默认已经上传的文件列表 | fileitem[] | [] | 改为 defaultValue |
| isPreview | 是否上传成功后展示预览图 | boolean | true | 改为 preview |
| defaultImg | 当上传非图片('image')格式的默认图片地址 | string | - | 改为previewUrl |
| isDeletable | 是否展示删除按钮 | boolean | true | 改为 deletable |
| method | 上传请求的 http method | string | post |  |
| listType | 上传列表的内建样式，支持两种基本样式 picture、list | string | picture | previewType |
| capture | 图片[选取模式](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/input#htmlattrdefcapture)，直接调起摄像头 | string |  |  |
| maximize | 可以设定最大上传文件的大小（字节） | number | string | Number.MAX_VALUE | maxFileSize |
| maximum | 文件上传数量限制 | number | string | 1 | maxCount |
| clearInput | 是否需要清空`input`内容，设为`true`支持重复选择上传同一个文件 | boolean | true |  |
| accept | 允许上传的文件类型，[详细说明](https://developer.mozilla.org/zh-CN/docs/Web/HTML/Element/Input/file#%E9%99%90%E5%88%B6%E5%85%81%E8%AE%B8%E7%9A%84%E6%96%87%E4%BB%B6%E7%B1%BB%E5%9E%8B) | string | * |  |
| headers | 设置上传的请求头部 | object | {} | 改成 header |
| data | 附加上传的信息 formData | object | {} |  |
| uploadIcon | 上传区域[图标名称](#/zh-CN/icon)或图片链接 | string | photograph | uploadIcon ReactNode |
| uploadIconSize | 上传区域[图标尺寸](#/icon)大小，如 `20px` `2em` `2rem` | string | number | - | 删 |
| uploadIconTip | 上传区域图片下方文字 | string | - | uploadLabel ReactNode |
| xhrState | 接口响应的成功状态（status）值 | number | 200 |  |
| withCredentials | 支持发送 cookie 凭证信息 | boolean |  |  |
| multiple | 是否支持文件多选 | boolean |  |  |
| disabled | 是否禁用文件上传 | boolean |  |  |
| timeout | 超时时间，单位为毫秒 | number | string | 1000 * 30 |  |
| onBeforeUpload | 上传前的函数需要返回一个`Promise`对象 | function | null | beforeUpload |
| onBeforeXhrUpload | 执行 XHR 上传时，自定义方式 | function(xhr，option) | null | beforeXhrUpload |
| onBeforeDelete | 除文件时的回调，返回值为 false 时不移除。支持返回一个 `Promise` 对象，`Promise` 对象 resolve(false) 或 reject 时不移除 | function(file): boolean | promise | - | beforeDelete |

Uploader:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| status | 文件状态值，可选'ready,uploading,success,error,removed' | `ready` |  |  |
| uid | 文件的唯一标识 | `new date().gettime().tostring()` |  |  |
| name | 文件名称 | - |  |  |
| url | 文件路径 | - |  |  |
| type | 文件类型 | `image/jpeg` |  |  |
| formData | 上传所需的data | `new formdata()` |  |  |

FileItem:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| onStart | 文件上传开始 | `options` |  |  |
| onProgress | 文件上传的进度 | `event, options, percentage` |  |  |
| onOversize | 文件大小超过限制时触发 | `files` |  |  |
| onSuccess | 上传成功 | `responsetext, options` |  |  |
| onFailure | 上传失败 | `responsetext, options` |  |  |
| onChange | 上传文件改变时的状态 | `filelist, event` |  |  |
| onRemove | 文件删除之前的状态 | `files, filelist` |  | 删除时的回调，改为 onDelete |
| onFileItemClick | 文件上传成功后点击触发 | `fileitem` |  | ?onFileClick |

events:
    
| 属性 | 描述 | 类型 | 默认值 | 改动点 |
| --- | --- | --- | --- | --- |
| submit | 手动上传模式，执行上传操作 | - |  |  |
| clear v1.4.9 | 清空已选择的文件队列（该方法一般配合在手动模式上传时使用） | index |  |  |


# 缺点

Props 的改动属于破坏性更新，升级成本比较高

# 备择方案


# 采用策略


# 未解决的问题

