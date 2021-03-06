---
title: Объявления
---

Svelte автоматически обновляет DOM при изменении состояния вашего компонента. При этом иногда некоторые части состояния компонента должны быть вычислены из *других* частей и пересчитаны всякий раз, когда эти части изменяются. Например, переменная `fullname` может быть получена из `firstname` и `lastname`.

Для этого у нас есть *реактивные объявления*. Они выглядят так:

```js
let count = 0;
$: doubled = count * 2;
```

> Не волнуйтесь, если код выглядит для вас странно. Это [валидный](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/label) (хоть и необычный) JavaScript, который Svelte понимает как 'повторить вычисление выражения, как только изменится любое значение внутри него'. Просто начните использовать эту возможность и вы быстро привыкнете.

Давайте поместим `doubled` в нашу разметку:

```html
<p>Удвоим {count} и получим {doubled}</p>
```

Конечно, вы можете просто написать `{count * 2}` в разметке - но это всего лишь очень простой случай. Реактивные объявления становятся гораздо полезнее, когда нужно ссылаться на них несколько раз, или у вас есть значения, которые зависят от *других* реактивных значений.
