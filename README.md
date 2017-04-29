# Уровни сложности чтения

* Я слишком молод, чтобы думать
  * [Введение и правила игры](https://github.com/Skybladev2/DobbleMathModel/blob/master/README.md#%D0%92%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%B8%D0%B3%D1%80%D1%8B)
  * [Как они это делают?](https://github.com/Skybladev2/DobbleMathModel/blob/master/README.md#%D0%9A%D0%B0%D0%BA-%D0%BE%D0%BD%D0%B8-%D1%8D%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D1%8E%D1%82)
  * Матрица инцидентности для игры Доббль
  * Каких двух карточек не хватает в комплекте игры?
  * Благодарности

* Сделай мне умно
  * [Введение и правила игры](https://github.com/Skybladev2/DobbleMathModel/blob/master/README.md#%D0%92%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%B8%D0%B3%D1%80%D1%8B)
  * [Как они это делают?](https://github.com/Skybladev2/DobbleMathModel/blob/master/README.md#%D0%9A%D0%B0%D0%BA-%D0%BE%D0%BD%D0%B8-%D1%8D%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D1%8E%D1%82)
  * При чём тут карточки?
  * Проективные плоскости малых порядков
  * Матрица инцидентности для игры Доббль
  * Каких двух карточек не хватает в комплекте игры?
  * Благодарности

* Кошмар
  * [Введение и правила игры](https://github.com/Skybladev2/DobbleMathModel/blob/master/README.md#%D0%92%D0%B2%D0%B5%D0%B4%D0%B5%D0%BD%D0%B8%D0%B5-%D0%B8-%D0%BF%D1%80%D0%B0%D0%B2%D0%B8%D0%BB%D0%B0-%D0%B8%D0%B3%D1%80%D1%8B)
  * [Как они это делают?](https://github.com/Skybladev2/DobbleMathModel/blob/master/README.md#%D0%9A%D0%B0%D0%BA-%D0%BE%D0%BD%D0%B8-%D1%8D%D1%82%D0%BE-%D0%B4%D0%B5%D0%BB%D0%B0%D1%8E%D1%82)
  * Конечная геометрия для грудничков
  * При чём тут карточки?
  * Проективные плоскости малых порядков
  * Как построить проективную плоскость?
  * Матрица инцидентности для игры Доббль
  * Каких двух карточек не хватает в комплекте игры?
  * Благодарности

# Введение и правила игры

Несколько лет назад я купил игру [Доббль](http://www.igroved.ru/games/dobble/) ([Dobble](https://boardgamegeek.com/boardgame/63268/spot-it), оригинальное название “Spot It!”). Это очень простая, быстрая и весёлая игра, которую я считаю одной из лучших настольных игр вообще.
В комплекте игры 55 карточек с 8 разными символами на каждой. Вот как выглядят эти карточки:


![Card 1](https://github.com/Skybladev2/DobbleMathModel/blob/master/images/Dobble1.png) ![Card 2](https://github.com/Skybladev2/DobbleMathModel/blob/master/images/Dobble2.png)

_Рис. 1._ Пример карточек игры.

На каждых двух карточках совпадает один и только один символ. На приведённом рисунке это символ карандаша:

![Card 1 symbol 1-2](https://github.com/Skybladev2/DobbleMathModel/blob/master/images/Dobble1_symbol1-2.png) ![Card 2 symbol 1-2](https://github.com/Skybladev2/DobbleMathModel/blob/master/images/Dobble2_symbol1-2.png)

_Рис. 2._ Совпадающие символы на карточках

Игрок, первый увидевший совпадение, делает с одной из карточек действие, зависящее от тура игры. Например, забирает её себе или подкидывает сопернику.
Часто это приводит к тому, что одна из карточек, для которой игроки ищут совпадения, меняется. Из-за этого приходится искать новое совпадение, которое может быть совсем другим символом:

![Card 3](https://github.com/Skybladev2/DobbleMathModel/blob/master/images/Dobble3.png) ![Card 2](https://github.com/Skybladev2/DobbleMathModel/blob/master/images/Dobble2.png) 

![Card 3 symbol2-3](https://github.com/Skybladev2/DobbleMathModel/blob/master/images/Dobble3_symbol2-3.png) ![Card 2 symbol2-3](https://github.com/Skybladev2/DobbleMathModel/blob/master/images/Dobble2_symbol2-3.png)

_Рис. 3, 4._ Первая карточка заменяется на новую. Теперь между ними новое совпадение - символ клоуна.

# Как они это делают?

На первый взгляд, кажется невероятным, что на двух карточках ровно одно совпадение, ни больше, ни меньше. Сразу возникают вопросы - сколько всего символов в игре? Их не может быть слишком много (тогда на карточках будет больше одного совпадения) или слишком мало (тогда на карточках может вообще не оказаться совпадений).
Кроме того, очевидно, что символы расположены на карточках в особом порядке, который гарантирует единственное совпадение для любых двух карточек.

Элементарные навыки гугл-фу приводят нас на сайт stackoverflow, где описано, почему так происходит: http://stackoverflow.com/questions/6240113/what-are-the-mathematical-computational-principles-behind-this-game

В игре используются принципы [конечной геометрии](https://ru.wikipedia.org/wiki/%D0%9A%D0%BE%D0%BD%D0%B5%D1%87%D0%BD%D0%B0%D1%8F_%D0%B3%D0%B5%D0%BE%D0%BC%D0%B5%D1%82%D1%80%D0%B8%D1%8F). Хотя в этом словосочетании есть слово “геометрия”, это понятие относится больше к комбинаторике, чем к геометрии. Она оперирует конечным количеством точек, которые могут располагаться, в частности, в виде [проективной плоскости](https://ru.wikipedia.org/wiki/%D0%9F%D1%80%D0%BE%D0%B5%D0%BA%D1%82%D0%B8%D0%B2%D0%BD%D0%B0%D1%8F_%D0%BF%D0%BB%D0%BE%D1%81%D0%BA%D0%BE%D1%81%D1%82%D1%8C).

Карточки и символы в игре являются элементами проективной плоскости 7 порядка. Это значит, что на каждой карточке __n+1__ символ, а общее количество уникальных символов в игре - __n^2+n+1__, т.е. 57 символов.

© 2017 Skyblade
