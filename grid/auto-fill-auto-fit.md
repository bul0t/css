# Auto-fill & Auto-fit
CSS grid может быть адаптивным даже без использования медиазапросов.

    <div class="grid grid--1">
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
    </div> <!-- .grid -->

    .grid {
      display: grid;
      gap: 8px;
      min-height: 300px;
      /* grid-template-columns: repeat(3, 200px); */
      /* grid-template-columns: repeat(auto-fill, 200px); */
      /* grid-template-columns: repeat(auto-fill, minmax(200px, auto)); */
      grid-template-columns: repeat(auto-fit, minmax(200px, auto));
      border: 3px solid #9b59b6;
      box-sizing: border-box;
    }

    .grid__item {
      background-color: #ecf0f1;
      height: 300px;
    }

- `grid-template-columns: repeat(3, 200px);` - трех колоночный макет, ширина ячейки 100px (адаптива нет)
- `grid-template-columns: repeat(auto-fill, 200px);`
  - `auto-fill` - анализирует пустое пространство и заполняет его следующим грид элементом
- `grid-template-columns: repeat(auto-fill, minmax(200px, auto));`
  - `minmax(min, max)` - минимальная и максимальная ширина колонки
- `grid-template-columns: repeat(auto-fit, minmax(200px, auto));`
  - `auto-fit` - если ячеек 3 и сумма их ширин меньше ширины контейнера, то три ячейки растянутся на весь контейнер, закрыв пустое пространство
