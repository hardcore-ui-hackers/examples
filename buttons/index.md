# Кнопки

## 3D с ховером и нажатием
Взято с акции «[Съедобное-несъедобное](https://fuuud.project.tinkoff.ru/)» у Тинькова. Интересное — цвет тени задается через `currentColor`:

<buttons-ButtonTinkoffEda/>

<<< @/.vuepress/components/buttons/ButtonTinkoffEda.vue


## 3D с ховером и нажатием (2)
Свойство `transition-timing-function` задаётся с помощью функции `cubic-bezier()`. Это кубическая кривая Безье, которая строится по четырем точкам и задаёт параметры ускорения анимации.

<buttons-Button3DFlipping/>

<<< @/.vuepress/components/buttons/Button3DFlipping.vue

## Пузырики при нажатии
Каждый пузырик задаётся отдельным `background-image: radial-gradient(...)`. При анимации добавляется класс с `keyframe`, в котором изменяется положение каждого пузырика через `background-position`.

<buttons-ButtonBubble/>

<<< @/.vuepress/components/buttons/ButtonBubble.vue
