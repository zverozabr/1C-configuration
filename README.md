# 1C-configuration

## ДАННОЕ РЕШЕНИЕ ЯВЛЯЕТСЯ ШАБЛОННЫМ!

## Возможности 1Cv8_intaro_8.2: (Разработано на примере УТ 10.3)

* Обмен заказами 
* Выгрузка каталога
* Выгрузка цен и остатков

## Возможности RetailCRM_8.3_УТ11.3 и RetailCRM_8.3_УТ11.3 api v5: 
* Передача новых заказов и всех изменений по заказам из системы retailCRM в 1С.
* Передача изменений по заказу из 1с в retailCRM.
* Синхронизация остатков и закупочных цен в 1С и в retailCRM в разрезе складов.
* Выгрузка каталога товаров в retailCRM.
* Выгрузка типов цен в retailCRM.
* Передача оплат в 1С (в качестве примера в шаблонном решении создается документ “Поступление безналичных денежных средств”)

## Объекты интеграции

### В модуле 1Cv8_intaro_8.2: 

* Общий модуль - Интаро_общий
* Подписка на событие - Интаро_документы
* Константа - Интаро_константы
* Обработка - IntaroШаблонноеРешение

### В модуле RetailCRM_8.3_УТ11.3: 

* Подсистема - RetailCRMИнтеграция
* Общий модуль - RetailCRM_Общий
* Роль - RetailCRMИнтеграция
* Общие картинки - RetailCRM и RetailCRMlogo
* Подписка на событие - RetailCRM_документы
* Константа - RetailCRM_константы
* Обработка - RetailCRMШаблонноеРешение

RetailCRM_8.3 - Данное решение является рабочим на версии конфигурации Управление торговлей, редакция 11 (11.3.3.х) / 11 (11.3.4.х для api v5) Демо, платформа 1С:Предприятие 8.3 (8.3.10.2168). 
При несоответсвии версии конфигурации с вышеуказанной возможны ошибки и дальнейшая настройка осуществляется программистом 1С. При желании можно доработать под любую другую конфигурацию на управляемых формах.


## Изменения в модуле RetailCRM_8.3_УТ11.3

* Исправлены ошибки предыдущей версиии 
* Идентификация заказов по ИД, которое теперь хранится в доп сведениях
* Исправлена процедура выгрузки остатков
* Дата актуальности вынесена как новый реквизит

## Новые возможности в модуле RetailCRM_8.3_УТ11.3

* Сохранение настроек в txt файл
* Восстановление настроек из txt файла
* Кнопка полного обмена
* Флажки выгрузки/загрузки заказов, выгрузки типов цен, остатков
* Возможность загрузки одного заказа по ID

## Новые возможности в модуле RetailCRM_8.3_УТ11.3 api V5

* Отправка ставок НДС в crm
* Получение всех типов оплат из crm 

## Порядок интеграции

* Добавляем объекты в конфигурацию - в подписке на  события необходимо выбрать в качестве источника _ДокументОбъект.ЗаказКлиента_
* С помощью обработки инициализируем константы, сохраняем.
* С помощью обработки выполняется загрузка заказов из retailCRM, выгрузка остатков и цен в retailCRM, выгрузка типов цен (если используются) и если есть необходимость то и выгрузка каталога номенклатуры в retailCRM.
* Выгрузка данных по заказу из 1С в retailCRM происходит при проведении заказа. Для этих целей и нужна подписка на событие. Её настраиваем под нужную конфигурацию.
* Для автоматической загрузки заказов настраивается регламентное задание.
* Для автоматической выгрузки остатков и закупочных цен также необходимо регламентное задание.

Подробное описание настройки можно посмотреть по ссылке: [http://www.retailcrm.ru/docs/Users/1C](http://www.retailcrm.ru/docs/Users/1C)
