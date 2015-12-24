# Установка и конфигурация

### Установка
Сохраните скрипт sipuni-calltracking.min.js и подключите его на странице.
```
<script src='/js/sipuni-calltracking.min.js'></script>
```

### Пример использования
Предположим, у нас на сайте отображатся два номера телефона, и нам нужно отследить трафик с Яндекс Директ и двух сайтов: habrahabr.ru и oborot.ru

В HTML добавляем CSS класс ct_phone в элемент, где будет происходить подмена номеров:
```
    <div>Телефон: <span class="ct_phone">+7 888 888-88-88</span></div>
```    

Настраиваем вызов скрипта подмены. 
 * В поле sources задаем правила определения источников трафика. 
 * В поле phones задаем названия источников трафика, и соответсвующие им номера телефонов. 

Вызов этого скрипта должен происходить после HTML элементов содержащих номера телефонов, или в событии готовности DOM модели.
```
<script>
    sipuniCalltracking({
      sources: {
        'ydirect':{'utm_source': 'direct.yandex.ru'},
        'articles':{'ref':/(habrahabr|oborot\.ru)/ig}
      },
      phones: [
        {'src':'articles', 'phone':['+75555555555']},
        {'src':'ydirect', 'phone':['+73333333333']}
      ]
    });
</script>
```

 * [Оглавление](index.md)
 * [Настройка источников трафика](sources.md)
 * [Отображение нескольких телефонов](many-numbers.md)
 * [Подмена конента страницы](subst-content.md)


[![](doc/img/sipuni_logo.png)](http://calltracking.sipuni.com)
 