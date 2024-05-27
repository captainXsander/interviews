Паттерны Проектирования
1) Listener(Observer)
```
interface Observable {
    void registerObserver(Observer o);
    void removeObserver(Observer o);
    void notifyObservers();
}
```

```
public class CatholicChurch implements Observable {
    private List<observer> parishioners;
    private String newsChurch;

    public CatholicChurch() {
        parishioners = new ArrayList<>();
    }

    public void setNewsChurch(String news) {
        this.newsChurch = news;
        notifyObservers();
    }

    @Override
    public void registerObserver(Observer o) {
        parishioners.add(o);
    }

    @Override
    public void removeObserver(Observer o) {
        parishioners.remove(o);
    }

    @Override
    public void notifyObservers() {
        for (Observer o : parishioners)
            o.update(newsChurch);
    }
}
```

```
interface Observer {
    void update (String news);
}
```

```
public class Parishioner implements Observer {
    private String name;

    public Parishioner(String name, Observable o) {
        this.name = name;
        o.registerObserver(this);
    }

    @Override
    public void update(String news) {
        System.out.println(name + " узнал новость: " + news);
    }
}
```
2) Proxy
Нужен для того чтобы например: добавить какую-то логику к существующему интерфейсу, например контроллировать доступ,
залогировать что-то etc или чтобы не выполнять сложную логику. Есть реализация интерфейса, 
прокси также реализует этот интерфейс + свою логику добавляет
3) Solid 
4) Что такое coupling и cohesion?
5) Зарефакторить код
