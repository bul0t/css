# Grid Nesting
Вложенность grid сеток. Grid сетки можно вкладывать друг в друга. Это удобно при создании больших сайтов и проектировании сложных дизайнов.

    <div class="grid grid--1">
      <div class="grid__item grid__item--1">1</div>
      <div class="grid__item grid__item--2">2</div>
      <div class="grid__item grid__item--3">3</div>
      <div class="grid__item grid__item--4">4</div>
      <div class="grid grid--2 grid__item grid__item--5">
        <div class="grid__item grid--2__item grid__item--6">6</div>
        <div class="grid__item grid--2__item grid__item--7">7</div>
        <div class="grid__item grid--2__item grid__item--8">8</div>
        <div class="grid__item grid--2__item grid__item--9">9</div>
      </div>
      <div class="grid__item grid__item--10">10</div>
    </div> <!-- .grid -->

    .grid {
      display: grid;
      gap: 8px;
      grid-template-columns: repeat(auto-fill, minmax(200px, auto));
      border: 3px solid #9b59b6;
      box-sizing: border-box;
    }
    .grid--1 {
      height: 100vh;
    }
    .grid--2 {
      grid-template-columns: repeat(2, auto);
    }

    .grid__item {
      background-color: #ecf0f1;
    }

    .grid--2__item {
      background-color: #bdc3c7;
    }
