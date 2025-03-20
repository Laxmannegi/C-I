# C- Interview

**Visual Studio .Net:**
It's an IDE provide by microsoft for developing .net application.  
It is used for developing console, Windows, web application  

**Folder** : Folder is logical container in Operating System.  

**Constructor:**
1. It's a special method present under a class responsible for initializing the variables of that class.
2. The name of a constructor method is exactly the same name of the class in which it was present and more over it's a non-value returning method.
3. Each and every class required this constructor if we want to create the instance of the that class.
```c#
class Test
{
  int i;
}

Test obj = new Test(); // Valid
```
4. It's the reponsibility of a programmer to define a constructor under his class and if he fails to do so, on behalf of the programmer an **implicit constructor** gets defined in that class by the compiler.
```c#
class Test
{
  int i; string s; bool b;

  public Test(){
  i = 9;   // Initializing the variable
  s = null;
  b = false;
  }
}
```
5. Implicitly defined constructors are also know as default constructors.
6. Implicitly defined constructors are parameters less and these constructors are also know as default constructors.
7. Implicitly defined constructors are public.
8. We can also define a constructors under the class if we defined it we can call it as an explicit constructor
   and explicit constructor can be parameter less or parameterized also.
```c#
   [<modifiers>] <name>( [<parameter list>] )
   {
      -Stmts
   }
```
   **Defining** : Implicit or Explicit
   Calling : Explicit

   Summary :
   Constructor is a special method that is present in the class resposible for initializing the variable for the class.
   Every class required the constructor for the instance of the class.
   

**Type of Constructors:**
1. Default or Parameter Less Constructor
2. Parameterized Constructor
3. Copy Constructor
4. Static Constructor

- If a Constructor method doesn't take any parameters then we call that as default or parameter less. These Constructor can be defined by the programmer expilicty or else it will be default implicitly provided if there is no explicit constructor under the class.

**Parameterized  Constructor:**
If a constructor method is defined with any parameters we call that as parameterized constructor and these constructor can be defined by the programmers only but never can be defined implicitly.


**Copy Constructor :**
If we want to create multiple instances with the same values then we use these copy constructors, in a copy constructor  the constructor takes the same class as a parameter to it.

let me demostrate it.
```c#
class CopyConDemo
{
  int x;
  public CopyConDemo(int i){
    x = i;
  }

  public CopyConDemo(CopyConDemo obj){
    x = obj.x;
  }

  public void Display(){
  Console.WriteLine("Value of X is: " + x);
  }

  static void Main(){
  CopyConDemo cd1 = new CopyConDemo(10);
  cd1.Display();
  //CopyConDemo cd2 = new CopyConDemo(20);
  CopyConDemo cd2 = new CopyConDemo(cd1);
  cd2.Display();
  }
}
```
**Static Constructor:**
If a constructor is explicitly declared by using the static modifier we call that as Static Constructor. All the constructors we have defined till now are non-static or instance constructors.
```c#
class Test
{
  static Test()  //Static constructor defined explicitly
  {
  }
  public Test()  //Implicit default constructor
  {
  }
}
```
1. If a class contains any static variables then only implicit static contructure will be present
   or else we need to define them explicit whereas non-static constructor will be implicitly defined as in every class 
   (except static class) provided we did not define them explicitly.
2. Static constructor are responsible in initializing static variables and these constructors are never called explicitly 
   they are implicilty called and more over these constructor are first to execute under any class.
3. **Static constructor can't be parameterized** so overloading static constructor are not possible.

**Why constructure are need in our class?**

- Every class requires a constructor to be present init if we want to create an intance of that class.
- Every class contain an implicit constructor if not defined explicitly and with the help of implicit constructor the instance 
  of class can be created.
  
**What is the need of defining a constructor explicitly again?**
  Implicit constructors of a class will initialize variables of a class with the same value even if we create multiple 
  instance of that class.

  - If we define constructors explicitly with parameters then we get a chance of initializing the fields or variables of the class with a new value every time we are going 
    to create instance of that class.
  - Whenever we define a class first identify whether if the class variables requires some values to execute and if they are required then define a constructor explicitly 
    and pass values thru that constructor, so that every time the instance of class is created we get a chance of passing new values.

Note : Generally every class requires some values for execution and the values that are required for a class to execute are always send to that class by using the constructor only. 


**Static Constructors vs Non-Static Constructors:**
- If a constructor is explicitly declared by using a static modifier we call that constructor as static constructor whereas 
  rest of other are non-static constructors only.

- Constructors are responsile for initializing fields/variables of a class, static fields are initialized by static 
  constructors and non-static fields are initialized by non-static constructors.
  
- Static Constructors are implicitly called whereas non-static constructors must be explicitly( when we are create instance of a class) called.
- Static constructors executes immediately once the execution of a class starts and more over it's the first block of code to run under a class whereas non-static 
  constructor executes only after create the instance of class as well as each and every time the instance of class is created.
- In the life cycle of a class static constructor executes one and only one time whereas non-static constructor executes for
  zero of no instances are created and "n" times if "n" instances are created.
- Non-static constructors can be parameterized but static constructor cannot have any parameter because static constructors are impliclity called and more over it's the 
  first block of code to run under the class.
- Non-static constructors can be overloaded where as static constructor can't be overloaded.
  
- Every class contain an implicit constructor if not defined explicilty and those implicit constructor are defined based on the following criteria:
  - Every class except a static class contains an impicit non-static constructor if not defined with an explicit   
    constructor.
  - Static constructors are implicitly defined only if that class contains any static fields or else that constructor will not be present at all.
 
 ---------------------------------------------------------------------------------------------------------------------------
#
Variable of a class
Instance of a class
Reference of a class

Variable of a class:  a copy of the class that is not initialized.

Instance of a class: a copy of the class that is initialized by using the new keyword.

Class: It's a user-defined type / data type. / Class is collection object
If you want to consume of a class, we need to create a copy of it.

```c#
int = 100; // int is only a buleprint for your particular data, it doesn't have any memory location.
int i = 100;

string = "Hello";
string s = "Hello";

Instance of a class only when we use new keyword.

First f = new First(); //f is instance of class
    or
First f;               //f is variable of class
f = new First();       //f is instance of class
```
Memory allocation is done only  after creating instance , untill and unless you create an instance memory allocation will be done. Instance can be created only by using the new keyword
Every instance unique itself.  
The changes made on one instance never relfect on another instance.  

**Reference of a class:**
References is copy of the class that is initialized by using an existing instance and references of class will not have any memory allocation they will be sharing the same
memory of the instance that assigned for initializing the variable.

- Reference of class can be called as a pointer to the instance and every modification we perform on the members using instance reflects when access those members thru refernce and vice-versa.
```c#
First f1 = new First(); // f1 is instance of class
First f2 = f1; // f2 is reference of the class;  f2 is pointer to f1; f2 doesn't have any separate memory location. f1 and f2 will be consuming the same memory in this context.
```
###  Access Specifiers:

It's a special kind of modifiers using which we can define the scope of a type and it's members.

- Private
- Internal
- Protected
- Protected Internal
- Public

```c#
//Consuming members of a class from same class
namespace AccessDemo1
{
  public class Program 
  {
     private void Test1()
     {
        Console.WriteLine("Private Method");
     }
     
     internal void Test2()
     {
        Console.WriteLine("Internal Method");
     }
     
     protected void Test3()
     {
        Console.WriteLine("Protected Method");
     }

     protected internal void Test4()
     {
        Console.WriteLine("Protected Internal Method");
     }
     
     public void Test5()
     {
        Console.WriteLine("Public Method");
     }
     
     static void main(string[] args)
     {
        Program p = new Program();
        p.Test1(); p.Test2();p.Test3();
        p.Test4(); p.Test5();
        Console.ReadLine();
     }
  }
}

Private Method.
Internal Method.
Protected Method.
Protected Internal Method.
Public Method.
```
**Note: A member of a class that is defined with any scope is always access within a class. If there are any ristriction, the ristrict will start when go outside the class.**
```c#
//Consuming members of a class from child class of same project
namespace AccessDemo1
{
  class Two:Program
  {
    static void Main()
    {
      Two t = new Two();
      t.Test2(); t.Test3(); t.Test4(); t.Test5();
    }
  }
}

**Output** 
> Private // Member can't be access in child access
> Internal Method
> Protected Method
> Protected Internal
> Public Method
```
### Important
- Private : The method is accessable only within the class in which it was defined. 
- The Default scope of every method of a class is private. / Every member of class is by default private.
- We can't declare types as private; so we can't declare private class. 
- Elements defined in a namespace cannot be explicitly declared as private, protected or protected internal
- What can use on a class is public and internal by default is internal.
  
```c#
//Consuming members of a class from non-child class of same project
namespace AccessDemo1
{
  class Three
  {
    static void Main()
    {
      Program t = new Program();
      t.Test2(); t.Test4(); t.Test5();
    }
  }
}
**Output**
> Internal
> Protected Internal
> Public
```
**Note : Members declare as a protected in a class are accessable only within the child. Not access from non-child class**

```c#
//Case 4: Consuming members of a class from child class of different Project
namespace AccessDemo1
{
  class Four:Program
  {
    static void Main()
    {
      Program t = new Program();
      t.Test3(); t.Test4(); t.Test5();
    }
  }
}
**Output:**
> Protected
> Protected Internal
> Public

```
Internal : If you declared a member or classs as **internal** it is accessable only within the project from child and as non-child also.

```c#
//Case 5: Consuming members of a class from non-child class of different Project
namespace AccessDemo1
{
  class Five
  {
    static void Main()
    {
      Program t = new Program();
      t.Test5();
    }
  }
}

**Output**
> Public

```
> [!IMPORTANT]  
> Can I call private Method? No, Why - not in the same Class  
> Can I call internal Method? No, Why - not in the same Project  
> Can I call protected Method? No, Why - Not a child Class  
> Can I call protected Internal? No, Why - if internal , protected are not accessible , then protected Internal also will not be accessible

> [!NOTE]  
> **Private** : Within the class  
> **Internal** : Within the Project both from child and non-child class  
> **Protected**: Within the class and Within the child class  
> **Protected Internal**: Either Within the Project or Within the child class of other projects  
> **Public**: Global can access from anywhere

![image](https://github.com/Laxmannegi/C-I/assets/15025418/9f92060c-f00e-42b4-a69f-685c20f9f900)


**_Different kind of Variable_**  

1. Non-static
2. Static
3. Constants
4. Readonly

**_Non-static and Static_**  

- If a variable is explicitly declared by using the static modifer or else if a variable is declared under any static block then those varibles are static where as rest of 
 the other are non-static.

Note: Static members of a class doesn't require the instance of class for initailization or execution also, 
where as non-static members of a class require the instance of class both for initialization and execution.

- Static variables of a class are initialized immediately once the execution of class starts, where as instance variables are initialized only after the creating the class instance as well as each and every time the instance of class is created.
- In the life cycle of a class a static varible is initialized one and only one time,
  whereas instance variables are initialized for 0 times if no instance are created and n times if n instances are created.
  
- Initialization of instance/non-static variables is associated with instance creation & constructor calling,
  so instance variables can be initialized thru the constructor also.
[Image]

```c#
class Program
{
  int x = 100;          //Non-static
  static int y= 200;    //static
  const float pi;  //**Error: A Const field requires a value to be provided**
  const float pi = 3.14; // **Error: Literal(mean value) of type double cannot be implicity converted to type 'float'; use an 'F' suffix to create a literal of this type**
  const float pi = 3.14f;
  readonly bool flag;
  public Program()
  {
      this.flag = true;
  }
  static void Main(string[] args)
  {
      int z;  //static
      Console.WriteLine(y); // A Static is initialize immediately once the execution of class start.
      Console.WriteLine(x); // giving error; Why? -> The reason is - the memory of x is going to be allocated only if we created the instance of the class.
      Console.WriteLine(pi); // Const and static doesn't required instance of a class.
      Program p1 = new Program();
      Console.WriteLine(p1.x);

      Program p2 = new Program();
      Console.WriteLine(p2.x);
  }
}
```
**_Constant_**  
If a variable is declared by using the keyword "const" we call it as a constant variable 
and these contant variables can't be modified once after their declaration,
so it's must to initialize constant variables at the time of declaration only
```c#
const float pi = 3.14f;
```
- The behaviour of constant variables will be similar to the behaviour of static variables.
   i.e. initialized one and only one time in the life cycle of a class and doesn't require the instance of class for accessing or initializing.
Note : (If it create of multiple copy of value , it's a wastage of memory creating a same value of every instance)

- The only difference between static and constant variable is static variables can be modified where as constant variable can't be modified.

**Readonly**  
If a variable is declared by using the readonly keyword we call that variables as a readonly variable and these variables also can't be modified like constants but after initialization.   
It's not compulsory to initialize a readonly variable at the time of declaration, they can also be initialized under the constructor.   

The behaviour of readonly variables will be similar to the behaviour of non-static variables, i.e. initialized only after creating the instance of class and once foreach instance of the class is created.   
- The only difference between readonly and instance variables is instance variables can be modified, but not readonly variables.  
- Constant variables is a fixed value for the whole class where as readonly variables is a fixed value specific to an instance of class.   
- Constant variable value cannot modified after declaration but Readonly variables cannot modified after initialization.
  
> [!WARNING]
- A readonly field cannot be assigned to (except in a constructor or a variable initializer).  

> [!IMPORTANT]  
> **what is an instance variable?**.  
> **Instance** -> also called as non-static variables what is it, maintains one copy for each instance of the class created and intializes only the instance is created. if you create N instances N copy , zero instance zero copy.   
> **Static** -> Maintain one value for the whole class , can be modified, will not create multiple copyies. Intializes one and only.   
> **Constant** -> These variables can't be modified by after declaration, you must assigned the value at the time of declaration only. You can't be modified the value. Maintain one and only one copy though out the class life cycle.   
> **Readonly** -> These variables also can't be modified but after initialization not after declaration, maintain the copy of each instances. Once the initialization done we can't be modified the value.   


--------------------------------------------------------------------------------------------------------------

**Inheritance**
It's a mechanism of consuming the members of one class in another class by establishing parent/child relationship between the classes which provides re-usability.   
```c#
[<modifers>] class <child class> : <parent class>
class A {
- Members
}
class B:A {
- Consuming the members of A from here
}
```
Note: In inheritance child class can consume members of it's parent class as if it is the owner of those member's (expect private members of parent).

 A => Parent or Base or Super
 B => Child or Derived or Sub

1. Parent classes constructor must be accessible to child class, otherwise inheritance will not be possible.   
2. In inheritance child class can access parent classes members but parent classes can never access any member that is purely defined under the child class.   
Error :  'Class1' does not contain a definition for 'Test3' and no extension method 'Test3' accepting a first argument of type 'Class1' could be four(are you missing a using directive or an assembly reference?).   


```c#
namespace InheritanceProject
{
  class Class1
  {
    // class1 parent constructor should be public 
    public Class1()
    {
      Console.WriteLine("Class1 constructor is called");
    }
    public void Test1()
    {
      Console.WriteLine("Method 1");
    }

    public void Test2()
    {
      Console.WriteLine("Method 2");
    }
  }

  class Class2 : Class1
  {
    //Private Constructor ;  **Class1** constructor should be access to be Class2 not class2 to class1
    Class2()
    {
      Console.WriteLine("Class2 constructor is called");
    }
    public void Test3()
    {
      Console.WriteLine("Method 3");
    }

    static void Main()
    {
      Class2 c = new Class2();
      c.Test1();
      c.Test2();
      c.Test3();
    }
  }
}

OutPut:
Class1 constructor is called
Class2 constructor is called // Private constructor called
Method 1
Method 2
Method 3

-: Whenever the child class instance is created the child class constructor will implicitly call it's parent class constructors.

**Don't Forget**  
- Even I don't define a constructor their will be a constructor.
- Default of scope of class members is private

**Class2** constructor is not public , **Class2** constructor doesn't required to be public why? **Class1** constructor should be access to be Class2 not class2 to class1.  
When child class instance is created it's implicitly call the parent class constructor.   
```
```C#
static void main()
{
  Class1 p ; //p is a variable of class1
  Class2 c = new Class2(); //c is instance of Class2
  p = c; // p is a reference of parent class created by using child class instance
  p.Test1();
  p.Test2();
  p.Test3(); // Error still we can't be able to call child class method.
  Console.ReadLine();
}
Error:  
// Use of unassigned local variable 'p'
```
We can initialize a parent classes variables by using the child class instance to make it as a reference, So that the reference will be consuming the memory of child class instance,   but in this case also we can't call any pure child class members by using the reference.

**Remember**
1. Parent class constructor must be accessable to child class or else inheritance will not be possible.  
2. In inheritance child classes can access parent classes members but a parent class can never access its child class members.  
3. We can inialize a parent class variable by using it's child classes instance to make it as a reference and that reference will be consuming the memory of child class instance but 
   with that reference we can't call any child class members.  
**4. Every class that is defined by us or pre-defined in the libraries of the language has a default parent class i.e Object class of system namespace.**  

 > [!IMPORTANT]  
> General when we define a class we think like we didn't from inherit any class but by default your is inherited from object class. And Object is a parent class of all the class that is present in our base class libary well as each and every class what we are defined here object is a parent class so, because the object is a parent class member of the object class.    
> 4 Important memeber are  
> - Equal()  
> - GetHashCode()  
> - GetType()  
> - ToString()
>   are accessable from any where.  

![image](https://github.com/Laxmannegi/C-I/assets/15025418/0c0f6fd8-233c-45f5-b39c-dbb44894b9c2)

Object(always on the top any Parent class of Class1)   
 
Class1(Class1 is a child of Object class and parent class of class2)  

Class2  

Class3  

Types of Inheritance:  
No. of parent classes a child class have or the no. of child classes a parent class have.
1. Single
2. Multi-Level
3. Hierarchical
4. Hybrid
5. Multiple


Single Inheritance  
Multiple Inheritance

- If at all a class has 1 immediate parent class to it we call it as single inheritance and if it has more than 1 immediate parent class to it we call it as multiple inheritance.
- In C# we don't have support for multiple inheritance thru classes. What we are provided is only single inheritance thru classes.


```c#

namespace InheritanceProject
{
  class Class1
  {
    public Class1(int i)
    {
      Console.WriteLine("Class1 Constructor is called": + i );
    }
    public void Test1()
    {
      Console.WriteLine("Method 1");
    }
    public void Test2()
    {
      Console.WriteLine("Method 2");
    }
  }

  class Class2
  {
    public Class2(int a):base(a)
    {
      Console.WriteLine("Class2 Constructor is called");
    }
    public void Test3()
    {
      Console.WriteLine("Method 3");
    }
  }

  static void Main()
  {
    Class2 c = new Class2(10);
    Console.ReadLine(); 
  }
}

 In the first point we learnt whenever child class instance is created, child class constructor will implicity call it's  
 parent classes constructor but only if the constructor is paremeter less, where as if the constructor of parent is  
 parameterized, child class constructor can't impilictly call it's parent's constructor, so to overcome the problem it is the  
 responsibility of the programmer to expilicitly call parent classes constructor from child class constructor and pass values  
 to those paramters to call parent's constructor from child class we need to use the **base** keyword.  
```
2. Multilevel Inheritance
   ```C#
   class BaseClass { }
   class IntermediateClass : BaseClass { }
   class DerivedClass : IntermediateClass { }
   ```
3. Hierarchical Inheritance : Multiple classes inherit from a single base class.
   ```C#
   class BaseClass { }
   class ChildClass1 : BaseClass  { }
   class ChildClass2 : BaseClass  { }
   ```
 **Why C# doesn't support mutiple inheritance?**  
 C# does not support multiple inheritance for classes primarily to void the complexity and ambiguity it can introduce, which can make code diffcult to maintain and debug.
 
 **Ambiguity Problem (Diamond Problem)**  
 When a class inherits from two base classes that have methods and properties with the same name, it creates ambiguity. This issue is often referred to as the "Diamond problem".
 or  
 The Diamond Problem occurs in multiple inheritance when a class inherits from two base classes that have a common ancestor, creating ambiguity about which inherits method or
 property to use. Since C# does not allow multiple inheritance for classes, this problem is avoided.

 ```C#
 class A
 {
    public void Display()
    {
 	Console.WriteLine("Class A Display");
    }
 }
 class B : A
 {
    public void Display()
    {
	Console.WriteLine("Class B Display");
    }
 }
 class C : A
 {
    public void Diplay()
    {
	Console.WriteLine("Class C Display");
    }
 }
 //Hypothetical case of multiple inheritance:
 Class D : B,C
 {
    //Ambiguity: Which 'Display' method should D use?
 }

//Usage:
D obj = new D();
obj.Display(); //Ambiguous: B's Display or C's Display?
 ```
 
**Entity :** It's a living or non living object associated with a set of attributes.  

step 1: Identify the entities that are associated with the application we are developing.

-------------------------------------------
Method Overloading:  
-------------------------------------------

public void Test()  
public void Test(int i)  
public void Test(string s)  
public void Test(int i, string s) // Order of parameter change  
public void Test(string s, int i) // Order of parameter change  

public string Test() //Invaild --Parameter is important; Return can't be consider;
// bacause ambiguity of method come out (same method name and same paramter so, identification of which method has to been call is a confusion, so execution was will not take place for you.  
// You may have a dought return type are different? yes, return is different , return type are return of method will come into picture in the end of execution but the confusion is  
// here where to start there is not clearity where to start the execution, When you don't know the where to start talking about the end of excution is foolishness. So first thing what  
// to required is where to start is not clear, so talking about end is not point here why where is not clear here.. that is why return type will never taken into considersion.  ).

**The call is ambiguous between the following methods or properties: 'Program.Test()' and 'Program.Test()'.**

--------------------------------------
Polymorphism
--------------------------------------
--Pending


# Method Overriding:
It's an approach of re-implementing a parent classes method under the child class with the same signature.

```C#
Class1
Show()
Show(int i)  
Test()  
  
Class2 : Class1
Show(string s)  
Test()  

```
Overloading:  
1. In this case we define multiple methods with the same name by changing their parameters.
2. This can be performed either within a class as well as between parent child classes also.
3. While overloading a parent classes method under the child class, child class doesn't require to take any permission from the parent class.
4. Overloading is all about defining multiple behaviours to a Method.

   
Overriding:  
1. In this case we define multiple method with the same name and same paraters.
2. This can be performed only between parent child classes can never be performed with in the same class.
3. While overriding a parent's method under child class requires a permission from it's parent.
4. Overriding is all about changing the behaviour of parent's class method under child class.

 Note : If we want to override a parent's method under the child class first that method should be declare by using the virtual modifier in parent class.

 Class1
 public virtual void Test() //Overidable
   - Any virtual method of the parent class can be overriden by the child class if required by using the override modifier.  

 Class2:Class1
 public override void Test() // Overriding

```C#

namespace MethodOverriding
{
  class LoadParent
  {
    public void Show()
    {
      Console.WriteLine("Parent show Method is called");
    }
    public virtual void Test()
    {
      Console.WriteLine("Parent Test Method is called");
    }
  }

  class LoadChild:LoadParent
  {
    //Overloading show's method in child class
    public void Show(int i)
    {
      Console.WriteLine("Child's Show Method Is Called");
    }
    //Overriding Test's method in child class
    public override void Test()
    {
      Console.WriteLine("Child's Test Method Is Called");
    }
  }

  static void Main()
  {
    LoadChild c = new LoadChild();
    c.show(5);
    c.show();
    c.Test();
  }
}

```
# Method Hiding:

- Method overriding is an approach of re-implementing a parent classes method under the child class exactly with the same name and signature.

- Method Hiding/Shadowing is also an approach of re-implementing a parent classes method under the child class exactly with the same name and signature.
  
- In the first case child class re-implements it's parent class method which are declare as virtual, where as in the second case child class can re-implement any parent's method even if the method is not declared as virutal.

```C#
namespace MethodHiding
{
  class ParentClass
  {
    public virtual void Test1()
    {
      Console.WriteLine("Method Test1 from parent class.");
    }

    public void Test2()
    {
      Console.WriteLine("Method Test2 from parent class");
    }
  }

  class ChildClass:ParentClass
  {
    public override void Test1() //Method Overriding
    {
      Console.WriteLine("Method Test1 from child class");
    }

    public new void Test2()  //Method Hiding/Shadowing
    {
      Console.WriteLine("Method Test2 from child class");
    }
    or

    public void Test2()  //warning message
    {
      Console.WriteLine("Method Test2 from child class");
    }

    static void Main()
    {
      ChildClass c = new ChildClass();
      c.Test1();
      c.Test2();
    }
  }
}
```
[Image] Warning message method hiding;



We can re-implement a parent class method under child class by using 2 approaches:
  1. Method Overriding
  2. Method Hiding/Shadowing

- After re-implementing parent class methods under child classes the child class instance will start calling the local methods only that is the re-implemented method if required in any case we can also call the parent methods from child classes by using 2 approaches.
  1. Directly create the instance of parent class under child class, We can parent's method from child class.
  2. By using the **base keyword** also we can call parent's method from child class, but keyword like this and **base can't be use from static blocks**

[image]



Note:
- A Parent class reference even if created by using the child class instance cannot access any members that are purely defined under the child class. **But can call overridden members of child class.** Because overriden members are not considered as pure child class members, but members which are re-implemented by using the approach of hiding are considered as pure child class members and not accessible to parent's references.
   
- using P I can't purely define parent class method..
  
```C#
static void Main()
{
  ChildClass c = new ChildClass(); //c is Instance of child class
  ParentClass p = c; // P is a reference of parent class by created by using child's
  p.Test1(); //Invokes child classes method // In overriding a parent a class reference can call child class overridden members 
  p.Test2(); //Invokes parent classes method // but in hiding a parent a class reference can't call child class method by which is re-implemented by hiding approach
}

**Important:**  
B/w : In overriding parent class as a given a permission for the child for re-implementing the method and when the child class re-implement those method,
parent class will identify them / recogized them, because the parent class recoginzed us,  parent class able to call child methods.  
But In method hiding remember without taking any permission from parent class , child class started re-implemention,
because the child class started without taking any permission parent reference will not recognized this. so in this case invoke parent class method.  

```

# Operator Overloading


Method Overloading is an approach of defining multiple behaviours to a method and those behaviours will vary based on the parameters of that method.

```C#
String str = "Hello how are you";
str.Substring(14);  you;
str.Substring(10);  are you;
str.Substring(10, 3) are;
```

Operator overloading is also an approach defining multiple behaviours to an operator and those behaviours will vary based on the operand types between which the operator
is used. For example + is an addition operator when used between 2 numeric operands and it is an concatenation operator when used between 2 string operands.
  Number + Number  => Addition
  String + String  => Concatenation

```C#
int x = 10;
int y = 20;
int z = x + y; // "+ so, here the is confusion is all about, how exactly a computer knows  when + is used to b/w this, it has to add two number".
int m = x -y;
int b = x > y;

public static int operator +(int a, int b)
public static int operator -(int a, int b)
public static bool operator >(int a, int b)
public static string operator +(string a , string b)
public static bool operator ==(string a, string b)
public static bool operator !=(string a, string b)

string s1 = "Hello";
string s2 = "World";
string s3 = s1 + s2;
bool b1 = s1 == s2;
bool b2 = s1 != s2;
```
"Can we substraction two string, no , if you try do also we get an error why we get an error the reason is there no predefine operation method avaiable for performing a substraction between two string "
[image]

[<modifiers>] static <return type> operator <opt> (<operand types>)
{

}

# Abstract Class and Abstract Method

- A Method without any method body is known as an abstract method, What the method contians is only declaration of the method.
- If a method is declared as abstract under any class then the child class of that class is reponsible for implementing the method.
- The concept of abstract methods will be nearly similar to the concept of Method Overriding.

- A class under which we define abstract methods is known as an abtract class.

  Note : To define a method or class as abtract we require to use abstract keyword on them.
  
```C#
abstract class Math
 {
    public abstract void Add(int, int y);
 }
```

```C#
class Class1
{
  public virtual void Method1()
  {

  }
}
class Class2 : Class1
{
  public override Method1() // Optional
  {
   -- Re-implementation
  }
}
```

```C#
abstract class Class1
{
  public abstract void Method1();
}
class Class2 : Class1
{
  public override Method1() // Mandatory
  {
   -- implementation
  }
}
```

# Abstract Class:
  - Abstract Methods
  - Non-abstract Methods

# Child class of Abstract Class:
- Implemenation each and every abstract method of parent class.
- Now only we can consume non-abstract methods of parent class.


-----------------------------------
Abstract Method : A  method without any body is known as abstract method.
Abstract Class : A Class which contains any abstract members in it is known as abstract class.

Entities: Rectangle, Circle, Triangle, Cone

Rectangle: Width, Height
Circle: Radius, Pi
Triangle : Width, Height
Cone : Radius, Height, Pi

Width, Height, Radius, Pi

```C#

namespace FigureNamespace
{
  public abstract class Figure
  {
    public double Width, Height, Radius;
    public const double Pi = 3.14;
    public abstract double GetArea();
  }

  public class Rectangle : Figure
  {
    public Rectangle(double Width, double Height)
    {  
      this.Width = Width;
      this.Height = Height;
    }
    public override double GetArea()
    {
      return Width * Height;
    }
  }

  public class Circle:Figure
  {
    public Circle(double Radius)
    {
      this.Radius = Radius; 
    }
    public override double GetArea()
    {
      return Pi * Radius * Radius;
    }
  }

  public class Cone:Figure
  {
    public Cone(double Radius, double Height)
    {
      this.Radius = Radius;
      this.Height = Height;
    }
    public override double GetArea()
    {
      return Pi * Radius (Radius + Math.Sqrt(Height * Height + Radius * Radius));
    }
  }
  class TestFigure
  {
    static void Main()
    {
      Rectangle r = new Rectangle(12.67, 56.78);
      Circle c = new Circle(45.67);
      Cone cn = new Cone(34.98, 12.98);

      Console.WriteLine("Area of Rectangle: " + r.GetArea());
      Console.WriteLine("Area of Circle:" + c.GetArea())
      Console.WriteLine("Area of Cone:" + cn.GetArea())

      Console.ReadLine();
    }
  }
}
```
--------------------------------------------------------------
# Interface

Class: It's a user-define data type
Interface: This is also an user-defined data type only.

Class: Non-Abstract Methods (Methods with method body)
Abstract Class : Non-Abstract Methods (Methods with method body) and also Abstract Method (Method without method body).

Interface:  Contains only Abstract Methods (Methods without method body).

Note: A class can inherit from a class and interface at a time.
1. The default scope the members of an interface is public whereas it's private in case of a class.
2. By Default every member of an interface is abstract so we don't require to use abstract modifier on it again.
3. We can't declare any fields/variables under an interface.
4. If required an interface can inherit from another interface.
5. Every member of an interface should be implement under the child class of the interface with out fail, but while implementing we don't require to use override modifer just like we have done in case of abstract class.
6. We can't create a instance of Interdace , but we can created a reference of interface.
   
[interface image]

public abstract void Add(int a, int b);


What is an interface?
An interface is also a user-defined type like a class but can contain only abstract methods in it.

How to define a interface ?
[<modifiers>] interface <Name>
{
  - Abstract Member Declarations
}

Multiple Iheritance with Interface:

- single
- Multi-Level
- Hierarchical
- Multiple
- Hybrid

- Even if multiple inheritance is not supported thru classes in Csharp, it is still supported thru interfaces.

- A class can have one and only one immediate parent class, whereas the same class can have any number of interfaces as it's parent i.e multiple inheritance is supported in CSharp thru interfaces.

![image](https://github.com/Laxmannegi/C-I/assets/15025418/897974c4-7754-4726-80e5-a701f88025c8)



**Why multiple inheritance is not supported thru class and how is it supported thru interfaces?**  
Multiple inheritance is not supported thru class because we came accross ambiguity problem

```text
You are dealing with ambiguous situations when you see that there is more than one solution to a problem, but you aren't sure which one to do. Or, it might be when you come to a conclusion about a situation, but before you can act on it, the situation has already changed.
```

```C#
namespace InterfaceProject
{
  interface Interface1
  {
    void Test();
  }
  interface Interface2
  {
    void Test();
  }
  class MultipleInheritanceTest: Interafce1, Interface2
  {
    public void Test()
    {
      Console.WriteLine("Interface Method implemented in child class");
    }
  }
}
```
# Structure

- Class is a user-defined type.
- Structure is also a user-defined type.

- Structure in C language can contain only fields in it where as structure in CSharp can contain most of the members what a class can contain like Fields, Methods, Constructors, Properties, Indexers, Operator Methods etc.

  [<modifiers>] struct <name>
  {
    - Define members here
  }

  ```C#
  namespace DemoProject
  {
    struct MyStruct
    {
      Public void Display()
      {
        Console.WriteLine("Method in a structure");
      }
      static void Main()
      {
        MyStruct m1 = new MyStruct();
        m1.Display();
        Console.ReadLine();
      }
    }
  }
  ```

Difference between Class and Structure:

1. Class is a reference type whereas structure is a value type.
2. Memory allocation for instances of class is performed on managed heap whereas memory allocation for instance of structure is performed on stack.
3. We use class for representing an entity with larger volumes of data whereas we use structures for representing smallar volumes of data.

Note:  All pre-defined data types under the libraries of our language which comes under reference type category E.g: String and Object are classes, whereas all the pre-defined data types which come under value type category E.g: int(Int32), float(single), bool(boolean) are structures.

4. In case of a class "new" is mandatory for creating the instance whereas in case of a structure it is only optional.
5. Fields of a class can be initialized at the time of declaration whereas it's not possible with fields in structure.

Note: If the structure contain any fields then we need to initialize those fields either by explcitly calling the default constructor with the help of "new" or else if we are not using "new" for creating the instance we need to explicitly assign value to the field referring it thru the instance and assign values.

[image]

6. We can define any constructor under the class that is either parameter less or parameterized and if no constructor is defined
   then there will be an implicit constructor which is default whereas in case of a structure parameter less of default whereas in
   case of a structure parameter less of default constructor is always implicit and can't be defined explicitly again, what we can
   define is only parameterized constructor.

7. If zero constructor are defined in a class after compilation where will be 1 constructor (Implicit) and if we define "n" constructors in a class after compilation there will be "n" constructors only whereas in case of a structure if we define "0" constructors then after compiliation there will be 1 constructor (Implicit) and if we define "n" constructors after compilation ther will be "n + 1" constructors.
8. Class can be inherited by other classes, whereas structure can't be inherited by other structures i.e. a structure doesn't support inheritance.
9. A class can implement an interface same as that a structure also can implement an interface.


# Enumeration or Enum Type:

```C#
[<modifiers>] enum <name> [:Type]
{
-- list of name constant values
}

namespace DemoProject
{
  public enum Days
  {
    Monday,
    Tuesday,
    Wednesday,
    Thursday,
    Firday
  }
  class TestClass
  {
    
  }
}
```
Properties:
Property is a member of class using which we can expose values associated with a class to the outside enviroment.


# Indexers:
Modifier <type> this [int index]
{
  [get {<stmts>}] //Get Accessor
  [set {<stmts>}] //Set Accessor
}

[image]

```C#
namespace std
{
  public object this [int index]
  {
    get
    {
     if (index == 0)
      return Eno;
     else if (index == 1)
      return Ename;
     else if (index == 2)
      return Job;
     else if (index == 3)
      return salary;
     else if (index ==4)
      return Dname;
     else if (index == 5)
      return Location;
     else
      return null;
    }

  set
  {
    if(index == 1)
     Eno = (int)value;
    else if(index ==2)
     Ename = (string)value;
    else if(index == 3)
     Job = (string)value;
    else if(index == 4)
     salary = (double) value
    else if(index == 5)
     Dname = (string)value;
    else if(index == 6)
     Location = (string)value;

  }
}
  public object this [string name]
  {
    get
    {
     if (name.ToUpper() == "ENO")  // Case sensitive issue in this case
      return Eno;
     else if (name.ToUpper() == "ENAME")
      return Ename;
     else if (name.ToUpper() == "JOB")
      return Job;
     else if (name.ToUpper() == "SALARY")
      return salary;
     else if (name.ToUpper() == "DNAME")
      return Dname;
     else if (name.ToUpper() == "LOCATION")
      return Location;
     else
      return null;
    }
}
}
```
Note:  
If you define a indexer in class, class is working like virtual array.

-----------
# Delegate

It's a type safe function pointer.
(Delegate is type, a class is a type stuct is a type , interface is a type all these are user-define type , class is user-define type , interface is a user-define type. as the Delegate is also user-define type.
generally if we understand the Different b/w class and struct the main difference b/w class and struct is  class is reference type and struct is a value type same as delegate is a reference type. )

( If your are with vs every you define class will be under namespace same way a struct, interface whatever you are doing everthing are define under a namespace, why type are going to be define under a namespaces namespace is a logical container of types and because namespace is a logical container of type we are going to be all type inside namespace. so, Now if the question aries where i should a define a namespace  )

- A delegate holds the reference of a method and then calls the method for execution.  

- To call a method by using a delegate we have 3 steps:  

1. Define a delegate  
Modifier delegate void [type <name>]([<parameter list>])  

public delegate void AddDelegate(int x, int y);  
public void AddNums(int a, int b);  

Public delegate string SayDelegate(string name) //delegete signature is going to match return type and parameter of method
public static string SayHello(string name)

2. Create an instance of delegate
  public delegate void AddDelegate(int x, int y);
  public delegate void SayDelegate(string name);

3. Now call the delegate by passing required parameter values, so that interally the method which is method with the delegate
   get execute

```C#
namespace DelegateProgram
{
  public delegate void AddDelegate(int x, int y);
  public delegate void SayDelegate(string name);
  
  class Program
  {
    public void AddNums(int a, int b)
    {
      Console.WriteLine(a+b);
    }
    public static string SayHello(string name)
    {
      return "Hello " + name;
    }
    static void Main(string[] args)
    {
      Program p = new Program();
      //Your method is a non-static method, and right now you are creating an instance of a delegate in a static block,
       and very important rule is - A non-static member of class can't access directly , you can access it only thru instance of a         class
      AddDelegate ad = new AddDelegate(p.AddNums);
      SayDelegate sd = new SayDelegate(SayHello); // With the class we can directly access the name of method,
                                                      outside the class with name of the class we can access
      add(1,1);
      ad.Invoke(1,1) // another way to call method
      string value = sd.Invoke("Laxman");
      //p.AddNums(1 ,1);
      //string value = Program.SayHello("Laxman");
      Console.WriteLine(value);
      Console.ReadKey();
    }
  }
}
```

------------------------
# Multicast Delegate

```C#
namespace DelegateProject
{
  public delegate void RectDelegate(double Width, double Height);
  
  class Rectangle
  {
    public void GetArea(double Width, double Height)
    {
      Console.WriteLine(Width * Height);
    }
    public void GetPerimeter(double Width, double Height)
    {
      Console.WriteLine(2 * (Width + Height));
    }

    static void Main()
    {
      Rectangle rect = new Rectangle();
      // RectDelegate obj = new RectDelegate(rect.GetArea); // another way to intialize delegate
      RectDelegate obj = rect.GetArea;
      obj  += rect.GetPerimeter;
      obj.Invoke(12.34, 56.78);

      //rect.GetArea(12.34, 56.78);
      //rect.GetPerimeter(12.34, 56.78);

      Console.ReadLine();
    }
  }
}
// Note :
// We cear full you are using a multicasting delegate all these have the same signature means the return
// and the parameter type should match with each other.  
// If these two method are value returning , it's override the first value.  


```

# Anonymous Methods:
Anonymous is also related to the delegate only. 
Without binding a named method to the delegate you can bind code block to the delegate.

```C#
namespace DelegateProject
{
  public delegate string GreetingDelegate(string name);
  class AnonymousMethods
  {
    
    static void Main()
    {
      GreetingDelegate obj = delegate(string name)
      {
        return "Hello " + name + " a very good morning!";
      }
      string str = obj.Invoke("Laxman");
      Console.WriteLine(str);
      Console.ReadLine();
    }
  }
}

```

[image]
[image]
[image]


# Fun, Action and Predicate Delegates

**Generic Delegates:**  
func  
action  
predicate  


```c#
namespace DelegateProject
{
  public delegate double Delegate1(int x, float y, double z);
  public delegate void Delegate2(int x, flaot y, double z);
  public delegate bool Delegate3(string str);
  class GenericDelegates
  {
    public static double AddNums1(int x, float y, double z)
    {
      return x + y + z;
    }

    public static void AddNums2(int x, float y, double z)
    {
      Console.WriteLine(x + y + z);
    }

    public static bool CheckLength(string str)
    {
      if(str.Length > 5)
      {
        return true;
      }
      else
      {
        return false;
      }
    }

    static void Main()
    {
      Delegate1 obj1 = AddNums1;
      double value = obj1.Invoke(100, 34.5f, 193.465);
      Console.WriteLine(value);

      Delegate2 obj2 = AddNums2;
      obj2.Invoke(100,34.5f,194.453);

      Delegate3 obj3 = CheckLength;
      obj3.Invoke("HelloWorld");
    }
  }
}
```
# To

```c#
namespace DelegateProject
{
  class GenericDelegates
  {
    public static double AddNums1(int x, float y, double z)
    {
      return x + y + z;
    }

    public static void AddNums2(int x, float y, double z)
    {
      Console.WriteLine(x + y + z);
    }

    public static bool CheckLength(string str)
    {
      if(str.Length > 5)
      {
        return true;
      }
      else
      {
        return false;
      }
    }

    static void Main()
    {
      Func<int, float, double, double> obj1 = AddNums1;
      double value = obj1.Invoke(100, 34.5f, 193.465);
      Console.WriteLine(value);

      Action<int, float, double> obj2 = AddNums2;
      obj2.Invoke(100,34.5f,194.453);

      Predicate<string> = CheckLength;
      bool statuc = obj3.Invoke("Hello /World");
      Console.WriteLine(status);
      Console.ReadLine();
    }
  }
}
```

# Lamda Expression
```c#
namespace DelegateProject
{
  class GenericDelegates
  {
    static void Main()
    {
      Func<int, float, double, double> obj1 = (x,y,z) =>
      {
         return x + y + z;
      };
      double value = obj1.Invoke(100, 34.5f, 193.465);
      Console.WriteLine(value);

      Action<int, float, double> obj2 = (x,y,z) =>
      {
         Console.WriteLine(x + y + z);
      };
      obj2.Invoke(100,34.5f,194.453);

      Predicate<string> = (str) =>
      {
          if(str.Length > 5)
            return true;
          return false;
      };
      bool status = obj3.Invoke("Hello /World");
      Console.WriteLine(status);
      Console.ReadLine();
    }
  }
}
```

# More Simplify Lamda Expression
```c#
namespace DelegateProject
{
  class GenericDelegates
  {
    static void Main()
    {
      Func<int, float, double, double> obj1 = (x,y,z) => x + y + z;
      double value = obj1.Invoke(100, 34.5f, 193.465);
      Console.WriteLine(value);

      Action<int, float, double> obj2 = (x,y,z) => Console.WriteLine(x + y + z);
      obj2.Invoke(100,34.5f,194.453);

      Predicate<string> = (str) =>
      {
          if(str.Length > 5)
            return true;
          return false;
      };
      bool status = obj3.Invoke("Hello /World");
      Console.WriteLine(status);
      Console.ReadLine();
    }
  }
}
```

# Extension Method
- This is a new feature that has been added in CSharp 3.0.
- It's a mechanism of addding new methods into an existing class or structure also without modifying the source code of the original type and in this process we don't
  require any permissions from original type and the original type doesn't require any re-compilation.
- Extension Methods are define as static but once they are bound  with any class or structure they turn into non-static.
- If an extension method is defined with the same name and signature of an existing method in the class, then extension method will not be called and the preference 
  always goes to the orignal method only.
- The first parameter of an extension method should be the name of the type to which that method has to be bound with and this parameter is not taken into consideration     while calling the extension method.
- An extension method should have one and only one binding parameter and it should be in the first place of the parameter list.

  Note : if an extension method is defined with n parameter then while calling it there will be n-1 parameters only because the binding parameter is excluded.
  
- Inheritance is a mechanism using which we can extend the functionalities of a class.

- We can't apply inheritance on sealed classes.
- If the original type is not a class and it's a structure. (We can't pre)


```C#
namespace ExtensionMethodProject
{
  class Program
  {
    public void Test1()
    {
      Console.WriteLine("Method 1")'
    }

    public void Test2()
    {
      Console.WriteLine("Method 2")'
    }

    static void Main(string[] args)
    {
      Program p = new Program();
      p.Test1(); p.Test2();
      Console.ReadLine();
    }
  }
}
```


```C#
namespace ExtensionMethodProject
{
  static class StatClass
  {
    public static void Test3(this Program P, int i)
    {
      Console.WriteLine("Method 3 : " + i);
    }
    Public static long Factorial(this Int32 x)
    {
      if(x == 1)
        return 1;
      if(x == 2)
        return 2;

      return x * Factorial(x-1);
    }

    public static string ToProper(this String oldstr)
    {
      if(oldstr.Trim().Length > 0)
      {
        string Newstr = null;
        oldstr = oldstr.ToLower();
        string[] sarr = oldstr.Split(' ');
        foreach(string str in sarr)
        {
          char[] carr = str.ToCharArray();
          carr[0] = carr[0].ToUpper();
          Newstr += " " + new string(carr);
        }
      }
    }
  }

  class TextExtMethod
  {
    static void Main()
    {
      Program p = new Program();
      p.Test1(); p.Test2();
      p.Test3(5);

      i = 5;
      double f = i.Factorial();
      Console.WriteLine("Factorial of {0} is: {1}", i, f);

      String str = "hEILo hOw aRe yoU";
      string result = str.ToProper();
      Console.WrtieLine(result);
      Console.ReadLine(); 
    }
  }
}
```
# Exceptions and Exception Handling

What is a Exception?
Whenever we are developing an application, In the application becoming across two diff type error occurs 
1. Compile time : An error occur in your program due to syntaxical mistake , forget semicolon, culry braces
2. Runtime Error :
     - Wrong Implementation of logic
     - Wrong Input Supplied
     - Missing required resources

- IndexOutofBound Exception it is a name of a class that come into picture when you go beyond the size of an array to abnormally terminate the program
- DivideByZeroException
- OverflowException : Value excedding size limit you will get this error
- Format Exception

Exception (Parent class):  Logic for abnormal termination
          - Contain a readonly property to display an error message which is declared as virtual Property "Message"
          "all the child class overriden the 'Message' property"
    - Two child are define under exception class
      - Application Exception : non-Factal Error : These are basically we can perform these type of action, but we don't want. These exception cause by programmer will do.
      - System Exception :  Factal Error -> These type of action should never be perform so, system will never allow to be performed. These exception cause by CLR.
        -> Format Exception
        -> IndexoutOfBound Exception
        -> Arithetic Exception
            -> DivideByZero Exception
            -> Overflow Exception
       
Exception Handling:
1. Abnormal termination stops so that statements that are not related with the errors can be executed
2. We can display user friendly errors msgs to the end users so that we can describe about the error.
3. We can perform corrective action to resolve the problems that may come  into picture due to the error.

```C#
namespace std
class Ex
{
  try
  {
      //Stmt's Which will cause runtime errors
     //Stmt's Which doesn't require execution when the runtime error occured.
  }
  catch(DivideByZeroException ex1)
  {
      //Stmt's which should execute only when there is a runtime error.
  }
  catch(FormatException ex2)
  {
    Console.WriteLine("Input must be numeric");
  }
  catch(Exception ex)
  {
    Console.WriteLine(ex.Message);
  }
  finally
  {
    // Exception will execute, Exception will not occure -> excute ; If any return method then also execute.
  
  }
}
```

```C#

class A
{
 try
  {
    // Open a file on HD
    // Write into the file
  }
  catch(Exception ex)
  {
    
  }
  finally
  {
    //Close file
  }
}
```

[image]


-----------------
# MultiThreading
----------------

Multitasking : Windows operating system is a multitasking operating system. How all these application run at time.. Operating system to execute all this perticular program internally will make use of process. so what is process?

Under this Operating system we have a process and this running our application, under the process an application run and to run the code inside the application ,process will use a concept knows thread. What is thread? Thread is a light weight process. In a simple word.. A thread is a unit which execute the code under a application.

Operating System:
 - Process
   - Thread
     
Every application has logic some logic in it and to execute that logic this thread come into picture. and this thread will be reponsible to executing the logic inside your application.

- Every application by default contains one thread to execute the program and that is known as Main Thread, so every program is by default single threaded model.

Drawback of Single Thread Application / Model


Multi-Threading:
 - Process
 - - Multiple Threads

  - A process can contain more than one thread in it to execute.
  - Each Thread are trying to perform different action.
  - Advantage : The execution take place simultaneously. When their are multiple thread to run in a program what will happen is op is going to allocate some time period for each thread to execute. Mean it will share the time b/w each thread to execute. How much time? That was not in our control. Operation system will take care.
    suppose there are thread to execute, so the operating system is going share the time b/w each thread and based on the time sharing all thread are going to execute for you equally.


**What is Context switching?**  
Whenever you are trying to use multiple thread in your code what will happen operating system will be sharing the time between each and every thread and the control will be transferred between the threads and basically that is called as a context of switching that is going to happen now when the context switiching is not in our control that is done by operating system so it threaded accessing a resource before it completes suppose if the context of switching is performed what is going to happen you know at the same time second thread also will try to access the same resource.  

```C#
using System;
using System.Threading;

class TheadDemo
{

static void Test1()
{
  for(int i = 1; i <= 50; i++)
   {
	Console.WriteLine("Test1");
   } 
}

static void Test2()
{
  for(int i = 1; i <= 50; i++)
   {
	Console.WriteLine("Test2");

	if(i == 20)
	{
	Console.WriteLine("Test2 Method going to sleep");
	  Thread.Sleep(10000);
         Console.WriteLine("Test2 Method woke up");
	}
   } 
 
}

static void Test3()
{
  for(int i = 1; i <= 50; i++)
   {
	Console.WriteLine("Test3");
   } 
}

static void Main()
{
  Console.WriteLine("Main Started");
  Thread t = Thread.CurrentThread;
  t.Name = "Main Thread Name";
  Thread t1 = new Thread(Test1);
  Thread t2 = new Thread(Test2);
  Thread t3 = new Thread(Test3);

  t1.Start();
  t2.Start();
  t3.Start();
  Console.WriteLine("Current ThreadName {0}", t.Name);
  Console.WriteLine("Main Exits");
}

}
//Note : 4 Thread we have  1 Main thread and 3 Child thread.
```

# The Constructor of Thread class

The Four constructors we have in our thread class.
1. ParameterizedThreadStart -> start : Initializes a new instance of the thread class, specifying a delegate that allows an object to be
2. ThreadStart -> start : A ThreadStart delegate that represents the methods to be invoked when this thread begin executing.


# ThreadStart
```C#
using System;
using System.Threading;

namespace std
{
 class ThreadStartDemo
 {
   static void Test1()
   {
    for(int i = 0; i < 50; i++)
    {
	    Console.WriteLine("Test: " + i);
    }
   }
   static void Main()
   {
     ThreadStart obj = new ThreadStart(Test1);
     Thread t1 = new Thread(obj);
     t1.Start();
   }
 }
}
// Note: When you directly pass a method name to Thead class , internally it will create the instance of the Delegate called as a ThreadStart and pass it as a parameter it's done by a framework or CLR for us.

ThreadStart obj = new ThreadStart(Test1);
Thread t = new Thread(obj);
        or
Thread t = new Thread(Test1);
// Instantiation of a delegate is process of binding the method with the delegate; This can done by many ways

//Another way
TheadStart obj = Test1;
Thread t = new Thread(obj);

// anonymous
ThreadStart obj = delegate() { Test1(); };
Thread t = new Thread(obj);

// anonymous - lamda expression
TheadStart obj = () => Test1();
Thead t = new Thead(obj);

// Either you expilictly perform it.. or you don't perform it.. then the CLR is going to perform it on behalf of you.
// Option 1 : You can Peform it
// Option 2: You directly pass the name of the method CLR will perform it.
```

# ParameterizedThreadStart

Note : ParameterizedThreadStart Delagate **object** as a parameter

```C#
using System;
using System.Threading;

namespace std
{
 class ThreadStartDemo
 {
   static void Test1(object j)
   {
    int k = Convert.ToInt32(j);
    for(int i = 0; i < k; i++)
    {
	Console.WriteLine("Test: " + i);
    }
   }
   static void Main()
   {
     ParameterizedThreadStart obj = new ParameterizedThreadStart(Test1);
     Thread t1 = new Thread(obj);
     t1.Start(10);
   }
 }

}
```
# Thead Join

Main Thread is not allow to get out the program in Middle.  
If you want the Main Thread to wait until all the thread are completing there work. What you required to do is Join.  
Now untill all the child threads are finishing/completing there jobs Main thread cannot get way from program/ Main thread will not exit.  
Main thread cannot exits from program untill all the child thread are finishing there jobs.
or
untill all the other thread are exiting from the program main thread is not allowed to exit from the program.
```c#

using System;
using System.Threading;
namespace std
{
  class ThreadJoinDemo
  {
    static void Test1()
    {
      Console.WriteLine("Thread 1 Starting");
      for(int i = 0; i < 50; i ++)
      {
        Console.WriteLine("Test1");
      }
      Console.WriteLine("Thread 1 Existing");
    }

    static void Test2()
    {
      Console.WriteLine("Thread 2 Starting");
      for(int i = 0; i < 50; i ++)
      {
        Console.WriteLine("Test2");
      }
      Console.WriteLine("Thread 2 Existing");
    }

    static void Test3()
    {
      Console.WriteLine("Thread 3 Starting");
      for(int i = 0; i < 50; i ++)
      {
        Console.WriteLine("Test3");
      }
      Console.WriteLine("Thread 3 Existing");
    }
  

   static void Main()
   {
     Console.WriteLine("Main Thead Starting");
     Thread t1 = new Thread(Test1);
     Thread t2 = new Thread(Test2);
     Thread t3 = new Thread(Test3);
     
     t1.Start(); t2.Start(); t3.Start();
     t1.Join(300); t2.Join(); t3.Join();
     Console.WriteLine("Main Thead Existing");
   }
}
	
}
```

# Lock

```C#
using System;
using System.Threading;
namespace std
{
 class ThreadLock
 {
   void Test()
   {
     lock(this)
     {    
	Console.Write("Hello, I'm going ");
        Thread.Sleep(5000);
     }
     Console.WriteLine("to Mars");
   }
 
  static void Main()
  {
    ThreadLock t = new ThreadLock();
    Thread t1 = new Thread(t.Test);
    Thread t2 = new Thread(t.Test);
    Thread t3 = new Thread(t.Test);
    t2.Priority = ThreadPriority.Highest
    t1.Start(); t2.Start(); t3.Start();
  }
 }
}

// Hello, I'm going to Mars
// Hello, I'm going to Mars
// Hello, I'm going to Mars

// First Thread execute than immediately that second thread will start the execution but it cannot access this code by means because the code is put in a lock only
// one thread is allowed to enter into the code into this block multiple thread cannot access this now How many threads can access only one thread and one thread went inside and was sleeping days and until it finishes and comes out the second one cannot access the things now so waits for 5 sec and at the same time third one also start but all are waiting outside the block cannot enter inside just like a telephone booth if I just see a telephone if one person enter into your telephone booth the other person coming over there has to stand outside the person inside the telephone booth is making a call and after he comes out only second one can enter when first one is talking the second one cannot go inside and enter and interrupt him now so compulsory has to wait there until the first one finishes his jobs and comes out and once the first one completes and comes out of it then only the second one enter.
```

# Thread Priority
   - Lowest
   - Below Normal
   - Normal[d]
   - Above Normal
   - Highest
     
- ThreadPriority Enum : Above Normal , BelowNormal, Highest, Lowest, Normal [d]

- All are going to consume the CPU resources equally you will not find any variation at all but we can change these priorities so that the thread which going to have the highest priority will consume more CPU resources then compared with the other levels so if at all you set the highest that will consume more CPU resources then comapred with other levels.

T1.Abort():

#  ThreadPerformance

```C#
using System.Threading;
using System.Diagnostics;
namespace std
{
  class ThreadPerformance
  {
   public static void IncrementCounter1()
   {
 	long Count = 0;
 	for(long i = 0; i <= 100000000; i++)
	   Count++;
 	Console.WriteLine("IncrementCounter1: " + Count);
   }
   public static void IncrementCounter2()
   {
 	long Count = 0;
 	for(long i = 0; i <= 100000000; i++)
	   Count++;
 	Console.WriteLine("IncrementCounter2: " + Count);
   }
   static void Main()
   {
     Thread t1 = new Thread(IncrementCounter1);
     Thread t2 = new Thread(IncrementCounter2);

     Stopwatch s1 = new Stopwatch();
     Stopwatch s2 = new Stopwatch();

     //Single Threaded Model
     s1.Start();
     IncrementCounter1();
     IncrementCounter2();
     s2.Stop();

    // Multithread Model
     s2.Start();
     t1.Start(); 
     t2.Start();
     s2.Stop();

     t1.Join();
     t2.Join();
     
     Console.WriteLine("Time taken to complete the work in single threaded model: " + s1.ElapsedMilliseconds);
     Console.WriteLine("Time taken to complete the work in multi threaded model: " + s2.ElapsedMilliseconds);
     Console.ReadLine();
   }
  }
}
```

# Collections in C#

## Collections

- Dynamic Array

What are these collections see, first thing what the collection means the first important point to understand it's a dynamic Array. What is this Dynamic Array.
if you just came across the Arrays in any of the language like C or C++ or in C-sharp language you'll understand about this Array are fixed length What's it once an array is declared we can never change the size of an array 

int[] arr = new int[10];

suppose, if you want to increase the size of array you have two option
1. you required to manually create a new array and to copy the values

int[] arr = new int[15];

2. Array class so in the System namespace there is a class called array this array class provides as a method called as Resize. By calling this resize method also
   we can resize an array so it is possible to resize by calling the resize method open but remember even through there is a method called resize to research an array
   what is does internally it will destory the old array and it creates a new array.

Array.Resize();

```C#
namespace std
{
  class Program
  {
    int[] arr = new arr[10];
    Array.Resize(ref arr, 15);
  }
}
```
   
Drawback of Array
1. Increasing the size
2. You can never insert value at middle of the Array / Inserting values into the middle.
3. Deleting or removing values from the middle


1. Auto Resizing ( The size of your array automatically increment whenever we keep adding new values to it.)
2. It is possible to insert the values in middle of the collections
3. Possible delete or remove the values in middle of the collections

The Collection Which are introduced in the 1.0 are known as 
Non-Generic Collections: 
System.Collections - Stack, Queue, LinkedList, SortedList, ArrayList, Hashtable

Difference between an Array and ArrayList:

Fixed Length 				Variable Length
Not Possible to insert items		We can insert items into the middle
Not Possible to delete items		We can delete items from the middle

```C#
using System;
using System.Collections;
namespace std
{
  class Program
  {
    static void Main(string[] args)
    {
      ArrayList al = new ArrayList();  // ArrayList al = new ArrayList(10);  you can set inital Capacity
      Console.WriteLine(al.Capacity);
      al.Add(100);
      Console.WriteLine(al.Capacity);
      al.Add(100), al.Add(200), al.Add(300);
      Console.WriteLine(al.Capacity);
      al.Add(500);
      Console.WriteLine(al.Capacity);

      foreach(object obj in al)
      {
        Console.Write(obj + "  ");
      }
      Console.WriteLine();
      a.Insert(3, 350);

      foreach(object obj in al)
      {
        Console.Write(obj + "  ");
      }
      Console.WriteLine();

      al.Remove(200);  // remove through values
      al.ReamoveAt(1); // or you can remove by index position also
      Console.ReadLine();
    }
  }
}

// output
0
4
4
8
100 200 300 400 500
100 200 300 350 400 500
```

Diff b/w Array and Collection
1. Array are fixed length but Collections are variables length
2. Array of an never can be increase if you want to increase the size of an Array, internally a new Array gets created and values are copy into the new array.
The Size of the Collection grow automatically as you keep adding new into it. The collection will grow so that what auto sizing.
3. We can never remove item from an array but we can remove an item from an collection.
4. We can never insert item into an array but we can insert an items into a collection.

**Both are going to store the value in same style in the index pattern.**

Hashtables: Key/Values Combination; key is User Define value

Array and ArrayList : Key/Value Combination; Key are predefine

"Eid", 1010
"Ename","Scott"
"Job","Manager"
"Salary",25000.00
"Mgrid", 1002
"Phone",234893393
"Email",scott@gmail.com
"Department","Sales"
"Location","Mumbai"
"Age", 30

```C#
using System;
using System.Collection;

namespace std
{
  class HashCollection
  {
   static void Main()
   {
     Hashtable ht = new Hashtable();
     ht.Add("Eid", 1010);
     ht.Add("Ename","Scott");
     ht.Add("Job","Manager");
     ht.Add("Salary",25000.00);
     ht.Add("Mgrid", 1002);
     ht.Add("Phone",234893393);
     ht.Add("Email",scott@gmail.com);
     ht.Add("Department","Sales");
     ht.Add("Location","Mumbai");
     ht.Add("Did", 30);

     Console.WriteLine("Hello".GetHashCode());
     foreach(object key in ht.Keys)
     {
        Console.WriteLine(key + ":" + ht[key]);
     }
     Console.ReadLine();
   }
  }
}

// Remember: Every Class by default contains 4 method init.- GetHashCode(), ToEqual(), GetType(), ToString()
// Hashtable Every item contain three values - Key, Value, HashCode
```
What is a problem the problem is in an application I want to store n number of integer value, so what is that is n number of integer values so generally if at all I say I want to store 10 integer value what we can do we can take an Integer array in store. Array are type safe actually so we can declare an integer array the type safe but when we can use an array if you know the size I wanted to store 10 items array is okay I want to store 20 items array is Okay but If i want to store n items the N is not known the N is not known right now so in the runtime when the values are being taken out at the time we are going to identify them so when n is  not known we cannot use the array so because the problem with the arrays is arrays fixed length so they cannot increase the size if you want to increase the what the drawback is your required to create a new array and copy the old values to the new array, So overcome this particular problem we came to collections. Collection when you talk about a collection size is not requied to be specified by a collection because collection can store variable number of items it's not like a fixed length it is a variable length and the size of the collection is going grow automatically Auto resizing facility is avaiable **but not type safe**. Why they are not type safe if C for storing n number of integer values  if i take a collection while entering the value by mistake if any wrong values entered there it accepts the wrong type of values entered it accepts . I'm going enter string values it's accept , I'm going to enter integer value , bool, float it accepts whatever we enter it accepts but our requirement is purely sotring integer values so this the problem we have with the collections.

**Collection has one drawback is not type safe**

Array : Type Safe but fixed length
Collection: Auto Resizing but not Type Safe

# Generic Collection: in C# 2.0
Generic Collection is also a collection. It's a type safe and Auto Resizing.

List<T>

public class Customer
{
public int Custid { get; set;}
public string Name { get; set;}
public double Balance {get; set;}
}

List<int> li = new List<int>();
List<string> ls = new List<string>();
List<Customer> customers = new List<Customer>();

Whatever collection classes we have in System.Collection namespace for all those classes Microsoft has provided a replacement in System.Collection.Generic namespace.

List<T> - Strongly Typed 
```C#
namespace std
{
 class Program
 {
  static void Main()
  {
   List<int> li = new List<int>();
   li.Add(10); li.Add(20); li.Add(30); li.Add(40);

   li.insert(3,35);
   foreach(int i in li)
   {                                                           
     Console.Write( i + "  ");
   }
   Console.ReadLine();
  }
 }
}
```
ArrayList  
In ArrayList is capable to store any type values init. The reason is Add method is going to take Object parameter. you can pass anything so it's not type safe.

```C#

namespace std
{
 class Generics
 {
  // if we use object, Internal compailer have to perform boxing and unboxing.
   public bool Compare<T>(T a , T b)
   {
	if (a.Equal(b))
           return true;
        return false;
   }
   static void Main()
   {
     Generic obj = new Generic();
     bool result = obj.Compare<float>(10.5f,10); //angular braces
     Console.WriteLine(result);
     Console.ReadLine();
   }
 }
}

```

```C#

namespace std
{
 class Generics2
 {
  // if we use object, Internal compailer have to perform boxing and unboxing.
   public bool Add<T>(T a , T b)
   {
	dynamic d1 = a;
        dynamic d2 = b;
	Console.WriteLine(d1 + d2)
   }

   public bool Sub<T>(T a , T b)
   {
	dynamic d1 = a;
        dynamic d2 = b;
	Console.WriteLine(d1 - d2)
   }

   public bool Mul<T>(T a , T b)
   {
	dynamic d1 = a;
        dynamic d2 = b;
	Console.WriteLine(d1 * d2)
   }

   public bool Div<T>(T a , T b)
   {
	dynamic d1 = a;
        dynamic d2 = b;
	Console.WriteLine(d1 / d2)
   }

   static void Main()
   {
     Generic obj = new Generic();
     obj.Add<int>(10,10);
     obj.Mul<int>(10,20);
     obj.Sub<int>(10,20);
     obj.Div<int>(10,40);
     Console.ReadLine();
   }
 }
}

```

// Pass Type directly to the class

```C#

namespace std
{
 class Generics2<T>
 {
  // if we use object, Internal compailer have to perform boxing and unboxing.
   public bool Add(T a , T b)
   {
	dynamic d1 = a;
        dynamic d2 = b;
	Console.WriteLine(d1 + d2)
   }

   public bool Sub(T a , T b)
   {
	dynamic d1 = a;
        dynamic d2 = b;
	Console.WriteLine(d1 - d2)
   }

   public bool Mul(T a , T b)
   {
	dynamic d1 = a;
        dynamic d2 = b;
	Console.WriteLine(d1 * d2)
   }

   public bool Div(T a , T b)
   {
	dynamic d1 = a;
        dynamic d2 = b;
	Console.WriteLine(d1 / d2)
   }

   static void Main()
   {
     Generic<int> obj = new Generic<int>();
     obj.Add(10,10);
     obj.Mul(10,20);
     obj.Sub(10,20);
     obj.Div(10,40);
     Console.ReadLine();
   }
 }
}

```
HashTable : Store a value in key value combination and List  

Comming to Generic collection hashtable was repalce as Dictionary  

List<T> : In List key are pre-define
Dictionary<TKey, TValue> 


```c#

namespace std
{
  class DictionaryCollection
  {
    static void Main()
    {
      Dictionary<string, object> dt = new Dictionary<string, Object>();
      dt.Add("EId", 1010);
      dt.Add("Ename", "Laxman");
      dt.Add("Job", "Manager");
      dt.Add("Salary", 24000);
      dt.Add("Email", "adbc@gmail.com");
      dt.Add("Phone", "23728282");

      foreach(string key in  dt.Keys)
         Console.WriteLine(key + ": " + dt[key]);
    }
  }
}

// Dictionary will store the value in sequence / Dicionary will print all the values in sequence
// Hashtable didn't store the value in sequence
```

**In case of a generic collection the type of values we want to store under the collections need not be pre-define typed only like int, float, char, string, bool etc. but it can also be some user-defined type also.**

Customer:\
 - CustId
 - Name
 - City
 - Balance

```C#

namespace std
{
  public class Customer
  {
   public int Custid { get; set; }
   public string Name { get; set; }
   public string City { get; set; }
   public double Balance { get; set; }
  }

  class TestCustomer
  {
    static void Main()
    {
      List<Customer> Customers = new List<Customer>();
      Customer c1 = new Customer { Custid = 101, Name = "Laxman", City = "Hyderabad", Balance = 25000.00};
      Customer c2 = new Customer { Custid = 102, Name = "Dev", City = "Kolkalta", Balance = 25000.00};
      Customer c3 = new Customer { Custid = 103, Name = "Sohit", City = "Dubai", Balance = 25000.00};
      Customer c4 = new Customer { Custid = 104, Name = "Sanoop", City = "Dehradun", Balance = 25000.00};
      Customer.Add(c1); Customer.Add(c2); Customer.Add(c3); Customer.Add(c4);

      foreach(Customer obj in Customers)
      {
        Console.WriteLine(obj.Custid + " " + obj.Name + " " + obj.City + " " + obj.Balance);
      }
      Console.ReadLine();
    }
  }
}

```
# IComparable & IComparer

And Comparison Delegate  

```C#

namespace std
{
  public class Student : IComparable<Student>
  {
   public int Sid { get; set; }
   public string Name { get; set; }
   public int Class { get; set; }
   public float Marks { get; set; }

   public int CompareTo(Customer other)
   {
     if (this.Sid > other.Sid)
         return 1;
     else if (this.Sid < other.Sid)
         return -1;
     else
         return 0;
   }
  }
  // suppose we don't have a access of student class or student is pre-define classs or some other person has implemented.. to overcome this problem take a new class and implment a interface IComparer; 
  Class CompareStudents : IComparer<Student>
  {
    public int CompareTo(Student x , Student y)
    {
      if (x.Marks > y.Marks)
        return 1;
      else if (x.Marks < y.Marks)
        return -1;
      else
        return 0;
    }
  }
  class TestCustomer
  {
    public static int CompareNames(Student s1, Student s2)
    {
      S1.Name.CompareTo(S2.Name);
    }
    static void Main()
    {
      Student s1 = new Student { Sid = 101, Name = "Laxman", Class = 10, Marks = 372.00f};
      Student s2 = new Student { Sid = 102, Name = "Dev", Class = 10, Marks = 500.00f};
      Student s3 = new Student { Sid = 103, Name = "Sohit", Class = 10, Marks = 659.00f};
      Student s4 = new Student { Sid = 104, Name = "Sanoop", Class = 10, Marks = 700.00f};

      List<Student> Students = new List<Student>() {s1, s2, s3, s4, s5, s6};
      CompareStudents obj = new CompareStudents();
      Students.Sort(obj);
      //Students.Sort();
      //Student.Sort(1,5, obj);

      //Comparison<Student> obj = new Comparison<Student>(CompareNames);
      //Student.Sort(obj);

      //Student.Sort(CompareNames);
      //Student.Sort(delegate(Student S1, Student S2) { return S1.Name.CompareTo(S2.Name); }); //anonomus method
      Student.Sort((S1,S2) => S1.Name.CompareTo(S2.Name)); // lamda experssion
      Student.Sort( new Comparison<Student>(CompareNames));
      
      foreach(Student obj in Students)
      {
        Console.WriteLine(obj.Sid + " " + obj.Name + " " + obj.Class + " " + obj.Marks);
      }
      
    }
  }
}

```
[image] error


# IEnumerable Interface

IEnumerable Interface is parent of all the collection

- IEnumerable
  - ICollection
     - IList
     - IDictionary
       Hashtable, Dictionary

Foreach work because Every Collection inherit from Interface called IEnumerable. This IEnumerable Internal contains a method GetEnumerator() and that GetEnumerator method Implemented by all the collection class and that GetEnumerator method is used by the foreach for Printing. 

[Image]

```C#
namespace std
{
 class class Employee
 {
   public int Id { get; set; }
   public string Name { get; set; }
   public string Job { get; set; }
   public double Salary { get; set; }
 }

 public class Organization
 {
   List<Employee> Employees = new List<Employee>();
   public void Add(Employee Emp)
   {
     Employees.Add(Emp);
   }
 }
 class TestEmployee
 {
  static void Main()
  {
    List<Employee> Employees = new List<Employee>();
    Employees.Add(new Employee {Id = 101, Name = "Raju", Job = "Manager", Salary = 25000.00});
    Employees.Add(new Employee {Id = 101, Name = "Venkart", Job = "Manager", Salary = 25000.00});
    Employees.Add(new Employee {Id = 101, Name = "Sohit", Job = "HR", Salary = 25000.00});
    Employees.Add(new Employee {Id = 101, Name = "Dev", Job = "Developer", Salary = 25000.00});
    Employees.Add(new Employee {Id = 101, Name = "Piyush", Job = "Andriod", Salary = 25000.00});

    foreach(Employee emp in Employees)
    {
       Console.WriteLine(Emp.Id + " " + Emp.Name + " " + Emp.Job + " " + Emp.Salary);
    }
    Console.ReadLine();
  }
 }
}
```

```C#
using System.Collection;
using System.Collection.Generic;

namespace std
{
 class class Employee
 {
   public int Id { get; set; }
   public string Name { get; set; }
   public string Job { get; set; }
   public double Salary { get; set; }
 }

 public class Organization : IEnumerable
 {
   List<Employee> Employees = new List<Employee>();
   public void Add(Employee Emp)
   {
     Employees.Add(Emp);
   }
   public int Count
   {
     get { return Employees.Count; }
   }
   public Employee this[int index]
   {
     get { return Employees[index] }
   }
   public IEnumerator GetEnumerator()
   {
     //return Employees.GetEnumerator();
      return new OrganizationEnumerator(this);
   }
 }

 public class OrganizationEnumerator : IEnumerator
 {
    Organization OrgColl;
    int CurrentIndex;
    Employee CurrentEmployee;

    public OrganizationEnumerator(Organization org)
    {
      OrgColl = org;
      CurrentIndex = -1;
    }
    public object Current
    {
       get {}
    }

    public bool MoveNext()
    {
      if (++CurrentIndex >= OrgColl.Count )
         return false;
      else
         CurrentEmployee = OrgColl[CurrentIndex];
      return true;
    }

    public void Reset()
    {
       throw new NotImplementedException();
    }
 }
 class TestEmployee
 {
  static void Main()
  {
    Organization Employees = new Organization();
    Employees.Add(new Employee {Id = 101, Name = "Raju", Job = "Manager", Salary = 25000.00});
    Employees.Add(new Employee {Id = 101, Name = "Venkart", Job = "Manager", Salary = 25000.00});
    Employees.Add(new Employee {Id = 101, Name = "Sohit", Job = "HR", Salary = 25000.00});
    Employees.Add(new Employee {Id = 101, Name = "Dev", Job = "Developer", Salary = 25000.00});
    Employees.Add(new Employee {Id = 101, Name = "Piyush", Job = "Andriod", Salary = 25000.00});

    foreach(Employee emp in Employees)
    {
       Console.WriteLine(Emp.Id + " " + Emp.Name + " " + Emp.Job + " " + Emp.Salary);
    }
    Console.ReadLine();
  }
 }
}

[image]
```
![image](https://github.com/Laxmannegi/C-I/assets/15025418/fbd6ee46-fed4-4d94-81de-bf692f5c1745)
![image](https://github.com/Laxmannegi/C-I/assets/15025418/463d09f4-c97b-48ce-8e6e-3d36126c4938)
![image](https://github.com/Laxmannegi/C-I/assets/15025418/7f349e64-0923-4540-bc09-cf871ee89827)

 > [!NOTE]
> Highlights information that users should take into account, even when skimming.

> [!IMPORTANT]
> Crucial information necessary for users to succeed.

> [!WARNING]
> Critical content demanding immediate user attention due to potential risks.


```Text
1. Can we overload staic method or Override static method  
2. What is private constructor?  
3. What is the advantge of call a method by delegate?  
4. how authentication work?  
5. way to handle exception in .net core and angular?  
6. Difference between Array and ArrayList?  
7. Temp Table use case  
8. CTE Table use case  
9. How to handle exeception in SP
10. how authentication work?
11. Way to handle exception in .net core and angular?
12. Difference b/w var and Dynamic //  Dynamic introduce in .net 4.0
13. Difference b/w Dictionary and hashtable
14. Difference b/w ArrayList and List
14. What is System.Collection and System.Collection.Generic
15. Reverse String
16. Difference b/w record and class
17. What is ActionResult , IActionResult, Task<IActionResult>
18. String comparison: InvariantCultureIgnoreCase vs OrdinalIgnoreCase? -> StringComparison.InvariantCultureIgnoreCase
19. ObservableCollection

How we can connect open API to another API
-- through reffid

```

In last video I was just being demonstrating about delegate 
