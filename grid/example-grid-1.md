# Пример сложной сетки 1
На флексах такую сетку создать сложно. Создадим на грдах. В инспекторе включите подсветку гридов.  
Сетка состоит из 11 ячеек, расположены они в 3 строки и 6 колонок.  
Между ячейками есть зазор.  

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
      grid-column: span 2;
      grid-row: span 2;
    }
