В исходных файлах для импорта проверьте соответствие таблицам в базе данных. Все поля и последовательность полей в таблицах базы данных на сервере должны быть отражены в исходных данных. При необходимости отредактируйте исходные данные (добавление или удаление столбцов, редактирование данных в столбцах, перестановка столбцов, добавление столбцов для поля ```id```).

## Таблица ```User```

Данные для таблицы User


![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image21.png)

Таблица ```User``` в базе данных

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image22.png)

Требуется разбить ФИО на три поля, а также в качестве ролей вместо строковых значений поставить значения связанной таблицы ```Role``` в виде внешних ключей числового типа.

Вставка ```Id```

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image23.png)

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image24.png)

Разбиения данных на столбцы

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image25.png)
![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image26.png)
![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image27.png)
![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image28.png)


## Таблица ```Role```

Таблица ролей

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image29.png)

Отредактированные данные для таблицы ```User```

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image30.png)

Перемещение столбца

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image31.png)

Готовая таблица ```User``` в базе данных

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image32.png)


## Таблица ```Order```

Данные для таблицы ```Order``

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image33.png)


Таблица ```Order``` в базе данных

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image34.png)

Очевидно, что в базу данных надо добавить дополнительные столбцы

Открытие конструктора таблицы

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image35.png)

Добавление новых столбцов в таблицу ```Users```

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image36.png)

Применение обновления

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image37.png)

Процесс обновления

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image38.png)

Успешное завершение обновления

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image39.png)

Таблица ```Order``` c данными

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image40.png)


## Таблица ```PickupPoint```

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image41.png)

Разделение по столбцам

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image42.png)

Создание таблицы ```PickupPoint```

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image43.png)

Данные для таблицы ```PickupPoint```

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image44.png)

Таблица ```PickupPoint``` с данными

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image45.png)

Добавление внешнего ключа в таблице ```Order``` к таблице ```PickupPoints```

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image46.png)


## Таблица ```Products```

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image47.png)

Исходное положение столбцов в таблице ```Products``` в базе данных

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image48.png)

Обновление таблицы продукты 

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image49.png)

Отредактированные данные для таблицы ```Product```

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image50.png)

Таблица ```Product``` c данными

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image51.png)


Создание скрипта базы данных ```SportStore``` c данными

![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image52.png)
![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image53.png)
![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image54.png)
![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image55.png)
![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image56.png)
![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image57.png)
![](https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image58.png)