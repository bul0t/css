# scale()
Изменяем масштаб элемента.

- transform: scaleX(2);
- transform: scaleY(0.5);
- transform: scale(-1, 2);
- transform: scale(4); // изменение сразу по 2м осям
- transform: scaleX(3) scaleY(4);

Пример:

    transform: scaleX(2);

`2` коэфициент во сколько раз увеличить, уменьшить масштаб. Может принимать положительные, отрицательные (зеркально отражается), дробные значения.

  .arc {
    background-color: #2ecc71;
    width: 50px;
    height: 50px;
    position: absolute;
    width: 50px;
    height: 50px;
    left: calc(50% - 25px);
    top: calc(50% - 25px);
    transition-property: transform;
    transition-duration: 1s;
  }
  .arc:hover {
    transform: scaleX(2);
    /* transform: scaleY(2); */
    /* transform: scale(2, 2); */
  }
