# Пример сложной сетки 1
На флексах такую сетку создать сложно. Создадим на грдах. В инспекторе включите подсветку гридов.  
Сетка состоит из 11 ячеек, расположены они в 3 строки и 6 колонок.  
Между ячейками есть зазор.

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
    </div> <!-- .grid -->

Сетка:

    .grid {
      display: grid;
      grid-template-columns: repeat(6, [col] 1fr);
      grid-template-rows: repeat(3, [row] 1fr);
      border: 3px solid #9b59b6;
      gap: 16px;
    }

Ячейки:

    .grid__item {
      min-height: 80px; // минимальная высота всех ячеек
    }

Первая ячейка занимает первый ряд и две колонки:

    .grid__item--1 {
      background-color: #ecf0f1;
      /* grid-column: 1 / 3; */
      /* grid-column: col 1 / col 3; */
      grid-column: span 2;
    }

Вторая ячейка растянута на 2 колонки и 2 ряда:

  .grid__item--2 {
    background-color: #ecf0f1;
    /* grid-column: col 3 / col 5;
    grid-row: row 1 / row 3; */
    grid-column: span 2;
    grid-row: span 2;
  }

Третья ячейка занимает 1 колонку и 2 ряда:

    .grid__item--3 {
      background-color: #ecf0f1;
      grid-column: span 1;
      grid-row: span 2;
    }

Девятая ячейка занимает 2 колонки и 1 ряд:

    .grid__item--9 {
      background-color: #ecf0f1;
      grid-column: span 2;
      /* grid-row: span 1; */
    }

Десятая ячейка занимает 2 колонки и 1 ряд:

    .grid__item--10 {
      background-color: #ecf0f1;
      grid-column: span 2;
      /* grid-row: span 1; */
    }
