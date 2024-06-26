---
title: "`aria-description`"
description: "Добавляем к элементу описание, которое видят только вспомогательные технологии."
authors:
  - tatianafokina
contributors:
  - skorobaeus
related:
  - a11y/aria-attrs
  - a11y/aria-label
  - a11y/aria-describedby
tags:
  - doka
---

## Кратко

[Глобальное свойство](/a11y/aria-attrs/#globalnye-atributy) из [WAI-ARIA](/a11y/aria-intro/#specifikaciya) для дополнительного описания элементов, которое видят только вспомогательные технологии.

<aside>

👶 `aria-description` — новое свойство из [черновика WAI-ARIA 1.3](https://w3c.github.io/aria/). Пока [его поддержка](https://a11ysupport.io/tech/aria/aria-description_attribute) не стала стабильной, лучше использовать другие способы описания элементов.

</aside>

## Пример

```html
<button aria-description="Открыть модальное окно">
  Настройки
</button>
```

<iframe title="Кнопка с визуально скрытым описанием" src="demos/button-with-description/" height="190"></iframe>

[Скринридер](/a11y/screenreaders/) сделает примерно такое объявление: «Настройки, кнопка. Открыть модальное окно».

## Как пишется

Задайте тегу атрибут `aria-description` с нужным текстом. Атрибут можно использовать для всех тегов и ARIA-ролей.

Старайтесь использовать `aria-description` только в случаях, когда нет возможности добавить видимое описание к элементу. Например, подсказки к полям нужны всем пользователям, так что лучше использовать для подсказок другой атрибут [`aria-describedby`](/a11y/aria-describedby/).

Если зададите одному элементу одновременно `aria-description` и `aria-describedby`, скринридер прочитает описание только из `aria-describedby`.

## Как понять

Атрибут добавляет дополнительное описание, которое нельзя добавить в _имя элемента_. Это краткое название элемента, которое озвучивает скринридер при фокусе или последовательном зачитывании содержимого. Скринридер прочтёт дополнительное описание после имени элемента и другой основной информации о нём.

## Подсказки

💡 `aria-description` чем-то похож на атрибут [`title`](/html/global-attrs/#title), хотя его содержимое не всплывает при наведении на элемент.

💡 Содержимое `aria-description` пока не переводится сервисами для автоматического перевода.

💡 Не забывайте переводить содержимое атрибута, когда поддерживаете несколько языков.
