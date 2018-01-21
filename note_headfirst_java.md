set PATH=%PATH%;C:\Program Files\Java\jdk1.8.0_131\bin  

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

    - 一个类包含抽象方法，那么该类必须是抽象类
    - 子类必须重写父类的抽象方法，或者声明自身为抽象类
    
抽象方法

    public abstract double computePay();
        - must be implemented in the subclass
        
    构造方法，类方法（用static修饰的方法）不能声明为抽象方法
        
        
封装 Encapsulation
    
    将 抽象性函式接口 的 实现细节部份 包装、隐藏起来 的方法
    要访问该类的代码和数据，必须 通过 严格的 接口控制
    
    最主要的功能 在于我们 能修改自己的实现代码，
    而不用修改 那些 调用我们代码的 程序片段
        
    类内部的结构 可以 自由修改
    隐藏 信息 实现细节
        
    step:
        1. set member variable as private
        2. 对 private variable 提供对外的公共方法访问，也就是创建 一对 getter和setter方法
        
        
接口 Interface
    
    抽象方法的集合
    一个类通过继承接口的方式，从而来继承接口的抽象方法
        - purely contract

    difference
        类 描述对象的属性和方法
        接口 则包含类要实现的方法
            - 无法被 实例化，可以被 实现
            - 除非 实现 接口的类 是 抽象类，否则 该类 要 定义接口中的 所有方法
            
        接口没有 构造方法
        所有的方法 必须是抽象方法
            - 方法是不能在接口中实现的，只能由实现接口的类来实现
            
        成员变量 只能是 public static final 
        不是被 继承 ，而是被 实现
        接口支持 多继承
            - multi implement
        
        不能含有 静态代码块 以及 静态方法
            - 用 static 修饰的方法
            - 隐式的指定为 public abstract, and only this is valid
                - static: class ownership?
        
        
        
    接口类型可用来 声明一个变量，
    绑定一个 实现此接口 的对象
        - interface variable
        
        
    隐式抽象的
    接口中每一个方法也是隐式抽象的
    方法都是公有
        
        
    类在实现接口的方法时，不能抛出强制性异常，只能在接口中，或者继承接口的抽象类中抛出该强制性异常
        # ???
        # how to throw?
        
    一个接口能继承另一个接口
        - is an interface able to extend other multiple interface?
        - yes!
        
        
标记接口

    最常用的 继承接口
    没有任何方法的接口被称为 标记接口
        - 给某个对象打个标（盖个戳）
        
    1. 建立一个公共的父接口
    2. 向一个类添加数据类型
        最初的目的
        该类通过多态性变成一个接口类型
            - an interface reference 
            - is able to be used to point to the new class
        
        
包(package)
    
    更好地组织类
    区别 类名的命名空间
        
    包也限定了 访问权限，拥有 包访问权限 的类 才能访问某个包中的类
        
    also 提供搜索和定位类（class）、接口、枚举（enumerations）和注释（annotation）...
        
    source code in one package, it needs to put the declearation of the package at the 
    beginning of the file
        - e.g. package animals;
        
    
    import
        import package1[.package2…].(classname|*);
            - import from other package

        类文件中可以包含任意数量的 import 声明
        import 声明必须在包声明之后，类声明之前
        
    包名 须与 目录结构 相吻合
        - 通常，一个公司使用它互联网域名的颠倒形式来作为它的包名.
        - 例如：互联网域名是 runoob.com，
        - 所有的包名都以 com.runoob 开头。
        - 包名中的每一个部分对应一个子目录。
        
            - javac -d . zz.java
            - automatically generate the delcared package structure 
        
        
    并不要求 .class 文件的路径跟相应的 .java 的路径一样。
    你可以分开来安排源码和类的目录
        - 可以将你的类目录分享给其他的编程人员，而不用透露自己的源码    
    
        
    JAR 文件按包含 Java 平台相关的类，所以他们的目录默认放在了 class path 中
        - ??
        
        
        
mark:
    http://www.runoob.com/java/java-exceptions.html
        
        
        
        
        
        
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









    
