Yii2 Ace (Ajax.org Cloud9 Editor) Widget
========================================

[![Latest Stable Version](https://poser.pugx.org/wbraganca/yii2-ace-widget/v/stable.svg)](https://packagist.org/packages/wbraganca/yii2-ace-widget)
[![Total Downloads](https://poser.pugx.org/wbraganca/yii2-ace-widget/downloads.svg)](https://packagist.org/packages/wbraganca/yii2-ace-widget) 
[![Latest Unstable Version](https://poser.pugx.org/wbraganca/yii2-ace-widget/v/unstable.svg)](https://packagist.org/packages/wbraganca/yii2-ace-widget) 
[![License](https://poser.pugx.org/wbraganca/yii2-ace-widget/license.svg)](https://packagist.org/packages/wbraganca/yii2-ace-widget)

Ace (Ajax.org Cloud9 Editor) source repository can be found here - [https://github.com/ajaxorg/ace](https://github.com/ajaxorg/ace).

Original demo can be found here - [http://ace.c9.io/#nav=embedding](http://ace.c9.io/#nav=embedding).

## Installation

The preferred way to install this extension is through [composer](http://getcomposer.org/download/).

Either run

```bash
$ php composer.phar require "wbraganca/yii2-ace-widget" "*"
```

or add

```
"wbraganca/yii2-ace-widget": "*"
```

to the `require` section of your `composer.json` file.

## Usage

```php
<?php
use wbraganca\AceEditor\AceEditorWidget;

// For basic usage
echo AceEditorWidget::widget([
    'name' => 'editor_name',
    'value' => 'your text code',
]);

// Ace editor with emmet
$this->registerJsFile('https://cloud9ide.github.io/emmet-core/emmet.js');
echo AceEditorWidget::widget([
    'id' => 'attribute_id',
    'model' => $model,
    'attribute' => 'attribute_name',
    'theme' => 'sqlserver',
    'extensions' => [
        'emmet'
    ],
    'aceOptions' => [
        'showPrintMargin' => false,
        'minLines' => 20,
        'maxLines' => 500,
        'newLineMode' => 'unix'
    ]
]);
?>
```

### Options

- `varNameAceEditor` - global javascript variable (default is `aceEditor`).
- `mode` - code language (default is `php`).
- `theme` - color scheme (default is `github`).
- `editable` - whether to display editable text input or just highlight the output (default is `true`).
- `autocompletion` - whether to enable simple autocompletion functionality (only with `editable = true`).
- `aceOptions` - ACE's editor options.
