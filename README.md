# Homework 2 (еще не все)
## Дедлайн - 25 сентября 15:30

Ниже описаны условия заданий, которые вам нужно выполнить. Примеры кода с пары с некоторыми комментариями в папке Lesson2

## Task 1
### 2 балла
Реализовать следующие методы:
```java
static boolean equals(String s1, String s2) {
  // проверить, что строки совпадают без учета регистра
}

static String replace(String str, String oldStr, String newStr) {
  // в строке str все вхождения oldStr заменить на newStr
}

static String format(String surname, int mark, String subject) {
  // вернуть строку, используя форматирование: Студент [Фамилия] получил [оценка] по [предмету]
}

static boolean insPalindrome(String str) {
  // проверить, является ли строка палиндромом
}
```

## Task 2
### 3 балла
Напишите класс IntHolder, который будет хранить в себе значение типа int. Инициализация должна быть реализована через конструктор и статический метод, должны поддерживаться стандартные арифметические операции над объектами данного типа (+, -, *, /, %), также должен быть реализован метод swap(IntHolder i, IntHolder j), который будет менять значения местами. Также переопределите в классе методы equals() и hashCode() Примеры их переопределения можно найти в Lesson2/src/main/java/contract

## Task 3
### 2 балла
Напишите  неизменяемый класс Point, описывающий точку на плоскости. Предоставьте конструктор с параметрами, конструктор без аргументов (должен задавать точку в начале координат), методы доступа к координатам, а также методы translate(double x, double y) -- должен перемещать точку на заданные координаты, и scale(double x) -- изменять масштаб по обеим координатам на соответствующий коэффициент.

## Task 4
### 5 балла
Реализуйте класс Car, моделирующий передвижение автомобиля по оси Ox.

```java
public class Car {

  private String colour;
  private int fuel;
  private final int maxFuel;
  private final String model;
  private final Engine engine;
  private int mileage;

  // your code
}
```
У класса Car должны быть параметры цвета, запаса топлива, максимальной вместимости бака, модели, двигателя (подумайте над вложенными классами) и пробега. Двигатель может быть включен и выключен, а также обладает параметром расход топлива. При включенном двигателе машина двигается, при выключенном стоит на месте. В ситуации, когда закончилось горючее , машина останавливается, двигатель выключается, в консоль нужно вывести сообщение о необходимости дозаправки. У авто должен быть метод дозаправки (его нужно переопределить: дефолтный вызов без параметров заполняет бак до максимума, либо с параметром - тогда топливо увеличивается строго на указанную величину, но не более максимума) и запуска двигателя (и его остановки соответственно), и метод info() выводящий информацию о всем текущем состоянии автомобиля. Также нужно уметь выводить расстояние, которое проехала машина.  Движение автомобиля можно имитировать в цикле (пусть переменная расход отвечает за расход на 100 километров, тогда в цикле уменьшайте запас топлива на параметр расхода, а пробег увеличивайте на 100) В методе main нужно протестировать соответствующую функциональность.

## Task 5
### 3 балла
Создайте класс Pet, записываем ему в наследники Cat, Dog и Parrot. Pet должен реализовывать метод say(), в классах наследниках он должен быть переопределен. В классе Pet должны быть поля name, weight, age и owner. В классах Cat, Dog дополнительно должна быть указана порода и тип корма (дорогой/дешевый - реализуйте как enum) и метод walk(). Данный метод нужно перегрузить: в стандартной реализации он должен выводить в консоль информацию о прогулке с хозяином, также должна быть версия walk(String name) для прогулки с человеком по имени name. 
В классе Parrot должно быть поле country -- откуда он родом, а также переменная, задающая наличие или отсутсвие документов на птицу. Также должен быть метод fly(), выводящий в консоль информацию о том, что попугай по имени name улетел, но обещал вернуться через некоторое время. "Некоторое время" выбирается рандомно в пределах от 1 до 60 минут. Проверить соответствующую функциональность в методе main, создать все типы животных в переменных типа Pet, у всех в цикле (добавьте их в список или массив) вызовите метод say(), а также проверьте на тип оператором instanceof и выполните методы для соответствующего типа. Для instanceof пользоваться синтаксисом новых версий java (третий пример с презентации).

## Task 6
### 2 балла
Реализуйте record Contact с параметрами String name, String email. В конструкторе добавьте валидацию: ничего из параметров не должно быть null, имя не должно быть пустым, email должен соответствовать паттерну электронной почты(тут считаем, что у нас вся почта может заканчиваться только на @gmail.com, следовательно нужно взять соответствующую подстроку -- посмотрите про методы contains() и substing() в классе String -- и проверить, что данная подстрока соответствует @gmail.com) Также перегрузите конструктор, который принимал бы только одно значение (второе заполните чем-то дефолтным, но так, чтобы это дефолтное соответствовало валидации). Также добавьте метод printName(), который выводит приветствие с имененм из тела record.

## Task 7
### 3 балла
Для класса Car из 3 задачи реализуйте паттерн builder и инициализируйте переменные через него. Пример кода можно найти в Lesson2/src/main/java/builder

## Task 8
### 2 балла
Реализуйте sealed наследование следующих классов:
```java
class Shape {
  private double volume;

  private void print() {
   // your code
  }
}

class Ball extends Shape {
  private double radius;
  // your code
}

class Cylinder extends Shape {
  private double height;
  // your code
}

class Pyramid extends Shape{
  private double height;
  private double area; // площадь основания
   // your code
}

class ColourPyramid extends Pyramid{
  private String colour;
  // your code
}
```

Какие классы объявить non-sealed, а какие final - ваш выбор, но должны быть и те, и те. Метод print должен выводить информацию о фигуре, его нужно будет переопределить. Также в конструкторе дочерних классов можно (и нужно) пользоваться родительским конструктором. Также некоторые поля могут быть посчитаны сразу (например volume для Ball, то есть вам нужен только радиус), такие вещи нужно посчитать сразу, а не загружать конструктор лишними параметрами. В main создать переменные типа Shape для каждого из типов и вызвать нужные методы. Кто разберется с switch pattern matching и напишет его - +1 балл.
