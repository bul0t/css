# Animation
Анимация - последовательное изменение свойств объекта, создающее эффект движения или "оживления" интерфейса.
Чтобы анимация заработала нужно использовать как минимум три сущности: @keyframes и два свойства animation-name, animation-duration.

- @keyframes
- animation-name
- animation-duration
- Временная шкала (TimeLine)
- Установка ключевых кадров
- Группировка ключевых кадров
- animation-iteration-count
- animation-delay
- animation-direction
- animation-fill-mode
- animation-timing-function
- animation-play-state
- animation

## @keyframes
Каждая анимация строится на основе ключевых кадров.  
В ключевых кадрах описывается состояние элемента.  
К которому в итоге должен прийти этот элемент.  

    @keyframes имя_анимации { список правил }

@keyframes устанавливает ключевые кадры, которые определяют какие свойства на каком шаге будут анимированы.

Ключи `from`, `to`:

    @keyframes имя_анимации { 
        from { свойство } /* из какого состояния */
        to { свойство }   /* к какому состоянию прийти */
    }

Ключи проценты:

    @keyframes имя_анимации {
        0% { свойство }
        25% { свойство }
        50% { свойство }
        75% { свойство }
        100% { свойство }
    }

Пример:

    .arc {
      color: #e74c3c;
      background-color: #e74c3c;
      width: 100px;
      height: 100px;
      animation-duration: 3s;
      animation-name: square;
      transform: rotate(0);
    }

    @keyframes square {
      0% {
        background-color: #e74c3c;
        transform: rotate(0);
      }
      17% {
        background-color: #e67e22;
        transform: rotate(60deg);
      }
      34% {
        background-color: #f1c40f;
        transform: rotate(120deg);
      }
      51% {
        background-color: #2ecc71;
        transform: rotate(180deg);
      }
      68% {
        background-color: #3498db;
        transform: rotate(240deg);
      }
      85% {
        background-color: #1f2f98;
        transform: rotate(300deg);
      }
      100% {
        background-color: #9b59b6;
        transform: rotate(360deg);
      }
    }

Если ключевые кадры в тот или иной момент имеют одинаковые свойства, то их можно группировать:

    @keyframes имя_анимации {
        0%, 100% { свойство }
        50% { свойство }
    }

Создаём перекат элемента вправо и обратно:

    .arc {
      background-color: #e74c3c;
      width: 100px;
      height: 100px;
      animation-name: roll;
      animation-duration: 3s;
      animation-iteration-count: 3;
    }

    @keyframes roll {
      0%, 100% {
        /* transform: none; */
        transform: translateX(0) rotate(0);
        /* или вообще не указывать 0%, 100% */
      }
      50% {
        background-color: #f1c40f;
        transform: translateX(200px) rotate(360deg);
        border-radius: 50%;
      }
    }

## animation-name
Можно указать несколько имён анимаций через запятую. `none` - отменяет анимацию.

    animation-name: имя_анимации;

## animation-duration
Задаёт длительность выполения анимации.

    .arc {
      animation-name: square;
      animation-duration: 3s;
    }

    @keyframes square {
      from {
        transform: translate(0, 0) scale(1) rotate(0);
      }
      to {
        transform: translate(100px, -50px) scale(2) rotate(45deg);
        background-color: #9b59b6; // можно добавить другие свойства, например изменения цаета
      }
    }

## Особенности использования CSS animation
- после анимации, элемент возвращается в изначальное состояние
  - если хотите сохранить конечное состояние, то нужно добавить свойство 
- при указании ключей `from`, `to` во `from` нужно указать стили начального состояния
  - стили указанные во `from` во время запуска анимации, никак не влияют на стили элемента указанные до запуска
  - если стили до запуска совпадают со стилями в `from`, то их можно не записывать, убрав ключ `from` (обычно работают без него)

## animation-iteration-count
Определяет, сколько раз будет повторяться анимация.

- `число` - анимация проигрывается определенное количество раз
- `0` - анимация проигрывается мгновенно, эффект анимации виден не будет
- `infinite` - анимация проигрывается бесконечно

Пример:

    selector {
      animation-name: name;
      animation-duration: 2s;
      animation-iteration-count: 3;
    }

## animation-delay
Устанавливает задержку перед началом выполнения анимации.  
Время можно задавать в секундах или миллисекундах.  
Через запяту можно указывать несколько время.

    selector {
      animation-name: roll;
      animation-duration: 3s;
      animation-iteration-count: 3;
      animation-delay: 2s;
    }

## Применяем к одному элементу сразу несколько анимаций

    animation-name: roll, color;
    animation-duration: 3s;
    animation-iteration-count: 3;
    animation-delay: 2s;

При необходимости к `color` можно добавить свои значения времени выполнения, повтора, задержки и т.д..

    animation-name: roll, color;
    animation-duration: 3s, 4s;
    animation-iteration-count: 3, 4;
    animation-delay: 2s, 4s;

## animation-direction
Направление проигрывания анимации. Анимция может двигаться в 2х направлениях, от начала до конца и наоборот.

- normal - анимация проигрывается в обычном направлении, от начала до конца
- reverse - анимация проигрывается в обратном направлении, с конца до начала

Значения, зависимые от количества проигрываний анимации:

- alternate - нечётные проигрывания воспроизводятся в прямом направлении, а чётные - в обратном.
- alternate-reverse - нечётные проигрывания воспроизводятся в обратном направлении, а чётные - в прямом

Пример:

    .arc {
      background-color: #e74c3c;
      width: 100px;
      height: 100px;
      animation-name: roll;
      animation-duration: 3s;
      animation-iteration-count: 3;
      animation-direction: reverse;
    }

    @keyframes roll {
      100% {
        transform: translateX(200px) rotate(360deg);
        background-color: #f1c40f;
        border-radius: 50%;
      }
    }

## animation-fill-mode
Оределяет, как нужно применять стили к объекту анимации до и после ее выполнения.

- `forwards` - элемент сохраняет конечное состояние анимации, т.е. свойства, записанные в последнем ключевом кадре будут применены к элементу после завершения анимации
- `backwards` - свойства описанные в первом ключевом кадре, будут сразу применены к элементу еще до начала проигрывания анимации, даже при установленной задержке перед началом проигрывания анимации, конечное состояние не сохраняет
- `both` - объединяет в себе свойства forwards и backwards, т. е. до начала анимации элементу присваивается состояние первого ключевого кадра, а после завершения - конечное состояние анимации сохраняется
- `none` - анимация не будет применять какие-либо стили к элементу как до, так и после проигрывания анимации, значение по-умолчанию

Пример:

    .arc {
      background-color: #e74c3c;
      width: 100px;
      height: 100px;
      animation-name: roll;
      animation-duration: 1s;
      animation-iteration-count: 3;
      /* animation-direction: alternate; */
      animation-fill-mode: forwards;
    }

    @keyframes roll {
      100% {
        transform: translateX(200px) rotate(360deg);
        background-color: #f1c40f;
        border-radius: 50%;
      }
    }

Поведение параметров зависит от значений направления (direction) и количества проигрываний (iteration-count) анимации.

## animation-timing-function
Определяет скорость и ускорение изменения значений свойств между ключевыми кадрами во время проигрывания анимации.

  selector {
    animation-name: name;
    animation-duration: 2s;
    animation-timing-function: ease-in-out;
  }

Параметры:

- ease (по-умолчанию)
- ease-in
- ease-out
- ease-in-out
- linear
- step-start
- step-end
- steps(<число>, start | end)
- cubic-bezier(<число>, <число>, <число>, <число>)

## animation-play-state
Устанавливает состояние анимации, т.е. анимация проигрывается или стоит на паузе.

    selector {
      animation-name: name;
      animation-duration: 2s;
      animation-play-state: running;
    }

Параметры:
- `paused` - анимация стоит на паузе
- `running` - анимация проигрывается

Создадим анимацию, где элемент будет двигаться по прямой и при наведении на элемент, анимация движения встанет на пайзу и запустится анимация ховера, затем при отведении мыши от элемента, продолжится анимация движения.

    .arc {
      position: relative;
      background-color: #e74c3c;
      width: 100px;
      height: 100px;
      animation-name: roll;
      animation-duration: 7s;
      animation-timing-function: linear;
      animation-iteration-count: infinite;
      animation-play-state: running;
    }

    .arc:hover {
      animation-name: roll, roll-hover;
      animation-duration: 7s, 0.25s;
      animation-timing-function: linear, ease;
      animation-iteration-count: infinite, 1;
      animation-fill-mode: none, forwards;
      animation-play-state: paused, running;
    }

    @keyframes roll {
      0% {
        left: 400px;
        transform: rotate(0);
        background-color: #f1c40f;
      }
      100% {
        left: -400px;
        transform: rotate(-360deg);
        background-color: #e74c3c;
        border-radius: 50%;
      }
    }

    @keyframes roll-hover {
      to {
        transform: rotate(30deg) scale(2) translate(7%, -12%);
      }
    }

## animation
Универсальная запись всех свойств, относящихся к CSS-анимациям, соблюдайте порядок записи свойств:

    selector {
      animation: имя_анимации 3s ease 1s 7 reverse forwards;
    }

Параметры:

- `none` - отменяет анимацию

Порядок записи свойств:
- animation-name
- animation-duration
- animation-timing-function
- animation-delay
- animation-iteration-count
- animation-direction
- animation-fill-mode
- animation-play-state

## Разное
- animate.style - animate.css, библиотека с анимациями
- animista.net - animista.net - сервис с анимациями
- minimamente.com/project/magic/ - Magic Animations CSS3, библиотека с анимациями
