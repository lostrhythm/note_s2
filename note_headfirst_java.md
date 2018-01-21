# Wednesday, 17-Jan-18 13:58:15  
headfirst java

    arrayList
        - P133
        .add
        .remove
        can not hold primitives
        import java.util.*

    array
        one and only instance variable
        length
        
        '[]' syntax is only used by array in JAVA

-P135
    
    objects have state and behavior
    
    put something somewhere <==> give something some position

-P151


# Thursday, 18-Jan-18 13:55:11 UTC  
circuit operator

    && ||
    
non circuit operator

    & |
    - for manipulating bits, force the jvm to check both side of the equation
        - P151
        
java.lang

    System.out.println  
    String  
    Math.random()
        - classes from a package
        
Using a library

    i.e java api  
    package name. class name
        - this is the full name
        
package

    in java 
    package is the set of classes
        
    javax
        start as extension
        then got a promotion
            - P 156
            
        Swing is the mother of all standard extensions
            - only in old version??
            - javax.swing
        
        
using ArrayList to contain primitives 
compiles will automatically "wrap" and "unwrap" it for you

import 

    is simply the way you give java the full name of a class
        - P 157
        
        
inherence

    when you call a method on an object reference,
    calling the most specific version
    the lowest one wins
        - P175
        
    is-a
        inherent relationship
        
    has-a
        member variable relationship
        
    super.method
        invoke the method of the superclass
        
        public void roam{
            super.roam();
            // following codes
        }
            - P180
            - similar to what decorator does.
        
     do not using inheritance just because reusing some code
        - can instead use a has-a relationship to reuse the code
        
     only using inheritance,
     when the subclass is a more specific type of the superclass
        - P 181
     
     
access levels
    
    - strict to loose
    private
        not inherited
        
    default
    protected
    public
        inherited
    
    
- P182
    
        
        
# Sunday, 21-Jan-18 19:08:36 UTC
polymorphism

    - contract  
    - writing a method to process the parent class instance
    - it can provide the subclass instance as well
    
    Animal myDog = new Dog();
        - parent reference -> children object
        - basic
        
    Animal[] animals = new Animal[5];
    animals [0] = new Dog();
        - P186
        - polymophic array
        
    public void giveshot(Animal a){...}
    Dog d = new Dog()
    giveshot(d)
        - polymophic parameter
        
        
non-public class

    declare class without "public"  
    can only be subclassed by classes in the same package
        - even use
       
       
To make sure the methods is worked exactly as you wish
    
    make the class final, cannot be inherented, thus cannot be overridden
        
overriden

    when doing overriden, the input and output of the methond cannot be changed,
    it need to be seen as the same to the outside world.
        - methods are contract P190        
        

- http://www.runoob.com/java/java-tutorial.html  
虚方法

    在编译的时候，编译器使用 parent 类中的 mailCheck() 方法验证该语句， 
        - if there is no such method in the parent, the compiling will not pass
        
    但是在运行的时候，Java虚拟机(JVM)调用的是 children 类中的 mailCheck() 方法。
        - 虚拟方法调用
        - mailcheck 虚拟方法
        

重写(Override)

    外壳不变，核心重写
        - params list
        - return type
    
    static method cannot be overridden
    but can be re-claimed
    
    smaller range of throwing exceptions
    
    constructor cannot be overriden
        - can only be overload
    
    principle: cannot inherent => cannot overriden
        
        
重载(Overload)

    独一无二的参数类型列表, 返回类型可以相同也可以不同
        - 参数个数或类型或顺序不一样
            - 无法以返回值类型作为重载函数的区分标准
            
        - 可以改变访问修饰符
        - 可以声明新的或更广的检查异常
        - 方法能够在同一个类中或者在一个子类中被重载
    
        - if the params list is the same
        - will be regarded as the overridden
        - but overridden also demands same ret
        
    最常用: 构造器的重载
        
    basically, overload is: the different funciton with same name.
        - a kind of duplication
        - for different application purpose
        
        
抽象类

    除了不能实例化对象之外，类的其它功能依然存在，  
    成员变量、成员方法和构造方法的访问方式和普通类一样  
    
    抽象类不能实例化对象，所以抽象类必须被继承，才能被使用
        - the method in it cannot be used directly, as the ab class cannot be instantiated
        - without instance, the methods cannot be invoked
        
    一个类只能继承一个抽象类，
    而一个类却可以实现多个接口
    
    abstract class Employee {}

抽象方法
    public abstract double computePay();
        - must be implemented in the subclass
        
------
basic blocks  

    1. print
        import java.io.*
        import java.util.*
        
        System.out.print()
        System.out.println()
        
        
    2. read file
        import java.io.*
        import java.util.*
        
        InputStreamReader ir = InputStreamReader(System.in);
        BufferedReader br = BufferedReader(ir);
        String inputline = is.readline();
        
    3. write file
    4. import 
    5. compile
    6. compile to exe
    7. read from cmd input
    
    8. final
        end of the inherent line
        no body can extend a final class
            - 189
        
------  
head first design pattern









    
