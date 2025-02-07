---
title: "Атрибут `placeholder`"
description: "Удобный атрибут для подсказки в поле ввода. Но есть нюансы!"
authors:
  - minich
keywords:
  - плейсхолдер
related:
  - html/input
  - css/placeholder
  - html/label
tags:
  - doka
---

## Кратко

Атрибут, который подсказывает пользователю, что именно нужно ввести в поле ввода (обычно это пример слова или фразы). Выглядит это как будто поле уже заполнено, только гораздо бледнее. А ещё значение атрибута исчезает, как только пользователь начинает вводить текст.

## Пример

```html
<input type="text" id="name" placeholder="Введите ваше имя">
```

<iframe title="Подсказка в поле ввода" src="demos/example/" height="180"></iframe>

## Как пишется

Атрибут `placeholder` можно задать для [`<input>`](/html/input/) и [`<textarea>`](/html/textarea/). Атрибут работает со следующими типами:

- `text`;
- `search`;
- `url`;
- `telephone`;
- `email`;
- `password`.

```html
<input type="email" id="email" placeholder="your_email@gmail.com">
```

Внешний вид можно стилизовать при помощи псевдоэлемента [`::placeholder`](/css/placeholder/).

Для браузеров старых версий нужны [вендорные префиксы](/css/vendor-prefixes/):

```css
input::-webkit-input-placeholder {
  color: #F0BBD7;
}

input:-moz-placeholder {
  color: #F0BBD7;
}

input::-moz-placeholder {
  color: #F0BBD7;
}

input:-ms-input-placeholder {
  color: #F0BBD7;
}

input::-ms-input-placeholder {
  color: #F0BBD7;
}
```

## Как понять

Текст плейсхолдера должен быть краткой подсказкой о том, что пользователь должен ввести в поле ввода.

Если для заполнения поля нужна инструкция (формате номера телефона или длина пароля), то такую инструкцию лучше оформить отдельно от поля ввода. Иначе пользователь не сможет эффективно её использовать, потому что заполнители исчезают во время набора текста.

```html
<label for="password">Пароль</label>
<input type="text" id="password" placeholder="Введите пароль" aria-describedby="hint">
<span id="hint">Пароль должен состоять из 8 символов, включая цифры и буквы.</span>
```

В этом примере инструкция к паролю всегда доступна пользователю и точно не потеряется.

## Контрастность

Цвет заполнителя в поле формы по умолчанию светло-серый, это может создавать дополнительную нагрузку для пользователей с нарушениями зрения.

Цветовой контраст между фоном и самим текстом должен быть достаточным, чтобы пользователи с нарушениями зрения могли его прочитать:

- текст и его фон должны иметь контрастность не менее _4.5:1_;
- текст заголовка (или просто крупный текст) должен иметь соотношение не менее _3:1_.

Подробнее о шкале контрастности можно узнать в [руководстве по доступности веб-сайтов](https://www.w3.org/WAI/WCAG21/quickref/#contrast-minimum).

## Подсказки

💡 Часто из-за дизайнерских решений `placeholder` используется для замены более семантического элемента метки. Однако это не означает, что текст-заполнитель может заменить [`<label>`](/html/label/), поскольку это создаёт неудобства для пользователей с особыми потребностями.
