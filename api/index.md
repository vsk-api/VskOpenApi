# Процесс продажи полисов


## Расчет стоимости полиса

Сервис выполняет расчет по указанным в запросе параметрам и, в случае успеха, возвращает рассчитанную премию.
При этом котировка не сохраняется в системе. 
При наличии ошибок возвращаются валидационные сообщения.
Обычно для рассчета премии достаточно минимального набора параметров, но если по продукту есть скоринг, то возможны отказы из-за того, что этого набора параметров недостаточно.


## Создание страхового полиса

Сервис позволяет сохранить полный набор данных, выполнить расчет премии и в случае успеха возвращает сохранёный полис. 
Указанные в запросе данные проходят валидацию. При наличии ошибок возвращаются валидационные сообщения. Генерируется номер договора.

## Оплата полиса

Сервис позволяет завершить оформление полиса.
Возможны 2 способа оплаты. Оплата на стороне партнера и оплата картой онлайн. 
При оплате на стороне партнера передается только факт оплаты.
При оплате картой онлайн, сначала нужно получить ссылку на страницу оплаты.

## Получение документов полиса

После оплаты полиса готовится пакет документов.