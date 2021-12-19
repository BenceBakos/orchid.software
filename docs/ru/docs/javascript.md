---
title: Использование JavaScript 
description: Пример использования Stimulus JS с пакетом Laravel Orchid
---

Основой платформы по части стилей является [Bootstrap](http://getbootstrap.com/), а в браузере выполняется код [Stimulus](https://stimulusjs.org/), вам необязательно использовать именно их.

Построим базовый пример, который отображает текст, введённый в поле. Для этого выполним описанные ниже действия.

В `resources/js` создадим следующую структуру:

```php
resources
├── js
│   ├── controllers
│   │   └── hello.js
│   └── dashboard.js
├── lang
├── sass
└── views
```

Класс контроллера со следующим содержанием:

```php
// hello.js
export default class extends window.Controller {

    static get targets() {
        return [ "name", "output" ]
    }

    greet() {
        this.outputTarget.textContent =
            `Hello, ${this.nameTarget.value}!`
    }
}
```

И точку сборки:

```php
// dashboard.js
import HelloController from "./controllers/hello"

application.register("hello", HelloController);
```

Такая структура не помешает вашему приложению не зависимо от того, какой front-end строится: Angular/React/Vue и т.п.

Останется только описать сборку в webpack.mix.js :

```php
let mix = require('laravel-mix');

mix.js('resources/js/dashboard.js', 'public/js')
```

Осталось только подключить полученный сценарий к панели в файле конфигурации или в сервис провайдере, используя метод `registerResource`. Точно так же можно поступить и с таблицами стилей, что позволит эффективно строить логику приложений.

```php
class ServiceProvider extends ServiceProvider
{
    public function boot(Dashboard $dashboard)
    {
        $dashboard->registerResource('scripts','dashboard.js');
        //$dashboard->registerResource('stylesheets','dashboard.css');
    }
}
```

Для отображения воспользуемся шаблоном, для которого предварительно нужно определить `Controller` и `Route` в вашем приложение:

```php
// hello.blade.php
<div data-controller="hello">
  <input data-target="hello.name" type="text">

  <button data-action="click->hello#greet">
    Greet
  </button>

  <span data-target="hello.output">
  </span>
</div>
```
