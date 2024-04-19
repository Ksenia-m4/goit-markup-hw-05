- Создай репозиторий goit-markup-hw-05.
- Склонируй созданный репозиторий и скопируй в него файлы предыдущей работы.
- Добавь анимацию декоративных эффектов для страниц макета домашнего задания #5.
- Настрой GitHub Pages и добавь ссылку на живую страницу в шапку GitHub-репозитория.

  **Критерии приёма работы наставником**

  _Проект_

- Все стили написаны в одном файле styles.css, который находится в папке css.
- Исходный код отформатирован при помощи Prettier.
- Все изображения и текстовый контент взяты из макета.
- На всех HTML-страницах подключен нормализатор стилей modern-normalize.
- Код написан следуя руководству.
- Скрипт модального окна подключен в HTML отдельным файлом modal.js.

_Разметка_

- Выполнена HTML-разметка всех элементов макета.
- Теги использованы согласно их семантического смысла.

_Оформление_

- Для всех эффектов ховера и фокуса (цвет, фон, тень) сделаны переходы. Время - 250ms, функция распределения времени - cubic-bezier(0.4, 0, 0.2, 1).

- В переходах и анимациях явно указаны анимируемые свойства. Нигде нет значения all.

- В секции Чем мы занимаемся текст с фоном спозиционирован поверх изображения.

- В главной навигации, при помощи псевдоэлемента ::after, сделано подчёркивание ссылки текущей страницы (на которой сейчас находится пользователь).

- Синий оверлей с текстом на карточках страницы Портфолио появляется при ховере в любом месте карточки.

- Синий оверлей в карточках страницы Портфолио выезжает снизу, как показано на видео.

- У псевдоэлементов нет текстового контента в свойстве content. Они использованы исключительно для декоративного оформления.

_Модальное окно_

- Выполнена разметка и оформление «бекдропа» (тёмного полупрозрачного фона) модального окна.

- «Бекдроп» заполняет 100% высоты и ширины вьюпорта браузера и фиксирован в нём.

- Выполнена разметка и оформление модального окна.

- Модальное окно вертикально и горизонтально спозиционировано посередине бекдропа.

- Выполнена разметка и оформление кнопки закрытия модального окна в верхнем правом углу.

- Изначально модальное окно и бекдроп скрыты при помощи класса is-hidden на бекдропе, в селекторе которого используются свойства visibility, opacity и pointer-events.

- Если убрать с бекдропа класс is-hidden - появляется бекдроп и модальное окно.

- Появление и скрытие модального окна анимировано при помощи перехода с произвольным эффектом, например scale или translate, и opacity.

_Открытие/закрытие модального окна_

> Модальное окно с формой заявки открывается по клику на кнопку "Заказать услугу". Для того чтобы скрипт сработал необходимо добавить в разметку специальные атрибуты, по которым скрипт ищет элементы:
> data-modal-open - на кнопку открытия модального окна.
> data-modal-close - на кнопку закрытия модального окна.
> data-modal - на бекдроп модального окна.
> После чего, перед закрывающим тегом body добавить тег script со ссылкой на файл скрипта для модально окна. Можно посмотреть видео-инструкцию.

<body>
  <!-- Вся твоя разметка, включая разметку модалки -->

  <!-- Ставим перед закрывающим тегом body -->
  <script src="./js/modal.js"></script>
</body>

Скрипт который необходимо скопировать и вставить в файл modal.js.

(() => {
const refs = {
openModalBtn: document.querySelector("[data-modal-open]"),
closeModalBtn: document.querySelector("[data-modal-close]"),
modal: document.querySelector("[data-modal]"),
};

refs.openModalBtn.addEventListener("click", toggleModal);
refs.closeModalBtn.addEventListener("click", toggleModal);

function toggleModal() {
refs.modal.classList.toggle("is-hidden");
}
})();
