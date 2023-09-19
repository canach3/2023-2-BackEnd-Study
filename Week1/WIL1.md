# Week 1 과제 제출
___

```java
interface Calculator {
    int plus(int a, int b); // a + b 값 반환
    int minus(int a, int b); // a - b 값 반환
    int mul(int a, int b); // a * b 값 반환
    int div(int a, int b); // a / b 값 반환
}
class Calculate implements Calculator {
    public int plus(int a, int b) { // a + b 값 반환
        return a + b;
    }
    public int minus(int a, int b) { // a - b 값 반환
        return a - b;
    }
    public int mul(int a, int b) { // a * b 값 반환
        return  a * b;
    }
    public int div(int a, int b) { // a / b 값 반환
        return a / b;
    }
}
abstract class Animal {
    public abstract void speak();
}
class Cat extends Animal {
    public void speak() {
        System.out.println("cat Says Meow!");
    }
}
class Dog extends Animal {
    public void speak() {
        System.out.println("dog Says Woof!");
    }

}

public class WIL1 {
    public static void main(String[] args) {
        Calculator calculator = new Calculate();

        System.out.println("1234 + 4321 = " + calculator.plus(1234, 4321));
        System.out.println("911 - 170 = " + calculator.minus(911, 170));
        System.out.println("2 * 3 = " + calculator.mul(2, 3));
        System.out.println("33 / 11 = " + calculator.div(33, 11));

        System.out.println("\n");

        Cat cat = new Cat();
        Dog dog = new Dog();
        Animal[] animals = {cat, dog};
        for (Animal animal : animals) {
            animal.speak();
        }
    }
}

