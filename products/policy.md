# Схема договора

Каждый запрос-ответ котировки и создания полиса состоит из объектов определенной структуры. 
В этом разделе описаны все встречающиеся объекты.

## Договор
| Элемент | Пример| Описание |
| ----- | ----- | ----- |
|"policyNumber":|12345FDS76543| Номер договора |
|  "product": { "code" }|OSAGO| Код продукта|
|  "status": { "code": } |PAID| Статус оплаты договора|
|  "startDate": |2020-02-02| Дата начала договора|
|  "endDate": |2021-02-02| Дата окончания договора|
|  "issueDate": |2020-02-02| Дата выдачи клиенту|
|  "premium": | Общая премия по договору|
|  "currencyCode": |RUR| Код валюты|
|  "currencyRate": |73.33| Обменныйы курс|
|  "placeOfIssue": |Москва| Место выдачи договора|
|  "draftId": |12345-12345-12345| ИД договора|
|  "policyHolder": || Страхователь ( физ, юр.лицо ) |
|  "beneficiaries": [] || Список выгодопреобретателей по договору|
|  "additionalProperties": { ||
|    "pos":| "123", | точка продаж|
|    "discountKVPercent":| 0  | скидка от КВ|
|    "promocode":| ""  | промокод|
|  "insuredObject":|  | Объект страхования. Зависит от продукта|
    
  
## Страхователь ( юр.лицо ) 
| Элемент | Описание|
|-----|-----|
|"policyHolder": | Страхователь|
|  "organization": {}, | Юр.лицо|
|  "phone": {},  | телефон|
|  "email": "string",  | эл.почта|
|  "document": {},  | документ о регистрации|
|  "address": {},  | адрес регистрации|
|  "representative": {  | представитель |
|    "person": {},  | ФИО + |
|    "phone": {},  | номер телефона|
|    "email": "string",  |эл.почта|
|    "document": {},  |документ|
|    "address": {},  |адрес|
|    "position": "Директор по продажам"  | Должность|
    
## Выгодопреобретатель
| Элемент | Описание|
|-----|-----|
|"beneficiaryPerson": { |Физлицо|
|    "person": {},|ФИО + перс данные|
|    "address": {},|адрес|
|    "phone": {}}, |телефон|
|  "beneficiaryOrganization": { ||
|    "organization": {}, |юр.лицо|
|    "address": {},  |адрес|
|    "phone": {}}, |телефон|
|  "percents": [{"risk": ,"percent":}] |по каким покрытиям и в какой процентн |
  
##Физ.лицо  

| Элемент | Пример | Описание|
|-----|-----|-----|
|"firstName": |"Иван"| Имя|
|"lastName": |"Иванов"| Фамилия|
|"middleName": |"Иванович"| Отчество|
|"birthDate": |"2002-02-02"| дата рождения|
|"fullName": |"Иван Иванович Иванов"|Полное ФИО, часто используется в ПФ|
|"fullNameEn": |"Ivan Ivanov"|Полное ФИО на английском|
|"birthPlace": |"Москва"|Место рождения|
|"citizenship": |"RU"|Гражданство. ISO-2|
|"gender": |"M"|Пол|
|"familyState": |"SINGLE"|Семейное положение|
|"isPublicOfficial": |true|является Государственным Должностным лицом|
		
##Юр.лицо

| Элемент | Пример | Описание|
|-----|-----|-----|
|"country":| "RU"| Страна регистрации |
|"inn":| "7710026574"| ИНН|
|"fullName":| "Страховое Акционерное Общество «ВСК» "| Полное наименование|
|"fullNameEn":| "Insurance Company VSK"| Наименование по английски|
|"shortName":| "САО «ВСК»"| Краткое наименование|
|"legalForm":| "OOO"| Форма|
|"kpp":| "997950001"| КПП|
|"ogrn":| "1027700186062"| ОГРН|
|"okpo":| "3253245"| ОКПО|
|"bic":| "044525225"| БИК|
		  
##Адрес
Объект адрес встречается во многих частях полиса. Минимальный необходимый набор реквизитов зависит от места и от страхового продукта.

| Элемент | Пример | Описание|
|-----|-----|-----|
|"typeCode": | "REGISTRATION"| тип адреса|
|"countryCode":| "RU"| код страны. ISO-2|
|"region":| "г Москва"| регион|
|"city":| "Москва"| город|
|"street":| "Академика Королева"| улица|
|"house":| "3"| номер дома|
|"building":| "2"| строение|
|"flat":| "25"| квартира|
|"room":| "2"| комната|
|"zipCode":| "129515"| индекс|
|"kladrId":| "7700000000015450062"| код кладр|
|"fiasId":| "f64c75cd-a640-41ed-9893-c1aaef58e638"| код фиас|
|"addressStr":| "129515, г.Москва, ул.Академика Королева, д.2, к.3, кв.4",| полный адрес|
|"addressStrEn":| "129515, г.Moscow"| полный адрес по-английски|
        
##Документ
Минимальный необходимый набор реквизитов зависит от родительского объекта, типа документа и от страхового продукта.

| Элемент | Пример | Описание|
|-----|-----|-----|
|"typeCode": |"PASSPORT"| код документа|
|"serial": |"1234"| серия|
|"number": |"123456"| номер|
|"dateIssue": |"2020-02-02"| дата выдачи|
|"validUntil": |"2030-02-02"| срок действия документа|
|"whom": |"12 УФМС"| кем выдан документ|
|"divisionCode": |"123"| код подразделения, выдавшего документ|

##Телефон

| Элемент | Пример | Описание|
|-----|-----|-----|
|"phoneNumber": |"79091234567"| телефонный номер |
|"contactPerson": |"Сергей"| контактное лицо|

##email    
Это обычная строка для хранения адреса эл.почты.