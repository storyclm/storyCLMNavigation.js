# storyCLMNavigation.js

storyCLMNavigation.js - это библиотека, реализующая переходы между отдельными html-файлами с помощью свайпов, как на устройствах с сенсорным вводом, так и в браузерах.
Библиотека предназначена для использования в HTML5 приложениях (презентациях) для StoryCLM и других подобных систем.

## Версия
Текущая версия документации актуальна для storyCLMNavigation.js (1.0.0).

## Зависимости

Данная библиотека требует подключенной библиотеки [hammer.js](http://hammerjs.github.io/).

## Подключение

```sh
<script src="js/hammer.js"></script>
<script src="js/storyclm-navigation-1.0.0.js"></script>
```


### StoryCLMNavigation
--------------------------

#### Method: block(bool)

**Описание:**

Блокирует всю навигацию.

**Параметры:**

* bool - флаг, определяющий, включен ли метод.

**Пример:**
```javascript
storyCLMNavigation.block(true);
```

--------------------------

#### Method: blockNext(bool)

**Описание:**

Блокирует навигацию вперед.

**Параметры:**

* bool - флаг, определяющий, включен ли метод.

**Пример:**
```javascript
storyCLMNavigation.blockNext(true);
```

--------------------------

#### Method: blockPrev(bool)

**Описание:**

Блокирует навигацию назад.

**Параметры:**

* bool - флаг, определяющий, включен ли метод.

**Пример:**
```javascript
storyCLMNavigation.blockPrev(true);
```

--------------------------

#### Method: blockSwipe()

**Описание:**

Одноразовый блок свайпов.
Удобно добавлять к слайдерам и перетаскиваемым элементам, чтобы избежать случайного перелистывания.

**Пример:**
```javascript
slider.draggable({
axis: 'x',
start: function (event, ui) {
    sliderEndPosition = 0;
    storyCLMNavigation.blockSwipe();
});
```

--------------------------

#### Method: isEmptyMeta()

**Описание:**

Проверка на наличие следующего/предыдущего слайда.

--------------------------

#### Method: onSwipeNext(direction)

**Описание:**

Свайп вперед по умолчанию.
На узловых слайдах требуется переопределсять эту функцию, чтобы явным образом указать, на какой слайд нужно перейти по свайпу вперёд.

**Параметры:**

* direction - файл слайда, на который нужно перейти.

**Пример переопределения функции:**
```javascript
    window.storyCLMNavigation.onSwipeNext = function () {
        window.direction = 'slide2.html'
    }
```

--------------------------

#### Method: onSwipePrev(direction)

**Описание:**

Свайп назад по умолчанию.

**Параметры:**

* direction - файл слайда, на который нужно перейти.

**Пример переопределения функции:**
```javascript
    window.storyCLMNavigation.onSwipePrev = function () {
        window.direction = 'slide1.html'
    }
```




