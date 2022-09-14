# Grid Lines & Grid Areas
Работаем с грид линиями и areas.

Управление размерами и позицией grid-элемента.

    grid-template-columns: repeat(3, 1fr);
    grid-template-rows: repeat(3, 1fr);

Создали трехколоночный макет, с тремя строками.  
Если допусти у вас будет всего три ячейки `div`, то остальные шесть будут пустыми без `div` но место всеравно займут, чтобы увидеть их границы нужно в инспеторе нажать на кнопку `grid` рядом с контейнером.

Сама сетка считается не по строкам или колонкам а по границам (lines), например у трехколоночной сетки будет 4 вертикальных линии, а у четырехстрочной сетки будет 5 горизонтальных линий.

    <div class="grid">
      <div class="grid__item grid__item--1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, optio?</div>
      <div class="grid__item grid__item--2">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Labore, alias!</div>
      <div class="grid__item grid__item--3">Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet, sit!</div>
    </div> <!-- .grid -->

Помещаем `grid__item--1` в нижний правый угол и растягиваем на три строки (на всю колонку).

    .grid__item--1 {
      grid-column-start: 3;
      grid-column-end: 4;
      grid-row-start: 1;
      grid-row-end: 4;
    }

`grid-column-start: 3;` определяем начало ячейки по вертикальной линии.  
`grid-column-end: 4;` определяем конец ячейки по верикальной линии.  
`grid-row-start: 1;` определяем начало ячейки по горизонтальной линии.  
`grid-row-end: 4;` определяем конец ячейки по горизонтальной линии.

Линиям можно давать имена.  
По умолчанию, нумерация линий происходит от верхнего левого угла, но можно отчет вести от нижнего правого угла (с отрицательными величинами).

Сокращённая запись:

    .grid__item--1 {
      grid-column: 3 / 4;
      grid-row: 1 / 4;
    }

Еще более сокращённая запись `grid-area`:

    .grid__item--1 {
      grid-area: 1 / 3 / 4 / 4;
    }

Порядок следования чисел:
- `grid-row-start`
- `grid-column-start`
- `grid-row-end`
- `grid-column-end`
