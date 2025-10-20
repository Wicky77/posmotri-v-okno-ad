*,
*::before,
*::after {
  box-sizing: border-box;
}

html {
  block-size: 100%;
}

.page {
  display: flex;
  align-items: center;
  justify-content: center;
  inline-size: 1200px;
  block-size: 100%;
  margin: auto;
  color: #fff;
  font-family: 'Fira Sans Condensed', sans-serif;
  font-size: 18px;
  background-color: #1b1919;
}

.content {
  display: flex;
  flex-direction: row;
  align-items: flex-end;
  gap: 30px;
  width: 100%;
  max-width: 1140px;
  padding: 0 30px; /* горизонтальные отступы */
  margin: 0 auto; /* центрирование */
}

/* Стили для формы поиска */
.search-form {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-start;
  gap: 40px;
  width: 100%;
}

/* Контейнер для списка карточек */
.content__details {
  display: flex;
  flex-direction: column;
  flex: 1; /* растягиваем на всю доступную ширину */
  height: 100%; /* растягиваем на всю доступную высоту */
  gap: 26px; /* отступ между заголовком и зоной с карточками */
}
.result__video-container{
  margin-bottom:16px;
  height:386px;
  width: 711px;
  position: relative;
}

.result__video {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
.content__list-container {
  height: 300px; /* фиксированная высота */
  overflow-y: auto; /* вертикальный скролл при переполнении */
  position: relative;
}

.content__video-card { /*скролл */
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: space-between;
  width: 100%;
  max-width: 100%;
}

.content__video-card-thumbnail { /* параметры карточек скролла */
  width: 194px;
  height: 103px;
  object-fit: cover;
  object-position: center;
}

.content__video-card-description-container { /* текст в карточке над скроллом */
  flex-grow: 1; /* всё, что не занято */
  min-width: 0;
  overflow: hidden;
  width: 100%;
}

.content__list {
  display: flex;
  flex-direction: column;
  row-gap: 30px;
}

/* Город, время суток */
.search-form__fieldset-title {
  font-weight: 400; /* вес шрифта(толщина) */
  font-size: 18px;
  margin-bottom: 5px; /* отступ снизу */
}

/* главный заголовок */
.title {
  font-family: 'Oswald';
  font-weight: 700;
  font-size: 75px;
  line-height: 0.94;
  text-transform: uppercase;/*верхний регистр*/
}

.content__accent {
  color: #545050; /* акцент на первыедые буквы */
}

/* ссылки */
.content__card-link {
  text-decoration: none; /* подчёркивание */
  color: #FFFFFF;
}

/* название городов*/
.content__video-card-title {
  font-weight: 700;
  font-size: 30px;
  line-height: 1;
  margin-bottom: 6px;
  overflow: hidden;/* обрезка длинного текста многоточием */
  text-overflow: ellipsis;  /* убирает лишнее */
  white-space: nowrap; /* многоточие */
  max-width: 100%; /* чтобы не выходил за предел */
  width: 100%;
  display: block;
}

/* описание */
.content__video-card-description {
  font-weight: 400;
  font-size: 18px;
  line-height: 16.2px;
  margin: 0;
  display: -webkit-box;/*обрезка*/
  -webkit-line-clamp: 4; /* ограничиваем до 4 строк */
  -webkit-box-orient: vertical;
  overflow: hidden;
}

/* стили для скрытия элементов, писала не я, дали в задании*/
.visually-hidden {
  position: absolute;
  inline-size: 1px;
  block-size: 1px;
  overflow: hidden;
  clip: rect(0 0 0 0);
  clip-path: inset(50%);
  white-space: nowrap;
}

/*  fieldset и кнопку в строку */
.search-form {
  display: flex;
  flex-direction: row;
  justify-content: space-between;
  align-items: flex-start;
  gap: 40px;
  width: 100%;
}

/* чекбоксы в линию */
.search-form__checkbox-list {
  display: flex;
  gap: 15px;
}

/* сброс border у fieldset */
.search-form__fieldset {
  border: none;
  flex: 1;
}

/* стили для строки ввода */
.search-form__label {
  display: flex;
  flex-direction: row;
  align-items: center;
  gap: 5px;
  width: fit-content;/* ширина по содержимому */
  cursor: pointer;/* курсор-указатель при наведении */
}

/* стилизация строки ввода */
.search-form__textfield {
  border: none;
  border-top: 1px solid currentColor;/* Верхняя граница текущим цветом */
  border-bottom: 1px solid currentColor;
  color: #fff;
  font-family: inherit;/* Наследует шрифт от родителя */
  font-size: 18px;
  background-color: transparent;/* Прозрачный фон */
  appearance: none;/* Убирает браузерные стили */
  padding: 2.5px 0;
  width: 225px;
}

.search-form__textfield:focus {/* Убираем стандартное браузерное выделение при фокусе */
  outline: none;
}

/*применяет стили к лейблу, если внутри него есть элемент в состоянии фокуса*/
.search-form__label:has(:focus-visible) {
  outline: 1px solid #fff;/* Белая обводка вокруг строки ввода */
  outline-offset: 1px;
}

/* Стилизация псевдочекбокса */
.search-form__pseudo-checkbox {
  display: flex;
  align-items: center;
  justify-content: center;
  width: 19px;
  height: 19px;
  border: 1px solid #fff;
  position: relative;
}

/* Псевдоэлемент для отмеченного состояния */
.search-form__pseudo-checkbox::after {
  content: "";/* Обязательно для псевдоэлемента */
  width: 15px; /* на 1px меньше с каждой стороны */
  height: 15px;
  background-color: #fff;
  opacity: 0;/* Изначально невидим */
  transition: opacity 0.3s;/* Плавное появление */
}

.search-form__checkbox:checked + .search-form__pseudo-checkbox::after {
  opacity: 1;/* Показываем внутренний квадрат при отмеченном чекбоксе */
}

/* Подчёркивание текста при наведении на лейбл */
.search-form__label:hover .search-form__label-text {
  text-decoration: underline;
}

/* Стили для кнопки */
.button {
  background: #00000000;
  border: 1px solid #fff;
  color: #fff;
  font-family: inherit;
  font-size: 18px;
  cursor: pointer;/* Курсор-указатель */
  padding: 0;
}

.search-form__submit-button {
  align-self: flex-end;
  padding: 5px 73px;
}

/* Индивидуальные стили для кнопки "Найти" */
.search-form__submit-button {
  align-self: flex-end;
  padding: 5px 73px;
}

/* Индивидуальные стили для кнопки "Показать ещё" */
.more-button {
  width: 100%;
  padding: 5px 0;
}

/* Состояния для всех кнопок */
.button:hover {
  text-decoration: underline;
}

.button:active {
  background: #545050;
}

.button:focus {
  outline: none;
}

.button:focus-visible {
  outline: 1px solid #fff;
  outline-offset: 1px;
}
/* Стилизация карточки */
.content__card-link {
  display: block; /* делаем карточку блочным элементом */
  text-decoration: none;
  color: #FFFFFF;
  padding: 2px; /* отступ для обводки */
  cursor: pointer;
}

/* Располагаем содержимое карточки в строку */
.content__video-card {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  justify-content: space-between;
  width: 100%;
  max-width: 100%;
  min-width: 0;
  padding: 2px 0; /* отступы между элементами */
}

/* Текущая (активная) карточка */
.content__card-link_current {
  background: #545050;
}

/* Карточка при наведении */
.content__card-link:hover .content__video-card-title,
.content__card-link:hover .content__video-card-description {
  text-decoration: underline;
}

/* Карточка в активном состоянии */
.content__card-link:active {
  background: #545050;
}

/* Сброс стандартного фокуса */
.content__card-link:focus {
  outline: none;
}

/* Кастомная обводка при фокусе с клавиатуры */
.content__card-link:focus-visible {
  outline: 1px solid #fff;
  outline-offset: 1px;
}

/* Отступы для элементов списка чтобы обводка не прилипала */
.content__list-item {
  padding: 0 3px;
}



/* Остальные стили остаются без изменений */
h1,
h2,
h3,
h4,
p,
ul,
ol,
li,
blockquote,
fieldset {
  margin: 0;
  padding: 0;
}

ul,
ol {
  list-style: none;
}

/* Кастомный скроллбар */
.content__list-container::-webkit-scrollbar {
  width: 4px;
}

.content__list-container::-webkit-scrollbar-track {
  background: rgb(217 217 217 / 10%);
}

.content__list-container::-webkit-scrollbar-thumb {
  background-color: #D9D9D9;
}

