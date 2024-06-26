---
title: "`<noindex>`"
description: "Запрещает поисковым системам индексировать содержимое сайтов."
authors:
  - rrramble
related:
  - html/a
  - html/meta
  - html/seo-for-beginners
tags:
  - doka
---

## Кратко

Тег `<noindex>` запрещает поисковым системам индексировать содержимое. Этот тег поддерживает только поисковик [Яндекс](https://yandex.ru/support/webmaster/adding-site/indexing-prohibition.html#indexing-prohibition__content).

## Пример

```html
<noindex>
  <!-- Рекламный текст другой компании -->
  <article>Реклама наших партнёров:...</article>

  <!-- Служебная ссылка -->
  <a href="/login">Вход во внутренний портал для работников компании</a>
</noindex>
```

## Как пишется

Этого тега нет в спецификации HTML, поэтому [HTML-валидатор](https://validator.w3.org) покажет ошибку. Чтобы избежать проблем с валидацией, Яндекс предлагает такие варианты:

- использовать синтаксис [`<!‐‐noindex‐‐><!‐‐/noindex‐‐>`](https://yandex.ru/support/webmaster/adding-site/indexing-prohibition.html#indexing-prohibition__content);
- использовать [тег `<noscript>`](/html/noscript).

Примеры:

```html
<!‐‐noindex‐‐>
  <!-- Рекламный текст другой компании -->
  <article>Реклама наших партнёров:...</article>

  <!-- Служебная ссылка -->
  <a href="/login">Вход во внутренний портал для работников компании</a>
<!‐‐/noindex‐‐>

<noscript>Текст, индексирование которого нужно запретить.</noscript>
```

### Другие способы запретить поисковикам индексирование

- Запретить индексирование разделов сайта и страниц: поместите в корневую папку сайта файл [_robots.txt_](https://developers.google.com/search/docs/crawling-indexing/robots/create-robots-txt?hl=ru).
- Запретить индексирование всей страницы: укажите тег `<meta name="robots" content="noindex">` в секции [`<head>`](/html/head/).
- Запретить переходить по ссылке: у тега [`<a>`](/html/a/) укажите [атрибут `rel="nofollow"`](https://developers.google.com/search/docs/crawling-indexing/qualify-outbound-links?hl=ru).

## Как понять

Поисковые системы сканируют (индексируют) содержимое сайтов в интернете. Когда пользователь ищет информацию, поисковики выдают ответ на основе ранее отсканированного.

Не всё содержимое имеет смысл индексировать:

- сторонняя реклама от партнёров сайта — если реклама не связана с сайтом;
- ссылки, которые публикуют пользователи форумов – если сайт не хочет отвечать за некорректные ссылки;
- служебная информация для своих работников.
