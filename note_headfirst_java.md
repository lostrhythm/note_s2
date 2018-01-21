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
    
    
------  
head first design pattern









    
