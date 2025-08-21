# Typecho-Options
TTDF后台设置框架独立版

支持文章字段，如果不需要直接删除`fields.php`即可

## 快速上手

在主题`functions.php`引入`options.php`即可快速调用设置选择框架进行开发

functions.php: 

```php
<?php 
if (!defined('__TYPECHO_ROOT_DIR__')) exit;
// 引入设置框架
require_once 'options.php';
```

### 开发示例

#### 主题后台设置项

| 字段类型 | 描述           |
| -------- | -------------- |
| Text     | 文本框         |
| Textarea | 文本域         |
| Radio    | 单选框         |
| Select   | 下拉框         |
| Checkbox | 多选框         |
| Html     | 自定义 HTML 标签 |

`setup.php`
```php
return [
    '基础设置' => [
        'title' => '基础设置',
        'fields' => [
            [
                // 'Html' => '自定义HTML标签',
                'type' => 'Html',
                'content' => '<div class="alert success">感谢使用<a href="https://github.com/YuiNijika/TTDF">TTDF</a>进行开发</div>'
            ],
            [
                // 'Text' => '文本框',
                'type' => 'Text',
                'name' => 'SubTitle',
                'value' => null,
                'label' => '副标题',
                'description' => '这是一个文本框，用于设置网站副标题，如果为空则不显示。'
            ],
            [
                // 'Textarea' => '文本域',
                'type' => 'Textarea',
                'name' => 'TTDF_Textarea',
                'value' => null,
                'label' => '文本域',
                'description' => '这是一个文本域~'
            ]
        ]
    ],
    'select-elements' => [
        'title' => '选择设置',
        'fields' => [
            [
                // 'Radio' => '单选框',
                'type' => 'Radio',
                'name' => 'TTDF_Radio',
                'value' => 'option1',
                'label' => '单选框',
                'description' => '这是一个单选框~',
                'options' => [
                    'option1' => '选项一',
                    'option2' => '选项二',
                    'option3' => '选项三'
                ]
            ],
            [
                // 'Select' => '下拉框',
                'type' => 'Select',
                'name' => 'TTDF_Select',
                'value' => 'option2',
                'label' => '下拉框',
                'description' => '这是一个下拉框~',
                'options' => [
                    'option1' => '选项一',
                    'option2' => '选项二',
                    'option3' => '选项三'
                ]
            ],
            [
                // 'Checkbox' => '多选框',
                'type' => 'Checkbox',
                'name' => 'TTDF_Checkbox',
                'value' => ['option1', 'option3'],
                'label' => '多选框',
                'description' => '这是一个多选框~',
                'options' => [
                    'option1' => '选项一',
                    'option2' => '选项二',
                    'option3' => '选项三'
                ]
            ]
        ]
    ],
    'HTML-Demo' => [
        'title' => 'HTML示例',
        // 定义HTML TAB栏
        'html' => [
            [
                // 'Content' => '自定义输出HTML内容',
                'content' => '
                    <div class="alert info">信息提示</div>
                    <div class="alert success">成功提示</div>
                    <div class="alert warning">警告提示</div>
                    <div class="alert error">错误提示</div>
                '
            ],
        ]
    ],
];
```

#### 文章字段项
| 字段类型 | 描述           |
| -------- | -------------- |
| Text     | 文本框         |
| Textarea | 文本域         |
| Radio    | 单选框         |
| Select   | 下拉框         |
| Checkbox | 多选框         |

```php
return [
    [
        // Text
        'type' => 'Text',
        'name' => 'TTDF_Fields_Text',
        'value' => null, // 默认值为 null
        'label' => '文本框',
        'description' => '用于输入单行文本',
        // 添加字段属性
        'attributes' => [
            'style' => 'width: 100%;'
        ]
    ],
    [
        // Textarea
        'type' => 'Textarea',
        'name' => 'TTDF_Fields_Textarea',
        'value' => null, // 默认值为 null
        'label' => '文本域',
        'description' => '用于输入多行文本',
        // 添加字段属性
        'attributes' => [
            'style' => 'width: 100%;height: 100px;'
        ]
    ],
    [
        // Radio
        'type' => 'Radio',
        'name' => 'TTDF_Fields_Radio',
        'value' => null, // 默认值为 null
        'label' => '单选框',
        'description' => '用于选择一个选项',
        'options' => [
            'option1' => '选项一',
            'option2' => '选项二',
            'option3' => '选项三'
        ]
    ],
    [
        // Select
        'type' => 'Select',
        'name' => 'TTDF_Fields_Select',
        'value' => null, // 默认值为 null
        'label' => '下拉框',
        'description' => '用于从列表中选择',
        'options' => [
            'option1' => '选项一',
            'option2' => '选项二',
            'option3' => '选项三'
        ]
    ],
    [
        // Checkbox
        'type' => 'Checkbox',
        'name' => 'TTDF_Fields_Checkbox',
        'value' => [], // 默认值为空数组
        'label' => '多选框',
        'description' => '用于选择多个选项',
        'options' => [
            'option1' => '选项一',
            'option2' => '选项二',
            'option3' => '选项三'
        ]
    ]
];
```
