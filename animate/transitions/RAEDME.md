# CSS переходы (transitions)
Переход из одного состояния в другое, за определённое время, меняются значения CSS-свойств. Позволяют задать плавный переход CSS-свойствам, значения свойств изменяются постепенно в течении определенного (заданного) промежутка времени.

- анимируемые CSS-свойства
- transition-property
- transition-duration
- transition-timing-function
- transition-delay
- transition (сокращенная запись)

Пример:

    .selector {
        width: 50px;
        height: 10px;
        background-color: #2ecc71;
        transition-property: height, background-color; /* Для каких свойств произвести анимацию */
        transition-duration: 2s;                       /* Время работы анимации */
        transition-delay: 1500ms;                      /* Задержка перед анимацией */
    }
    .selector:hover {
        height: 100px;
        background-color: #e74c3c;
    }

## Анимируемые CSS-свойства
Размеры, цвета, тени и т.п. Анимируемые CSS-свойства можно посмотреть на странице: https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_animated_properties

Не всем CSS свойствам можно задать плавный переход:

## transition-property
Определяет свойства, к которым будет применен эффект перехода.

    selector {
        transition-property: all; /* По умолчанию all */
        transition-duration: 1s;
    }

- none - эффект перехода не будет применен
- all - эффект перехода применится ко всем доступным свойствам
- `<свойство> [,<свойство>]*` - указываv имена одного или несколькольких свойств, к которым применится эффект перехода

В качестве оптимизации производительности, рекомендуется явно задавать имена свойств используемых в анимации, вместо `all`.

Для нескольких свойств задаём одно время:

    transition-property: width, height;
    transition-property: 1s;

Каждому свойству можно задать своё время выполнения или задержки и т.д.:

    transition-property: width, height;
    transition-property: 1s, 2s;

## transition-duration
Задает длительность эффекта перехода.

    selector {
        transition-duration: 1s; /* Длительность перехода */
    }

`<время> [,<время>]*` - задается в "s" или "ms"

## transition-timing-function
Определяет скорость и ускорение изменения значений свойств во время эффекта перехода.

    selector {
        transition-timing-function: ease;
        transition-duration: 1s;
    }

- linear - скорость одинакова от начала до конца
- ease - (по-умолчанию) медленно начинается, ускорение, замедление
- ease-in - начинается медленно, к концу ускоряется
- ease-out - начинается быстро, к концу замедляется
- ease-in-out - начинается и заканчивается медленно
- steps(число, start|end) - без анимации, пошаговый переход
    - start - движение начинается сразу
    - step-start - аналог steps(1, start)
    - step-end - аналог steps(1, end)

Вместо значений можно использовать `cubic-bezier()`, например аналог linear = `cubic-bezier(0.0, 0.0, 1.0, 1.0)`

## transition-delay
Задает задержку перед запуском эффекта перехода.

    selector {
        transition-delay: 1s;    /* Задержка перед запуском */
        transition-duration: 2s;
    }

`<время> [,<время>]*` - задается в "s" или "ms"  
Один из кейсов того зачем нужна задержка, например при всплытии меню, если с меню случайно на мгновение уйдет курсор, то меню скроется не сразу и у пользователя будет время для того чтобы вернуть курсор на область меню.

Также если хотите чтобы меню открывалось резко а закрывалось медленно, то вам нужно выставить такие параметры:

    .selector {
        transition-duration: 1s;
    }
    .selector:hover {
        transition-duration: 0;
    }

## transition
Универсальная запись всех свойств, относящихся к CSS-переходам.

    selector {
        transition: all 1s linear .25s;
    }

- none - отменяет переход
- порядок записи свойств:
    - transition-property
    - transition-duration
    - transition-timing-function
    - transition-delay

## Разное
Ссылки на различные easing-функции: easings.net/ru, cubic-bezier.com
