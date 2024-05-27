# OOP

1) Какие есть модификаторы доступа (package private)? Зачем нужны?

```
class Parent {
   protected void className() {
   System.out.println("Parent");
   }
}
class Child extends Parent{
   void className() {
   System.out.println("Child");
   }
}
public class Test {
    public static void main(String[] args){
        Parent parent = new Child();
        parent.className();
    }
}
```
2) А можно как-то вызвать private метод? Что такое reflection?
```
Method indexOfMethod = LongArrayUtil.class.getDeclaredMethod("indexOf", long[].class, long.class, int.class, int.class);
indexOfMethod.setAccessible(true);
```
3) Что такое static ключевое слово 
4) Можно переопределить/перегрузить статический метод?

5) Вложенные классы - nested classes какие бывают? (внутренние классы (inner classed/статические вложенные классы static nested classes отличие)
Зачем нужны внутренние классы? Велосипед и педали. Можно ли объект внутреннего класса создать в статическом методе внешнего класса? (нет, тк внутренний класс без внешнего не существует). Можно ли во внутреннем классе иметь статические переменные и методы? (нет)
Анонимный класс?
Статические вложенные классы - имеет доступ только к статическим полям и методам внешнего класса.

```
class Math {
public final double secret = 2;
}

class ComplexMath extends Math {
public final double secret = 4;
}

public class InfiniteMath extends ComplexMath {
public final double secret = 8;

    public static void main(String[] numbers) {
        Math math = new InfiniteMath();
        System.out.print(math.secret);
    }
}
```

```
class One{
public static void print(){
System.out.println("1");
}
}

class Two extends One{
public static void print(){
System.out.println("2");
}
}

public class Test{
public static void main(String args[]){
One one = new Two();
one.print();
}
}
```