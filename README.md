# Assignment #2 — Advanced CSS (Flexbox & Grid)

**Student Name:** [Zhakanov Sanzhar]  
**Group:** [SE-2526]

Atlas Studio — многостраничный учебный сайт по Front-End Development. Пять заданий объединены общей навигацией, типографикой и коллекцией из девяти оригинальных SVG-иллюстраций. Все изображения и стили локальные: сайт работает без интернета.

## Страницы и задания

| Файл | Задание | Реализация |
| --- | --- | --- |
| `index.html` | Обзор | Ссылки на все пять заданий |
| `task0.html` | Task 0 — Navigation Bar | Flexbox, logo слева, links справа, gap, вертикальное центрирование |
| `task1.html` | Task 1 — Card Row | Три Flexbox-карточки одинаковой высоты: image, title, text, настоящий button; hover |
| `task2.html` | Task 2 — Page Layout | Grid с именованными областями header, sidebar, main, footer |
| `task3.html` | Task 3 — Image Gallery | Девять изображений, равные колонки и строки Grid, gap, caption overlay |
| `task4.html` | Task 4 — Portfolio | Flexbox-navbar, Grid для projects слева и sidebar справа, Flexbox внутри project cards |

## Технологии и структура

HTML5, CSS3, Flexbox, CSS Grid, media queries и SVG. Без JavaScript, CSS-фреймворков, внешних шрифтов и зависимостей.

```text
WEB_2/
├── index.html
├── task0.html
├── task1.html
├── task2.html
├── task3.html
├── task4.html
├── css/
│   └── style.css
├── assets/
│   └── images/
│       ├── favicon.svg
│       └── scene-01.svg … scene-09.svg
├── .gitignore
└── README.md
```

В `css/style.css`:

- `.navbar` и `.nav-links`: горизонтальный Flexbox, `align-items: center`, `gap`, `justify-content: space-between` у navbar.
- `.card-row`: Flexbox с `align-items: stretch`; `.card-content` — колонка; `margin-top: auto` выравнивает кнопки снизу. На мобильном карточки идут вертикально.
- `.grid-page`: `grid-template-columns`, `grid-template-rows` и `grid-template-areas: 'header header' 'sidebar main' 'footer footer'`; каждому разделу задан `grid-area`.
- `.gallery`: `repeat(3, minmax(0, 1fr))`, одинаковые строки по 240 px и gap 22 px. На планшете две колонки, на телефоне одна.
- `.portfolio-grid`: проекты слева, информация справа; `.project-card` и `.project-content` используют Flexbox. Footer находится вне внутренней сетки и занимает всю ширину.
- Media queries на 960 px и 680 px адаптируют сайт для планшета и телефона. Поддерживаются `prefers-reduced-motion` и сенсорные устройства.

Навигация выделяет активную страницу через `aria-current`. Есть skip-link, заметный keyboard focus и alt-тексты. Подписи галереи открываются при hover, keyboard focus и переходе на карточку по ссылке; на touch-устройствах они видны сразу. Кнопки в Task 1 используют обычные GET-формы, открывающие нужное изображение в галерее без JavaScript.

## Запуск

Откройте `index.html` в браузере. Сборка и установка пакетов не требуются.

Либо из папки проекта запустите:

```bash
python3 -m http.server 8000
```

Откройте `http://localhost:8000`. Остановка сервера: `Ctrl+C`.

## Персонализация

Замените `[Student Name]` своим полным именем, а `[Group]` своей группой во всех HTML-файлах и этом README. На `task4.html` также можно адаптировать текст о себе. Перед защитой изучите код и убедитесь, что можете объяснить каждое CSS-правило.

## Первый push в GitHub

Создайте пустой **public** репозиторий `assignment2-frontend` в своём GitHub, без автоматически созданных README, license и .gitignore. Затем выполните в папке проекта, заменив `YOUR_USERNAME` своим логином:

```bash
git init
git add index.html task0.html task1.html task2.html task3.html task4.html css assets README.md .gitignore
git commit -m "Complete Assignment 2: Flexbox and Grid"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/assignment2-frontend.git
git push -u origin main
```

Если используете другое название репозитория, замените `assignment2-frontend` в команде и URL сайта. Авторизуйтесь в GitHub при запросе Git.

## GitHub Pages

1. Откройте репозиторий на GitHub после push.
2. Перейдите в **Settings → Pages**.
3. В **Build and deployment → Source** выберите **Deploy from a branch**.
4. В **Branch** выберите **main** и папку **/(root)**.
5. Нажмите **Save**, дождитесь завершения публикации (иногда до 10 минут).
6. Откройте адрес `https://YOUR_USERNAME.github.io/assignment2-frontend/`.
7. Проверьте все страницы и изображения уже на опубликованном сайте. Относительные пути поддерживают размещение в подпапке репозитория.

Официальная инструкция: [GitHub Pages — publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site).

**Статус:** проект подготовлен к GitHub Pages; публикация в аккаунте студента выполняется после push и настройки Pages. Наличие локальных файлов само по себе не означает публикацию.

## Условия сдачи из задания

- Работа индивидуальная; одинаковые работы других студентов не допускаются.
- Опубликуйте сайт через GitHub Pages или Netlify и сдайте ссылку на GitHub-репозиторий до срока в Moodle.
- Защитите работу на практическом занятии. Без защиты задание получает 0.
- Оценивание: практическая часть и опубликованный сайт — 20 баллов, устные вопросы — 30, live coding — 50.
- Срок сдачи уточняется в Moodle; в приложенном документе конкретной даты нет.
- Для защиты повторите материалы лекций и ресурсы задания: Abitova G.A., Web technologies Front-End Development, Part 1 (2022), [видеоплейлист](https://www.youtube.com/playlist?list=PLPT6CF0r4E3rkvy1rLUKdDHf_HmWZeURW), [Flexbox Froggy](https://flexboxfroggy.com/), [box-sizing](https://www.w3schools.com/css/css3_box-sizing.asp), [Flexbox](https://www.w3schools.com/css/css3_flexbox.asp).

## Self-check

- [x] Task 0 complete
- [x] Task 1 complete
- [x] Task 2 complete
- [x] Task 3 complete
- [x] Task 4 complete
- [x] Navbar links work
- [x] Responsive design implemented
- [x] README created
- [x] Ready for GitHub Pages
- [ ] Published site verified online — после публикации в вашем аккаунте
