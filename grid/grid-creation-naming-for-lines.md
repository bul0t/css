# Grid creation & naming for lines
Именование grid-линий, создание сетки, позиционирование элементов.

## Именование линий
Именование линий в CSS grid делает разработку более гибкой, так как каждая линия может быть именована своим именем.

Создадим небольшую сетку по примеру Bootstrap:
- зададим имена для колонок в свойстве `grid-template-columns`
- зададим имена для строк в свойстве `grid-template-rows`
- зададим 12 колонок и 8 строк

Имена задаются в квадратных скобках:

    grid-template-columns: repeat(3, [col] 1fr);
    grid-template-rows: repeat(3, [row] 1fr);

style.css:

    .grid {
      display: grid;
      grid-template-columns: repeat(12, [col] 1fr);
      grid-template-rows: repeat(8, [row] 1fr);
      border: 3px solid #9b59b6;
      column-gap: 16px;
    }

index.html:

    <div class="grid">
      <div class="grid__item grid__item--1">1</div>
      <div class="grid__item grid__item--2">2</div>
      <div class="grid__item grid__item--3">3</div>
      <div class="grid__item grid__item--4">4</div>
      <div class="grid__item grid__item--5">5</div>
      <div class="grid__item grid__item--6">6</div>
      <div class="grid__item grid__item--7">7</div>
      <div class="grid__item grid__item--8">8</div>
      <div class="grid__item grid__item--9">9</div>
      <div class="grid__item grid__item--10">10</div>
      <div class="grid__item grid__item--11">11</div>
      <div class="grid__item grid__item--12">12</div>
    </div> <!-- .grid -->

Ячейка занимает колонки:

    .grid__item--3 {
      background-color: #e74c3c;
      // grid-column: 1 / 4;         // ячейка занимает 3 колонки
      // grid-column: col 1 / col 4; // ячейка занимает 3 колонки
      // grid-column: 1 / span 4;    // ячейка занимает 4 колонки
      grid-column: col 1 / span 4;   // ячейка занимает 4 колонки
      grid-column: span 4;           // ячейка занимает 4 колонки
    }

Ячейка занимает строки:

    grid-row: row 1 / span 4;

`span` не выходит и не растягивает границы родителя, можно записать `span 20` и он не выйдет за границы 12-колоночной сетки.

## Разное
При именовании линий возможны конфликты, поэтому старайтесь давать разные имена линий, для разных сеток.
