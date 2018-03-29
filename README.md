# Миксин для преобразования данных из настроек

Настройки включаются в scss через дерективу import.

После чего в ваших scss доступен массив (map) $settings.
```scss
@import "settings";
```

Но! Для работы с переменными нужно использовать пару функций scss, из-за особенности самого scss. 

Так как color в scss это тип, а из настроек прилетает цвет в виде строки, вам помогут функции в данном репозитории (`function-settings.scss`).

```scss
// settings подтягиваются из платформы
@import "settings";

// Файл с миксином settings. $color: settings(color);
@import "function-settings";

// Настройки поумолчанию. $color-background-primary: #ffffff !default;
@import "variables-default";

// Данные из настроек. $color-background-primary: settings(color_background_primary);
@import "variables";
```

> Теперь нет необходимость создавать variables.scss.liquid, но нужно потратить время на понимание данного подхода. 
