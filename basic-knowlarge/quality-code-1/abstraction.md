# Abstraction

Например, есть код

```text
const element = document.createElement(‘button’);
element.id = 'id_button';
element.classList = ‘red’;
document.body.appendChild(element);
element.click();
```

Можно добавить в код кнопки функцию, обернуть, и использовать при создании кнопки функцию `createButton`:

```text
const.button = createButton('id_button');
button.click();

function createButton((id') {
    element = document.createElement(‘button’);
    element.id = id;
    element.classList = ‘red’;
    document.body.appendChild(element);

    return element;
}
```

По «говорящему» названию понятно, что функция делает и что передается id. Если мы хотим сделать кнопку и не разбираться, как она создается и зачем, — мы пишем код, используя эту функцию.

```text
button.component.js

let button = createButton('id_button');
button.click();
```

Дальше пишем **helper**, который позже используют другие разработчики. Если они пожелают понять, как жарится яичница или захотят изменить рецепт — добавить или убрать соль, то зайдут и почитают.

```text
button.helpers.js
function createButton(id) {
    let button = document.createElement('button');
    button.id = id;
    button.classList = 'red’;
    document.body.appendChild(element);

    return button;
}
```

