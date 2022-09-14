# Grid Elements Alignment
Выравнивание Grid элементов. Выравнивание CSS Grid очень похоже не выравнивание флексбокс.

Создадим сетку:

    <div class="grid">
      <div class="grid__item grid__item--1">
        Lorem ipsum
      </div>
    </div> <!-- .grid -->

    .grid {
      display: grid;
      grid-template-columns: 1fr; // Занять всю ширину
      grid-template-rows: 300px;
      border: 3px solid #9b59b6;
      align-items: stretch;
      justify-items: stretch;
    }
    .grid__item--1 {
      /* align-self: stretch; */
      /* align-self: start; */
      /* align-self: end; */
      align-self: center;

      /* justify-self: stretch; */
      /* justify-self: start; */
      /* justify-self: end; */
      justify-self: center;
    }

## Свойства применяемые к grid-элементу
- align-self - выравнивает элемент по вертикали
  - stretch - по-умолчанию, растягивает элемент по всей высоте контейнера
  - start   - элемент расположится в начале контейнера
  - end     - элемент расположится в конце контейнера
  - center  - элемент расположится в середине контейнера
- justify-self - выравнивает элемент по горизонтали
  - stretch - по-умолчанию, растягивает элемент по всей ширине контейнера
  - start   - выравнивает элемент слева
  - end     - выравнивает элемент справа
  - center  - выравнивает элемент по центру

## Свойства применяемые к grid-контейнеру
- align-items - выравнивает элементы по вертикали
  - stretch - по-умолчанию, растягивает контент по всей высоте контейнера
  - start   - элементы расположатся в начале контейнера
  - end     - элементы расположатся в конце контейнера
  - center  - элементы расположатся в середине контейнера
- justify-items - выравнивает элементы по горизонтали
  - stretch - по-умолчанию, растягивает элементы по всей ширине контейнера
  - start   - выравнивает элементы слева
  - end     - выравнивает элементы справа
  - center  - выравнивает элементы по центру
