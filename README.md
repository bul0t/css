# CSS
Руководство по языку CSS

- Анимации
  - Переходы (transition)
  - Трансформации (transform)
  - Анимации
- Переменные

## Разное
Чтобы расположить элемент { position: absolute } по середине, можно воспользоваться тремя способоами:
- left/top: 50% и добавить отрицательные margin
- left/top: calc(50% - ширина/высота элемента / 2)
- left/top: 50% и добавить свойство `transform: translate;`

Пример центрирования с помощью `calc()` и `transform`:

    width: 50px;
    height: 50px;
    left: calc(50% - 25px);
    top: calc(50% - 25px);

    или что более удобно (если не используете другие трансформации на элементе):

    width: 50px;
    height: 50px;
    left: 50%;
    top: 50%;
    transform: translate(-50%, -50%);
