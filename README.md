# Mirror App Frontend Test

Тестовое задание на Frontend разработчика

#### ВАЖНО! Перед начало работы сделайте Fork данного репозитория к себе.

## Запуск

1. Убедитесь, что вы находитесь в корневой папке.
2. Установить зависимости `npm install`.
3. Запустите клиентскую и серверную части `npm run start`
4. Проверьте, запустился ли клиентский сервер по адресу - `http://localhost:5173`.
5. Проверьте, запустилась ли серверная часть по адресу - `http://localhost:4000`
6. Если всё работает, вы молодец! Можете приступать к выполнению задания. Удачи!

## Краткое описание продукта

Наша компания (Mirror App) занимается разработкой конструктора (No Code) виджетов новостной ленты социальных сетей. Мы предоставляем пользователю интерфейс в котором он подключает аккаунт своей социальной сети (Facebook, Instagram, TikTok, etc...) и может настраивать вид своих постов (сетку раскладки, цвет заднего фона, шрифт, цвет текста и др.). После настройки пользователь/клиент может встроить настроенный виджет к себе в приложение/сайт/CMS через `<iframe />`. Наша основная задача - обеспечить корректную работу настроенного виджета в пользовательской среде, а также предоставлять пользователю широкий функционал по кастомизации. Наши планы - расширить количество сервисов с подключениями к социальным сетям и обеспечить легкую и гибкую масштабируемость.

## Описание репозитория и нефункциональные требования

Мы подготовили для Вас задание, максимально приближенное к текущему функционалу нашего приложения. Целью служит оценить Ваш подход к построению гибких (масштабируемых) интерфейсов.

Перед дальнейшим прочтением ознакомьтесь с пунктом `Запуск`.

1. Тестовое задание необходимо реализовать с использованием представленного API. В папке `/server` расположен фейковый JSON-server с заранее подготовленными данными. При запуске сервера будут генерироваться новые данные. Описание сервера Вы найдете в [README](./server/README.md).

2. В папке `/client` расположено настроенное окруженное с установленной библиотекой React. Наши приложения написаны используя архитектурный подход [FSD](fsd), поэтому в `/client` созданы папки согласно этой методологии. Какие из них использовать Вы решаете сами (Вы можете удалить ненужные, если для Вашей реализации они не нужны), важно лишь соблюдать основные концепции, принятые в [FSD](fsd).

3. На текущий момент в разработке Мы используем:

   - [Typescript](typescript).
   - Библиотеку [React 18](react).
   - Стилизация - [SCSS](scss).
   - HTTP-клиент - [Axios](axios).
   - Клиентский state-manager - [Zustand](zustand).
   - Серверный state-manager - [Tanstack Query V5](tanstack-query).

   Вы в праве использовать любой инструмент, сочетающийся с библиотекой React и её парадигмой, мы Вас не ограничиваем и приветствуем внедрение новых инструментов (если это обосновано).

4. Мы подключили [TailwindCSS](tailwind-css) для более быстрой стилизации компонентов. Если вы не работали с [TailwindCSS](tailwind-css), то можете стилизовать любым удобным для Вас способом (CSS/SCSS/CSS-in-JS). Вы также можете подключить любую библиотеку компонентов, однако, на Наш взгляд, для выполнение тестового необходимости в этом нет.

## Функциональные требования

Приложение должно состоять из одной страницы с постами, включающую в себя верхнюю панель с кнопкой обновления настроек.

**На странице постов:**

1. Отображается список постов, согласно полученным настройкам (количество колонок и рядов соответствует текущему layout). Layout могут быть разными и содержать не только columns и rows (в наших приложениях layout есть в виде слайдера или коллажа). Для упрощения выполнения тестового мы урезали до двух с одинаковыми параметрами, однако важно понимать, что они могут быть разными (визуально) и с разными параметрами.
2. В зависимости от типа навигации (в настройках) реализована пагинации или кнопка "Load More". Для пагинации вы можете воспользоваться любой общедоступной библиотекой, но будет здорово, если вы решите сделать интерфейс и функционал самостоятельно.
3. В зависимости от типа карточки (в настройках) меняется интерфейс карточки. Интерфейс карточек вы разрабатываете самостоятельно, главное требование, чтобы их можно было отличить в зависимости от типа и соблюдать семантику.
4. В карточке поста есть следующая информация:
   - Описание поста
   - Количество лайков
   - Количество комментариев
   - Дата поста (если меньше 7 дней, то выводить: "1 день назад", "2 дня назад" и т.д., если больше, вывести дату в формате день/месяц/год)
   - Информация о пользователе (имя пользователя)

**Верхняя панель:**

1. По нажатии на кнопку "Обновить настройки" интерфейс постов должен обновиться согласно новым настройкам.
2. Вывод информации о текущих настройках.

#### ВАЖНО! Приложение не должно ломаться при добавлении/удалении нового layout или template. Добавлять или удалять layout, как и template должно быть легко и с минимальным изменением текущего функционала и кодовой базы.

## Нефункциональные требования:

1. Использование [TypeScript](typescript).
2. Использование библиотеки [React 18](react).
3. В файле `/client` [README](/client/README.md) напишите какие инструменты для разработки вы использовали (описывать причину выбора не надо).

## Будет плюсом:

1. Покрытие кода unit-тестами.
2. Добавление нового типа навигации, к примеру, Infinite Scroll (бесконечная прокрутка).

#### ВАЖНО! Приложение не должно ломаться при добавлении/удалении типа навигации. Добавлять или удалять тип навигации должно быть легко и с минимальным изменением текущего функционала и кодовой базы. При выполнении п.2 из "Будем плюсом" вы можете внести изменения в серверную часть `/server`

## Возможные ошибки

Если вы столкнулись с ошибками в коде серверной части или у Вас есть вопросы по выполнению, то сообщите нам на Github в разделе `Issues`.

## А дальше?

После выполнения тестового пришлите Нам ссылку на ваш репозиторий.

[fsd]: https://feature-sliced.design/
[react]: https://react.dev/
[scss]: https://sass-lang.com/
[zustand]: https://github.com/pmndrs/zustand
[tanstack-query]: https://tanstack.com/query/latest
[axios]: https://www.npmjs.com/package/axios
[tailwind-css]: https://tailwindcss.com/
[typescript]: https://www.typescriptlang.org/
