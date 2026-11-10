<div align="center">

<img src="docs/screenshots/00-hero.png" alt="Брендбук PartnerOffice" width="100%">

# Interparts · Брендбук PartnerOffice

**Единый визуальный язык кабинета партнёров: цвет, типографика, сетка, иконки, 14 групп компонентов и шаблоны страниц.**

![version](https://img.shields.io/badge/версия-1.0-005bff?style=flat-square)
![tokens](https://img.shields.io/badge/токенов-316-203148?style=flat-square)
![components](https://img.shields.io/badge/компонентов-25-1dae40?style=flat-square)
![icons](https://img.shields.io/badge/иконок-34-f7b200?style=flat-square)
![font](https://img.shields.io/badge/шрифт-Onest-e83827?style=flat-square)
![deps](https://img.shields.io/badge/зависимостей-0-6183a2?style=flat-square)

[Открыть брендбук](#-как-открыть) · [Цвет](#-цвет) · [Типографика](#-типографика) · [Компоненты](#-компоненты) · [Шаблоны](#-шаблоны-страниц) · [Подключение](#-подключение)

</div>

---

## Что это

Брендбук интерфейса **PartnerOffice** — кабинета партнёров. Интерфейс повторяет привычный партнёрам рабочий инструмент «Турбо ПВЗ» (дизайн-система *ozi*): те же цвета, шрифт, сетка, формы, навигация и иконки, поэтому с PartnerOffice работают без обучения.

Брендбук — это **одна самодостаточная HTML-страница** без сборки фронтенда и внешних зависимостей: иконки встроены, стили подключены относительными путями. Рядом лежат токены, готовые CSS-компоненты и генератор страницы.

| Принцип | Суть |
|---|---|
| **1. Привычность** | Те же отступы, цвета и порядок элементов, что в рабочем ПО Ozon. Свои контролы не изобретаем |
| **2. Плотность и ясность** | Таблицы и фильтры в первую очередь. Один синий акцент, остальное нейтральное. Цвет несёт смысл статуса |
| **3. Токены, а не значения** | Любой цвет, тень и непрозрачность берутся из `tokens/ozon-tokens.css`. Тёмная тема включается классом `.theme-dark` |

<img src="docs/screenshots/01-intro.png" alt="Введение" width="100%">

## 🚀 Как открыть

```bash
git clone https://github.com/EvgeniBondarev/-Interparts-brandbook.git
cd -Interparts-brandbook
open brandbook/index.html          # macOS; на Linux — xdg-open, на Windows — start
```

Или через локальный сервер:

```bash
python3 -m http.server 8080
# затем http://localhost:8080/brandbook/index.html
```

> Пересборка страницы после правок токенов, иконок или компонентов: `python3 build/build_brandbook.py`

---

## 🎨 Цвет

Палитра построена на одном основном синем `#005bff` и нейтральных серо-синих. Статусы: зелёный — успех, жёлтый — предупреждение, красный и малиновый — ошибка и срочное. Фон приложения белый, блоки отделяются полупрозрачной подложкой.

<img src="docs/screenshots/02-colors-1.png" alt="Цвет: бренд, применение, базовые ряды" width="100%">

<details>
<summary><b>Ещё: акцентные оттенки и семантические токены (светлая и тёмная темы)</b></summary>
<br>

<img src="docs/screenshots/02-colors-2.png" alt="Цвет: акцентные оттенки" width="100%">
<img src="docs/screenshots/02-colors-3.png" alt="Цвет: семантические токены, текст и фоны" width="100%">
<img src="docs/screenshots/02-colors-4.png" alt="Цвет: фоны, графика и рамки" width="100%">
<img src="docs/screenshots/02-colors-5.png" alt="Цвет: слои" width="100%">

</details>

## 🔤 Типографика

Шрифт **Onest 2.0** (вариативный, лицензия OFL), лежит в `fonts/`. Размеры и начертания подключаются классами `ozi-body-*`, `ozi-heading-*`.

<img src="docs/screenshots/03-type-1.png" alt="Типографика" width="100%">
<img src="docs/screenshots/03-type-2.png" alt="Типографика, продолжение" width="100%">

## 📐 Сетка, отступы, радиусы, тени

<img src="docs/screenshots/04-foundation.png" alt="Сетка, отступы, радиусы, тени" width="100%">

## 🧩 Иконки

Спрайт `icons/icons.svg` — 34 символа: 24 сняты с оригинала и 10 нарисованы вручную (`ui-calendar`, `ui-close`, `ui-eye`, `ui-eye-off`, `ui-error`, `ui-warning`, `ui-info`, `ui-check`, `ui-print`, `ui-package`). Цвет иконки — `currentColor`.

<img src="docs/screenshots/05-icons.png" alt="Иконки" width="100%">

## 🏗 Каркас: шапка, меню, страница

<img src="docs/screenshots/06-shell.png" alt="Каркас: шапка, меню, страница" width="100%">

---

## 🧱 Компоненты

25 CSS-файлов в `components/ozon/`. Каждый компонент — отдельный файл, подключайте только нужные. Классы выгружены из оригинала и переименованы `ozi__X__y__HASH` → `po-X__y`.

| Группа | Файл |
|---|---|
| Кнопки | `button.css`, `icon-button.css` |
| Поля ввода и селекты | `input.css` |
| Выпадающий список | `../dropdown.css` |
| Чекбокс, радио, переключатель | `../checkbox.css`, `../radio.css`, `toggle.css` |
| Табы и чипы | `tabs.css`, `filter-chip.css` |
| Бейджи и счётчики | `badge.css`, `counter.css` |
| Информер | `informer.css` |
| Таблица | `table.css`, `data-cell.css` |
| Календарь | `../calendar.css` |
| Подсказка, поповер | `tooltip.css`, `popover.css` |
| Боковая панель, диалог | `drawer.css`, `window.css`, `dialog.css` |
| Скелетон | `skeleton.css` |
| Прочее | `avatar.css`, `link.css`, `menu-item.css`, `scroller.css`, `separator.css`, `text.css`, `truncate.css`, `typography.css` |

<img src="docs/screenshots/07-components-1.png" alt="Компоненты: кнопки, поля" width="100%">

<details open>
<summary><b>Списки, чекбоксы, табы, бейджи, информеры</b></summary>
<br>

<img src="docs/screenshots/07-components-2.png" alt="Компоненты: список, чекбоксы, табы, бейджи, информеры" width="100%">

</details>

<details>
<summary><b>Таблица, календарь, подсказка, панель, диалог, скелетон</b></summary>
<br>

<img src="docs/screenshots/07-components-3.png" alt="Компоненты: таблица, календарь" width="100%">
<img src="docs/screenshots/07-components-4.png" alt="Компоненты: подсказка, боковая панель" width="100%">
<img src="docs/screenshots/07-components-5.png" alt="Компоненты: диалог, скелетон" width="100%">

</details>

## 🗂 Шаблоны страниц

Любой раздел PartnerOffice собирается из этих шаблонов, поэтому экраны остаются одинаковыми: плитки-хаб, поиск по штрихкоду, страница с таблицей, список с панелью фильтров, дашборд, новость, список-карточки, пустые состояния.

<img src="docs/screenshots/08-patterns-1.png" alt="Шаблоны: плитки-хаб, поиск, страница с таблицей" width="100%">

<details>
<summary><b>Остальные шаблоны</b></summary>
<br>

<img src="docs/screenshots/08-patterns-2.png" alt="Шаблоны: список с фильтрами, дашборд" width="100%">
<img src="docs/screenshots/08-patterns-3.png" alt="Шаблоны: новость, карточки, пустые состояния" width="100%">

</details>

## 📜 Правила и ограничения

<img src="docs/screenshots/09-rules.png" alt="Правила и ограничения" width="100%">

---

## 🔌 Подключение

Порядок важен: сначала токены, потом база, потом нужные компоненты и каркас.

```html
<link rel="stylesheet" href="tokens/ozon-tokens.css">
<link rel="stylesheet" href="components/base.css">           <!-- шрифт Onest, сброс -->
<link rel="stylesheet" href="components/ozon/button.css">    <!-- нужные компоненты -->
<link rel="stylesheet" href="components/layout.css">         <!-- шапка, меню, страница -->
```

```html
<!-- иконка из спрайта -->
<svg width="24" height="24"><use href="#nav-claims"/></svg>

<!-- тёмная тема -->
<div class="theme-dark"> … </div>
```

- **Классы:** `po-имя__элемент` (BEM, как в оригинале), типографика `ozi-body-500`, `ozi-heading-400`.
- **Тема:** светлая по умолчанию (`:root`), тёмная — `.theme-dark` на контейнере.
- **Иконки:** спрайт `icons/icons.svg`, цвет — `currentColor`.
- **Живой пример подключения:** [`components/demo.html`](components/demo.html).

## 📁 Структура репозитория

| Путь | Что внутри |
|---|---|
| [`brandbook/`](brandbook) | Готовый брендбук `index.html`: цвет, типографика, сетка, иконки, каркас, 14 групп компонентов, шаблоны страниц, правила |
| [`tokens/`](tokens) | `ozon-tokens.css` и `.json`: 316 переменных `:root`, по 173 для светлой и тёмной темы (`.theme-dark`) |
| [`components/`](components) | `base.css` (шрифт, сброс), `layout.css` (шапка, меню, страница, плитки, карточки), `dropdown.css`, `checkbox.css`, `radio.css`, `calendar.css`, `demo.html` |
| [`components/ozon/`](components/ozon) | 25 файлов компонентов, выгруженных из оригинала |
| [`components/ozon/_full-reference/`](components/ozon/_full-reference) | Полные выгрузки списка, календаря и чекбокса из оригинала для сверки |
| [`fonts/`](fonts) | Onest 2.0 (вариативный, OFL) |
| [`icons/`](icons) | `icons.svg`, спрайт из 34 символов |
| [`build/`](build) | `build_brandbook.py`, генератор брендбука из токенов, иконок и компонентов |
| [`docs/`](docs) | Скриншоты страницы брендбука для этого README |
| [`RESEARCH.md`](RESEARCH.md) | Подробная сводка исследования дизайн-системы |

## ⚠️ Что заменить своим перед запуском

Логотип (в брендбуке заглушка «PO»), название «Турбо ПВЗ», 3D-иллюстрации и рекламные баннеры Ozon не переносились. Иконка-логотип Ozon оставлена в `icons.svg` как `logo-circle` только для справки, выводить её в интерфейс нельзя.

## Правки к выгрузке оригинала

- `components/ozon/input.css`: селектор `.po-textarea__placeholder:focus::placeholder:not(...)` переписан в `:focus:not(...)::placeholder`. Значение то же, но прежний вид не принимает минификатор lightningcss при сборке фронтенда.

## Известные ограничения

- Тёмная тема: токены есть, страницы в ней не проверялись.
- Не снято: формы действий (выдача, приём), сообщения об ошибках при отправке, toast-уведомления, выбор месяца и года в календаре.
- Мобильные ширины (<900px) сверены только по media-запросам CSS.
- Информер использует свой значок «i» вместо картинки Ozon; плитки-хаб — иконки-заглушки вместо 3D-иллюстраций.

## Источник и права

Визуальный язык снят с интерфейса «Турбо ПВЗ» (дизайн-система *ozi*, версия 3.11.59, снято 2026-10-12). Скриншоты оригинала и его исходные CSS в репозиторий не входят: на них реальные данные ПВЗ, а код принадлежит Ozon. Шрифт Onest распространяется по лицензии SIL OFL.
