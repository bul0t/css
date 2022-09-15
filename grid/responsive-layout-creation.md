# Responsive Layout Creation
Создание гибкого макета.

    <body class="container">
      <header class="element element--1">Header</header>
      <nav class="element element--2">
        Menu<br />Menu<br />Menu<br />Menu<br />Menu<br />Menu<br />Menu<br />Menu<br />Menu<br />Menu<br />
      </nav>
      <aside class="element element--3">Aside</aside>
      <main class="content">
        <div class="element element--4">Content</div>
        <div class="element element--5">Content Content Content Content</div>
      </main>
      <footer class="element element--6">Footer</footer>
    </body> <!-- .container -->

- в качестве грид контейнера выступает body
- макет трехколоночный `grid-template-columns: minmax(150px, 200px) 1fr minmax(150px, 200px);`
  - первая колонка `150-200px`
  - вторая колонка всё оставшееся пространство `1fr`
  - третья колонка `150-200px`

Привяжем части разметки header, nav, aside, main, footer с помощью свойства `grid-area` к сетке, для того чтобы используя в дальнейшем `grid-template-areas` к ним можно было обращаться:

    header { grid-area: header; }
    nav { grid-area: nav; }
    aside { grid-area: aside; }
    main { grid-area: main; }
    footer { grid-area: footer; }

С помощью `grid-template-areas` указываем как секции должны располагаться в макете:

    body {
      display: grid;
      gap: 8px;
      grid-template-columns: minmax(150px, 200px) 1fr minmax(150px, 200px);
      grid-template-areas: "header header header"
                            "nav main aside"
                            "footer footer footer";
      border: 3px solid #9b59b6;
      box-sizing: border-box;
    }

Прибьём футер к низу:
- зададим `body` высоту вьюпорта `height: 100vh;`
- зададим высоту каждому ряду, контентный ряд растянем `grid-template-rows: auto 1fr auto;`

Код:

    body {
      display: grid;
      gap: 8px;
      height: 100vh;
      grid-template-rows: auto 1fr auto;
      grid-template-columns: minmax(150px, 200px) 1fr minmax(150px, 200px);
      grid-template-areas: "header header header"
                            "nav main aside"
                            "footer footer footer";
      border: 3px solid #9b59b6;
      box-sizing: border-box;
    }

Добавим адаптив к макету с помощью медиазапросов:
- изменим свойства `body` (грид контейнера) на ширине экрана 600px
- трехколоночный макет должен стать двухколоночным
- секция `aside` должна быть скрыта

Код:

    @media (max-width: 600px) {
      aside {
        display: none;
      }
      body {
        grid-template-columns: repeat(2, 1fr);
        grid-template-areas: "header header"
                             "nav main"
                             "footer footer";
      }
    }

На ширине `375px` двухколоночный макет должен стать одноколоночным:

    @media (max-width: 375px) {
      body {
        grid-template-columns: 1fr;
        grid-template-areas: "header"
                             "nav"
                             "main"
                             "footer";
      }
    }

Свойство `grid-template-areas` отлично адаптирует макет на каждом из разрешений. Если изначально макет был трёхколоночным, то в каждой из строк мы указывали по три секции. При переходе на двухколоночный макет, в каждом ряду указывали по две секции. Когда макет становится одноколоночным, то указываем по одной секции.
