**BeanFactory** — это самый простой контейнер в **Spring**, обеспечивающий базовую поддержку **Dependency Injection (DI)**. Он основан на интерфейсе:

🔹 **`org.springframework.beans.factory.BeanFactory`**

Этот контейнер предоставляет механизмы управления жизненным циклом бинов, их создания, связывания и уничтожения.
#### 🔹 Основные характеристики `BeanFactory`

- **Ленивая инициализация**: бины создаются **только при первом запросе**, а не при старте приложения.
- **Оптимизированное использование памяти**: подходит для ресурсов с **ограниченными возможностями** (например, мобильные устройства, встроенные системы).
- **Поддержка DI**: позволяет внедрять зависимости в компоненты.
- **Механизм конфигурации через XML**: раньше использовался **XmlBeanFactory** (устарел с **Spring 3.1**).
#### 🔹 Реализации интерфейса `BeanFactory`

- **`XmlBeanFactory`** _(устаревший)_ — получал метаданные из **XML-конфигурационного файла**.
- **`DefaultListableBeanFactory`** — современная реализация, которая поддерживает аннотации и программную конфигурацию.

#### 🔹 Как создается `BeanFactory`

```java
Resource resource = new ClassPathResource("applicationContext.xml");
BeanFactory factory = new XmlBeanFactory(resource);
MyBean myBean = (MyBean) factory.getBean("myBean");
```
Но сейчас этот способ **устарел**, и вместо него используется `ApplicationContext`:
```java
ApplicationContext context = new ClassPathXmlApplicationContext("applicationContext.xml");
MyBean myBean = context.getBean(MyBean.class);
```
