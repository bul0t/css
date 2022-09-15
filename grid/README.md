# CSS Grid
CSS Grid - используется для создания гибких сеток, а также удобного манипулирования каждым элементом сетки.  
Ключевая концепция фексбокса - это расположение главной и поперечной оси.  

CSS Grid делит видимую область, на колонки и строки:
- колонки создаются с помощью `grid-template-columns`
- строки создаются с `grid-template-rows`

Верстать можно 4мя способами:
- таблицы
- флоаты
- inline-block
- флексы
- гриды

## Grid: три колонки
Создадим трехколоночный макет на гридах:

    .grid {
      display: grid;
      grid-template-columns: 200px 1fr 300px;
    }
    .grid__item--1 {
      background-color: #f1c40f;
    }
    .grid__item--2 {
      background-color: #e67e22;
    }
    .grid__item--3 {
      background-color: #e74c3c;
    }

    <div class="grid">
      <div class="grid__item grid__item--1">grid__item--1</div>
      <div class="grid__item grid__item--2">grid__item--2</div>
      <div class="grid__item grid__item--3">grid__item--3</div>
    </div> <!-- .grid -->

`grid-template-columns` - отвечает за количество и размер колонок, размер можно задавать в пикселях, процентах, fr  
`fr` - фракция, фактор гибкости, коэффициент пропорциональности, который отталкивается от общего количества фракций

## Разное
- `display: inline-grid` похожа на модель flexbox
- https://css-tricks.com/snippets/css/complete-guide-grid/ - весь грид

Грид в первую очередь предназначен для создания лэйаута или каркаса страницы, а вот с позиционированием контента внутри этого каркаса работает flex. Они дополняют друг друга.

Сетки на гридах, более производительны чем, сетки на флексах.
