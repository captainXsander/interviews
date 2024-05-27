# String Java

1) Java Heap/stack, что и где хранится? Управление мусором как происходит, Трейд-сейф, ошибки при переполнении?

2) String pool?
```
String s1 = "RSHB intech is cool";
String s2 = new String("RSHB intech is cool"); / s2 = "RSHB intech is cool";
System.out.println(s1 == s2);
```
3) Какие методы у строк знаешь?
```
String str = "Alex";
str.concat(" Kulikov");
System.out.println(str);
```
4) Палиндром?

# Сериализация

1) serialVersionUID
используется для указания версии сериализованных данных. Когда мы не объявляем serialVersionUID в нашем классе явно, 
среда выполнения Java делает это за нас, но этот процесс чувствителен ко многим метаданным класса включая количество полей, 
тип полей, модификаторы доступа полей, интерфейсов, которые реализованы в классе и пр. Рекомендуется явно объявлять serialVersionUID т.к. 
при добавлении, удалении атрибутов класса динамически сгенерированное значение может измениться и в момент выполнения будет выброшено исключение InvalidClassException 

2) Если нужно передать ДТО из одного модуля в другой Объект, но поля лишние, что будешь делать? (transient)

# Datetime

1) Отличие Instant/LocalDatetime/OffsetDatetime/ZoneDatetime

2) Иниициализация даты "2024-03-19". LocalDate.of()/parse

3) Есть формат "dd.MM.yyyy" и есть дата - "2024-03-19". Можешь ее отформатировать:
```
europeanDateFormatter = DateTimeFormatter.ofPattern("dd.MM.yyyy");
LocalDate.from(europeanDateFormatter.parse("15.08.2014"))
```
4) Есть дата "2024-03-19", как найти дату предыдущего четверга?
```
date.with(TemporalAdjuster.previous(DayOfWeek.THURSDAY)));
```