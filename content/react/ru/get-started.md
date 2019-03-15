---
title: "Начало работы"
tocTitle: "Начало работы"
description: "Настройка React Storybook в вашем окружении разработки"
commit: ebe2ae2
---

# Начало работы

Storybook запускается и работает рядом с вашим приложением в development режиме. Он помогает вам разрабатывать компоненты пользовательского интерфейса (UI) изолированно от бизнес-логики и контекста вашего приложения. Эта ваерсия Learn Storybook (Изучаем Storybook) для библиотеки React, также существуют версии для [Vue](/vue/en/get-started) и [Angular](/angular/en/getstarted).

![Storybook и наше приложение](/storybook-relationship.jpg)

## Устанавливаем React Storybook

Необходимо выполнить всего несколько шагов, чтобы настроить процесс сборки в вашем окружении. Чтобы начать, мы будем использовать [Create React App](https://github.com/facebook/create-react-app) (CRA) для установки системы сборки, а также подключим [Storybook](https://storybook.js.org/) и [Jest](https://facebook.github.io/jest/) тестирование в созданном нами приложении. Давайте запустим следующие команды:

```bash
# Создаем наше приложение:
npx create-react-app taskbox
cd taskbox

# Добавляем Storybook:
npx -p @storybook/cli sb init
```

Мы можем быстро проверить, что различные окружения в нашем приложении работают правильно:

```bash
# Запускаем тесты (Jest) в терминале:
yarn test

# Запускаем наш проводник компонентов на порту 9009:
yarn run storybook

# Запускаем само приложение на порту 3000:
yarn start
```

<div class="aside">
  ПРИМЕЧАНИЕ: Если команда <code>yarn test</code> выкинет ошибку, вам нужно установить <code>watchman</code> как советуют <a href="https://github.com/facebook/create-react-app/issues/871#issuecomment-252297884">вот здесь</a>.
</div>

У нашего приложения 3 режима: автоматизированные тесты (Jest), разработка компонентов (Storybook), и само наше приложение.

![3 режима](/app-three-modalities.png)

В зависимости от того, над какой частью приложения вы работаете, вы можете использовать один или несколько режимом одновременно. Поскольку в данный момент наша цель - создать один UI компонент, мы будем запускать только Storybook.

## Переиспользование CSS

Наше приложение Taskbox переиспользует дизайн-элементы [приложения](https://blog.hichroma.com/graphql-react-tutorial-part-1-6-d0691af25858), которое мы делали в курсе GraphQL и React Tutorial, поэтому мы не будем писать CSS код в нашем курсе. Мы просто скомпилируем LESS в один CSS файл и подключим его в наш проект. Скопируйте и вставьте [этот скопилированный CSS](https://github.com/hichroma/learnstorybook-code/blob/master/src/index.css) в файл src/index.css в соответствии с руководством CRA (Create React App)

![Taskbox UI](/ss-browserchrome-taskbox-learnstorybook.png)

<div class="aside">
Если вы хотите изменить стили, исходники LESS файлов представлены в Github репозитории.
</div>

## Добавляем ресурсы

Нам также необходимо добавить [папки](https://github.com/hichroma/learnstorybook-code/tree/master/public) со шрифтами и иконками в папку `public/`. После добавления стилей и ресурсов приложение будет отображаться несколько странно. Это нормально. Мы не будем работать над самим приложением прямо сейчас, а начнем с оздания нашего первого компонента!
