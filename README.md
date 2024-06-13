Functions — both static and non-static — can be overloaded. This means that in one class we can define several functions with the same name. When an invocation of one of these functions is encountered in the program, the compiler must know which one of them is meant: we say that it has to resolve the method call. For this to be possible, the overloaded functions have to differ in number and/or types of parameters in such a way that just by ’looking’ at the arguments of an invocation, the compiler can determine unambiguously the method to be called.

In the example below, there are three functions with the name sum.

# Listing 26 AFM-Overload/Overload.java Page 50

```java
public class Overload {
    static int sum(int a, int b) {
        return a + b;
    }

    static int sum(int a, int b, int c) {
        return a + b + c;
    }

    static String sum(String s, int a) {
        return s + a;
    }

    public static void main (String[] args) {
        int a = 4, b = 3, c = 5;
        String s = "a=";
        System.out.println(
            "Sum of a,b: " + sum(a, b) +
            "\nSum of a,b,c: " + sum(a, b, c) +
            "\nSum of s,a: " + sum(s,a));
    }
}
```
The first two overloads differ in the number of parameters/arguments. The first and the third have both two parameters, but the first of these parameters is of different type (int and String, respectively). Therefore, the compiler will always know which function to call just by ’looking’ at the number and types of arguments. The program prints:

```
Sum of a,b: 7
Sum of a,b,c: 12
Sum of s,a: a=4
```
