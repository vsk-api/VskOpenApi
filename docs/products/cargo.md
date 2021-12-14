# Страхование грузов

## Объект страхования
"insuredObject":

### "cargo": описание груза
| Параметр | Пример | Описание |
| ----- |-----|-----|
|"cargoType": |"Телекоммуникационное оборудование"|наименование груза|
|"cargoTypeEn": |"string"|наименование груза англ.|
|"cargoCategory": |"ПР"|ОЦГ - особо ценный груз, ПГ - прочий груз|
|"cargoСondition": |"NEW"|'Категория груза. NEW-новый, USED-б/у'|
|"weight": |"20 т."|масса груза|
|"quantity": |"13 мест"|количество мест|
|"packaging": |"бумажные коробки"|упаковка|
|"packagingEn": |" boxes"|упаковка англ|
|"containerNumbers": |\['ABC123','AB-C-543']|номера контейнеров |
|"containerAmount": |"22"|количество контейнеров|
|"cargoOwner": { "isPolicyHolder": }|false  |владелец груза|

### "delivery": описание транскорта
| Параметр | Пример | Описание |
| ----- |-----|-----|
|"shippingDocument": |Document|Сопроводительные документы|
|"transports": \[{"nameRu": ,"nameEn": ,"registrationNumber": }]||транспорт используемый для перевозки|,
|"conditionCarriage":| "Холодильная камера"|Условия перевозки|
|"RequirementTransport":| "Тент"|Доп. требование к ТС|
|"departureAddress":|Address|Адрес отправления|
|"destinationAddress": |Address|Адрес назначения|
|"transitAddresses":| \[{Address}]|Промежуточные адреса|
 
### Пример полиса
 
~~~
{
  "product": {
    "code": "CARGO_GENERAL"
  },
  "startDate": "2021-01-01T12:12:12",
  "endDate": "2022-01-01T12:12:12",
  "issueDate": "2021-01-01T12:12:12",
  "placeOfIssue": "Москва",
 
  "policyHolder": {
    "organization": {    
      "fullName": "ООО Самсунг СДС Рус",
      "shortName": "Самсунг СДС Рус",
      "legalForm": "OOO"   
    },
    "address": {
      "addressStr": "129515, г.Москва, ул.Академика Королева, д.2, к.3",
      "addressStrEn": "129515, г.Moscow"
    },
    "representative": {
      "person": {    
        "fullName": "Сергей",
      },
      "phone": {
        "phoneNumber": "79998887766"
      },
      "document": {
        "typeCode": "РоА",       
        "number": "23453452345",
        "dateIssue": "2020-02-02",
        "validUntil": "2030-02-02"      
      },
      "position": "Директор по продажам"
    }
  },
  
  "insuredObject": {
    "cargo": {
      "cargoType": "Золотые слитки и бриллианты",
      "cargoTypeEn": "Gold bars and diamonds",
      "cargoCategory": "ОЦГ",
      "cargoСondition": "NEW",
      "weight": "20 т.",
      "quantity": "13 мест",
      "packaging": "бумажные коробки",
      "packagingEn": "boxes",
      "containerNumbers": [
        "ABC123", "AB-C-543"
      ],
      "containerAmount": "22",
      "cargoOwner": {
        "isPolicyHolder": false
      }
    },
    "delivery": {
      "shippingDocument": {
        "number": "МФ-2592454",
        "dateIssue": "2021-09-30"     
      },
      "transports": [
        {
          "nameRu": "Авто",
          "nameEn": "Avia",
          "registrationNumber": "A123AA99"
        }
      ],
      "conditionCarriage": "Холодильная камера",
      "RequirementTransport": "Тент",
      "departureAddress": {
        "addressStr": "129515, г.Москва, ул.Академика Королева, д.2, к.3",
        "addressStrEn": "129515, г.Moscow"
      },
      "destinationAddress": {
        "addressStr": "129515, г.Москва, ул.Академика Королева, д.2, к.3",
        "addressStrEn": "129515, г.Moscow"
      },
      "transitAddresses": [
        {
          "addressStr": "129515, г.Москва, ул.Академика Королева, д.2, к.3",
          "addressStrEn": "129515, г.Moscow"
        }
      ]
    }
  }
}

~~~
