# Data Structure
1) HashMap?
2) Какая структура внутри бакетов? Массив односвязных списков или красночерное дерево
3) Сколько дефолтно корзин? (16) Как этим управлять, увеличивается в двое? Loadfactor (75%)*capacity(16)=threshold. Что будет если произойдет преувелечение size > threshold? (перехеширование)
4) Когда из односвязного списка в красно-черное дерево? и обратно. (Если количество бакетов превысится и элементов в бакете)
5) Как добавление элемента работает? Хэш код -> определение бакета -> коллизии? Сравнение хеш кода/equals, поиск конца списка, проверка на превышение threshold.

6) Написать односвязный список?
7) Посчитать число последовательностей нулей и единиц длины n, в которых не встречаются две идущие подряд единицы.