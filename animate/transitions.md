# CSS переходы (transitions)
Переход из одного состояния в другое, за определённое время, меняются значения CSS-свойств. Позволяют задать плавный переход CSS-свойствам, значения свойств изменяются постепенно в течении определенного (заданного) промежутка времени.

- анимируемые CSS-свойства
- transition-property
- transition-duration
- transition-timing-function
- transition-delay
- transition

## transition-property
Определяет свойства, к которым будет применен эффект перехода.

    selector {
        transition-property: all; /* По умолчанию all */
        transition-duration: 1s;
    }

- none - эффект перехода не будет применен
- all - эффект перехода применится ко всем доступным свойствам
- `<свойство> [,<свойство>]*` - указывается одно или несколько свойств, к которым применится эффект перехода

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

## transition-delay
Задает задержку перед запуском эффекта перехода.

    selector {
        transition-delay: 1s;    /* Задержка перед запуском */
        transition-duration: 2s;
    }

`<время> [,<время>]*` - задается в "s" или "ms"

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
