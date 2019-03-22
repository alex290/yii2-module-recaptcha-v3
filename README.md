Yii2 reCAPTCHA v3
=================
Yii2 reCAPTCHA v3

Установка
------------

Предпочтительным способом установки этого расширения является [composer](http://getcomposer.org/download/).

Запустить

```
php composer.phar require --prefer-dist alex290/yii2-module-recaptcha-v3 "*"
```

или добавить

```
"alex290/yii2-module-recaptcha-v3": "*"
```

в разделе require вашего `composer.json` файла.


Использование
-----

После установки расширения просто используйте его в коде :

добавьте это в основные компоненты main.php

```php
'components' => [
    ...
    'reCaptcha3' => [
        'class'      => 'alex290\recaptcha3\ReCaptcha',
        'site_key'   => 'site_key_###',
        'secret_key' => 'secret_key_###',
    ],

```

and in your model

acceptance_score the minimum score for this request (0.0 - 1.0) or null

```php
public $reCaptcha;
 
public function rules()
{
 	return [
 		...
 		 [['reCaptcha'], \alex290\recaptcha3\ReCaptchaValidator::className(), 'acceptance_score' => 0]
 	];
}
```

```php
<?= $form->field($model, 'reCaptcha')->widget(\alex290\recaptcha3\ReCaptchaWidget::class) ?>
```
