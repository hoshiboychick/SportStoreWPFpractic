В любом текстовом редакторе (VSC, блокнот) открыть файл скрипта для SQL Server (mssql.sql)

Изначальный вид скрипта представлен в листинге 1:

**Листинг 1. Исходный скрипт базы данных mssql.sql**

```sql

create database [Trade]
go
use [Trade]
go
create table [Role]
(
	RoleID int primary key identity,
	RoleName nvarchar(100) not null
)
go
create table [User]
(
	UserID int primary key identity,
	UserSurname nvarchar(100) not null,
	UserName nvarchar(100) not null,
	UserPatronymic nvarchar(100) not null,
	UserLogin nvarchar(max) not null,
	UserPassword nvarchar(max) not null,
	UserRole int foreign key references [Role](RoleID) not null
)
go
create table [Order]
(
	OrderID int primary key identity,
	OrderStatus nvarchar(max) not null,
	OrderDeliveryDate datetime not null,
	OrderPickupPoint nvarchar(max) not null
)
go
create table Product
(
	ProductArticleNumber nvarchar(100) primary key,
	ProductName nvarchar(max) not null,
	ProductDescription nvarchar(max) not null,
	ProductCategory nvarchar(max) not null,
	ProductPhoto image not null,
	ProductManufacturer nvarchar(max) not null,
	ProductCost decimal(19,4) not null,
	ProductDiscountAmount tinyint null,
	ProductQuantityInStock int not null,
	ProductStatus nvarchar(max) not null,
)
go
create table OrderProduct
(
	OrderID int foreign key references [Order](OrderID) not null,
	ProductArticleNumber nvarchar(100) foreign key references Product(ProductArticleNumber) not null,
	Primary key (OrderID,ProductArticleNumber)
)


```

В ```листинге 1``` на языке SQL создается база данных (по умолчанию имя Trade) и таблицы ```Role```, ```User```, ```Order```, ```Product```, ```OrderProduct```. При этом таблицы ```User``` и ```Role``` связаны связью 1:М, а таблица ```OrderProduct``` является связующей таблице между таблицами ```Order``` и ```Product```. Это можно понять по внешним ключам (foreign key).

    При анализе скрипта можно отметить следующие факты:

- Все атрибуты таблиц имеют префиксы названия таблицы (например первичный ключ ProductID в таблице ```Products```)

- В таблице ```Product``` в поле ```ProductPhoto``` указан тип данных ```image```, который предполагает, что изображения в базе данных будут храниться в виде двоичных бинарных файлах.

- Также в таблице ```Product``` в качестве первичного ключа указан ключ ```ArticleNumber``` строкового типа данных

- В атрибутах, где надо указывать дату поставлен тип данных ```datetime```, что является избыточным.

Стоит отметить тот факт, что работа разработка приложения данных планируется вести через ORM **Entity Framework**. Для этого надо обеспечить поле ```Id``` числового типа у каждой таблицы и убрать префиксы названия таблицы у атрибутов.

Скрипт после редактирования представлен в **листинге 2**.

**Листинг 2**. Отредактированный скрипт базы данных
```sql

create database [SportStore]
go
use [SportStore]
go
create table [Role]
(
	Id int primary key identity,
	Name nvarchar(100) not null
)
go
create table [User]
(
	Id int primary key identity,
	Surname nvarchar(100) not null,
	Name nvarchar(100) not null,
	Patronymic nvarchar(100) not null,
	Login nvarchar(max) not null,
	Password nvarchar(max) not null,
	Role int foreign key references [Role](Id) not null
)
go
create table [Order]
(
	Id int primary key identity,
	Status nvarchar(max) not null,
	DeliveryDate date not null,
	PickupPoint nvarchar(max) not null
)
go
create table Product
(
    Id int primary key identity,
	ArticleNumber nvarchar(100) unique,
	Name nvarchar(max) not null,
	Description nvarchar(max) not null,
	Category nvarchar(max) not null,
	Photo varchar(max) not null,
	Manufacturer nvarchar(max) not null,
	Cost decimal(19,4) not null,
    DiscountAmount tinyint null,
	QuantityInStock int not null,
	Status nvarchar(max) not null,
)
go
create table OrderProduct
(
    Id int primary key identity,
	OrderId int foreign key references [Order](Id) not null,
	ProductId int foreign key references [Product](Id) not null,
)

```

