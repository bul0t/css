# CSS Grid

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
