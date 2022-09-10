# grid-template-columns (rows)
`grid-template-columns` - может принимать несколько параметров и первые параметры это либо относительные либо абсолютные единицы: px, em, rem, % и т.д.

Контейнер будет занимать всю ширину родительского элемента не зависимо от того какие размеры у колонок:

    grid-template-columns: 1px 1px 1px;

Второй параметр это фракции (коэфициент пропорциональности):

    grid-template-columns: 200px 1fr 300px;

`1fr` - займет всю оставшуюся ширину

    grid-template-columns: 1fr 2fr 3fr;

1fr - займет одну треть от половины
2fr - займет две трети от половины
3fr - займет половину

## min-content / max-content
Ширина колонок может быть задана по минимальному и максимальному размеру контента. Колонки будут ориентироваться на размеры контента находящегося в них и подстраиваться под него.

    <div class="grid">
      <div class="grid__item grid__item--1">Lorem ipsum dolor sit amet consectetur adipisicing elit. Quam, optio?</div>
      <div class="grid__item grid__item--2">Lorem ipsum dolor sit amet, consectetur adipisicing elit. Labore, alias!</div>
      <div class="grid__item grid__item--3">Lorem ipsum dolor sit amet consectetur adipisicing elit. Eveniet, sit!</div>
    </div> <!-- .grid -->

    .grid {
      display: grid;
      grid-template-columns: min-content 200px max-content;
    }

`min-content` - первая колонка подстраивается под размер самого длинного слова
`200px` - вторая колонка равна по ширине 200px
`max-content` - третья колонка равна длине всего текста который выстраивается в одну строку

## minmax()
Минимальная, максимальная ширина колонки.

    grid-template-columns: 200px 300px minmax(100px, 300px);

Третья колонка в зависимости от условий будет растягиваться и сжиматься от 100px до 300px.

## repeat()
repeat() - дублирование части сетки. Создаём трехколночный макет, чтобы все три колонки были одинаковой величины.

    grid-template-columns: repeat(3, 1fr);

## Разное
- в случае не задания каких либо размеров каждой из колонок, её значение по-умолчанию будет `auto`.
- `grid-column-gap: 16px;` - расстояние между колонками (устаревшее), используйте `column-gap: 16px;`