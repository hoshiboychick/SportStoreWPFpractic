# Подготовка инфраструктуры проекта в Visual Studio 2022

Рассмотрим текущее положение архитектуры приложения в обозревателе решений

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image59.png]]


## Установка ```Nuget-package```

Для начала нам потребуется установить дополнительные Nuget-package для работы с ```Entity Framework```

- Microsoft.EntityFrameworkCore
- Microsoft.EntityFrameworkCore.Design
- Microsoft.EntityFrameworkCore.SqlServer
- Microsoft.EntityFrameworkCore.Tools

Управление пакетами ```Nuget``` в Visual Studio

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image60.png]]

Установка ```Entity Framework Core```

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image61.png]]
[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image62.png]]
[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image63.png]]

В зависимостях проекта можно посмотреть установленные пакеты

Установите самостоятельно остальные 3 пакета

**Коммит**: установка ```Nuget-package```

## Настройка папки для хранения ресурсов приложения

Создайте в проекте папку ```Resources```,в которую поместите файл логотипа и иконки для приложения (см. общие ресурсы)

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image65.png]]

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image66.png]]

В свойствах каждого файла в пункте 

```Действия при сборке``` отметить ```Ресурс```

```Копировать в выходной каталоге``` отметить ```Копировать более новую версию```


[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image67.png]]

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image68.png]]

## ```App.config```

Создайте новый элемент

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image69.png]]

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image70.png]]

## Определение строки подключения в конфиге

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image71.png]]



## Папка ```Infrastructure``` для классов-помощников

Создайте папку ```Infrastructure``` в проекте

## Восстановление классов сущностей из базы данных с помощью Scaffold

**Замечание**: надо установить ```Microsoft.EntityFrameworkCore.Tools```.

В консоле диспетчера пакетов Nuget прописать команду:

```Scaffold-DbContext "Server=(localdb)\mssqllocaldb;Database=SportStore;Trusted_Connection=True;" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Models```

Команда создает модели из каждой сущности в базе данных, учитывая связи, а также создает класс контекста для работы с данными как с классами.

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image72.png]]

Успешное восстановление. Обратите внимание, до выполнения команды не должно быть ошибок при сборке проекта

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image73.png]]

В папке ```Models``` в файле ```SportStoreContex.cs``` в методе ```OnConfiguring``` замените строку подключения на:

```Csharp
optionsBuilder.UseSqlServer(ConfigurationManager.ConnectionStrings["ConnectionLocalDb"].ToString());
```
Это надо для того, чтобы данные подключения не были видные в классе, а подключались из файла ```App.config``` в целях безопасности.

В итоге архитектура проекта

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image74.png]]

## Проверка подключения к базе данных

В файле ```MainWindow.cs``` в конструкторе класса ```MainWindow``` вызовем объект класса ```SportStoreContext```, для чего надо будет подключить пространство имен из папки ```Models```:  ```using SportStore.Models```. Потом найдем первого пользователя в таблице ```User```.

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image75.png]]

Успешное подключение к базе данных

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image76.png]]

**Коммит**: подключение к базе данных

## Работа c ```git``` из Visual Studio

Сделать коммит из Visual Studio => Зафиксировать

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image77.png]]
[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image78.png]]
[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image79.png]]
[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image80.png]]

Внешний вид обозревателя решений при подключении системы контроля версий ```git```

[[https://github.com/artemovsergey/SportStoreWPFpractica/raw/master/images/image81.png]]


