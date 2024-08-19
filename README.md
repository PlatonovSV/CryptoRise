CryptoRise App
==================

## Стек приложения
- Kotlin
- Single Activity
- Jetpack Compose
- Retrofit
- Kotlinx Serialization
- Coroutines
- Hilt
- Coil

## Декомпозиция 
Перед началом работы (19.08.2024) я принял решение декомпозировать процесс разработки и оценить сроки выполнения задач. 

Приблизительная структура будущего проекта:<br>

Модуль cryptolist - список популярных криптовалют;<br>
*navigation*<br>
&emsp;`CryptoListNavigation`<br>
`CryptoListViewModel`<br>
`CryptoListScreen`<br>
`CryptoListUiState`<br>

Модуль aboutcurrency - подробная информация о выбранной криптовалюте;<br>
*navigation*<br>
&emsp;`AboutCurrencyNavigation`<br>
`AboutCurrencyScreen`<br>
`AboutCurrencyViewModel`<br>
`AboutCurrencyUiState`<br>

Модуль app - entry point приложения;<br>
*navigation*<br>
&emsp;`CryptoRiseNavHost` - навигация между экранами приложения;<br>
*ui* <br>
&emsp;*theme* - классы, связанные с Material Design 3 темой приложения;<br>
`CryptoRiseApp`<br>
`CryptoRiseApplication`<br>
`MainActivity`<br>

Модуль core<br>
&emsp;Модуль network - отвечает за выполнение всех операций, связанных с сетью;<br>
&emsp;Модуль model - содержит классы, представляющие основные сущности;<br>
&emsp;Модуль data - обеспечивает уровень абстракции для доступа и управления данными независимо от источника.<br>
###  Календарный план проекта

20.08.2024
***
1. Добавить классы Material Design 3 для темы приложения;
2. Создать класс `CryptoRiseApplication` и, с использованием Hilt, внедрить свойство ImageLoader — для работы Coil;
3. Создать модуль cryptolist, включая `CryptoListNavigation`, `CryptoListScreen`, `CryptoListViewModel`;
4. Создать CryptoListUiState (3 реализации sealed интерфейса);
5. Добавить `CryptoRiseNavHost` с указанием startDestination — ABOUT_CURRENCY_ROUTE;
6. Создать репозиторий для получения списка криптовалют;
7. Используя Hilt, внедрить репозиторий в конструктор CryptoListViewModel;
8. Получение `CryptoListViewModel` данных о выбранной криптовалюте из репозитория;
9. Вывод информации о криптовалютах на экране CryptoList;

21.08.2024
***
1. Создать модуль aboutcurrency, включая `AboutCurrencyNavigation`, `AboutCurrencyScreen`, `AboutCurrencyViewModel`;
2. Создать `AboutCurrencyUiState` (3 реализации sealed интерфейса);
3. Реализовать навигацию от CryptoList к AboutCurrency с передачей id выбранной криптовалюты;
4. В AboutCurrency реализовать навигацию вверх при нажатии соответствующей кнопки;
5. Создать репозиторий для получения подробной информации о криптовалюте;
6. Используя Hilt, внедрить репозиторий в констуктор `AboutCurrencyViewModel`;

22.08.2024
***
1. Получение `AboutCurrencyViewModel` данных о выбранной криптовалюте из репозитория;
2. Привести экран AboutCurrency в соответствие макету;
3. Привести экран CryptoList в соответствие макету;

23.08.2024
***
1. Реализовать функционал Pull to Refresh для экрана CryptoList;
2. Добавить иконку приложения.

