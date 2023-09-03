# C- Interview

**Visual Studio .Net:**
It's an IDE provide by microsoft for developing .net application.  
It is used for developing console, Windows, web application  

**Folder** : Folder is logical container in Operating System.  

**Constructor:**
1. It's a special method present under a class responsible for initializing the variables of that class.
2. The name of a constructor method is exactly the same name of the class in which it was present and more over it's a non-value returning method.
3. Each and every class required this constructor if we want to create the intance of the that class.

class Test
{
  int i;
}

Test obj = new Test(); // Valid

4. It's the reponsibility of a programmer to define a constructor under his class and if he fails to do so, on behalf of the programmer an **implicit constructor** gets defined in that class by the compiler.

Class Test{
  int i; string s; bool b;

  public Test(){
  i = 9;   // Initializing the variable
  s = null;
  b = false;
  }
}

5. Implicitly defined constructors are also know as default constructors.
6. Implicitly defined constructors are parameters less and these constructors are also know as default constructors.
7. Implicitly defined constructors are public.
8. We can also define a constructors under the class if we defined it we can call it as explicit constructor
   and explicit constructor can be parameter less or parameterized also.

   [<modifiers>] <name>( [<parameter list>] )
   {
      -Stmts
   }

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

- If a Constructor method doesn't take any parameters then we call that as default or parameter less. These Constructor can be defined by the programmer expilicty or else it will be default implicitly provided there is no explicit constructor under the class.

**Parameterized  Constructor:**
If a constructor method is defined with any parameters we call that as parameterized constructor and these constructor can be by the programmers only but never can be defined implicitly.


**Copy Constructor :**
If we want to create multiple instances with the same values then we use these copy constructors, in a copy constructor   the constructor takes the same class as a parameter to it.

let me demostrate it.

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

**Static Constructor:**
If a constructor is explicitly declared by using the static modifier we call that as Static Constructor. All the constructors we have defined till now are non-static or instance constructors.

class Test
{
  static Test()  //Static constructor defined explicitly
  {
  }
  public Test()  //Implicit default constructor
  {
  }
}

1. If a class contains any static variables then only implicit static contructure will be present
   or else we need to define them explicit whereas non-static constructor will be implicitly defined as in every class 
   (except static class) provided we did not define them explicitly.
2. Static constructor are responsible in initializing static variables and these construtors are never called explicitly 
   they are implicilty called and more over these constructor are first to execute under any class.
3. Static constructor can't be parameterized so overloading static constructor are not possible.

**Why are constructure are need in our class?**

- Every class requires a constructor to be present init if we want to create an intance of that class.
- Every class contain an implicit constructor if not defined explicitly and with the help of implicit constructor instance 
  of class can be created.
  
**What is the need of defining a constructor explicitly again?**
  Implicit constructors of a class will initialize variables of a class with the same value even if we create multiple 
  instance of that class.

  - If we define constructors explicitly with parameters then we get a chance of initializing the fields or variables of the class with a new value every time we are going 
    to create instance of that class.
  - Whenever we define a class first identify whether if the class variables requires some values to execute and if they are required then define a constructor explicitly 
    and pass values thru that constructor, so that every time the instance of class is created we get a chance of passing new values.

Note : Generally every class requires some values for execution and the values that are required for a class to execute are        always send to that class by using the constructor only. 


**Static Constructors vs Non-Static Constructors:**
- If a constructor is explicitly declared by using a static modifier we call that constructor as static constructor whereas 
  rest of other are non-static constructors only.

- Constructors are responsile for initializing fields/variables of a class, static fields are initialized by static 
  constructors and non-static fields are initialized by non-static constructors.
  
- Static Constructors are implicitly called whereas non-static constructors must be explicitly(We are create instance of a class) called.
- Static constructors executes immediately once the execution of a class starts and more over it's the first block of code to run under a class whereas non-static 
  constructor executes only after create the instance of class as well as each and
  every time the instance of class is created.
- In the life cycle of a class static constructor executes one and only one time whereas non-static constructor executes for
  zero of no instances are created and "n" times if "n" instances are created.
- Non-static constructors can be parameterized but static constructor cannot have any parameter because static constructors   are impliclity called and more over it's the 
  first block of code to run under the class.
- Non-static constructors can be overloaded where as static constructor can't be overloaded.
  
- Every class constains an implicit constructor if not defined explicilty and those implicit constructor are defined based on the following criteria:
  - Every class except a static class contains an impicit non-static constructor if not defined with an explicit   
    constructor.
  - Static constructors are implicitly defined only if that class contains any static fields or else that constructor will not be present at all.
 
 ---------------------------------------------------------------------------------------------------------------------------

Variable of a class
Instance of a class
Reference of a class

Variable of a class:  a copy of the class that is not initialized.

Instance of a class: a copy of the class that is initialized by using the new keyword.

Class: It's is user-defined type / data type. / Class is collection object
If you want to consume of a class, we need to create a copy of it.

int = 100; // int is only a buleprint for your particular data, it doesn't have any memory location.
int i = 100;

string = "Hello";
string s = "Hello";

Instance of a class only when we use new keyword.

First f = new First(); //f is instance of class
    or
First f;               //f is variable of class
f = new First();       //f is instance of class

Memory allocation is done only  after creating instance , untill and unless you create an instance memory allocation is not done.  
Every instance unique itself.  
The changes made on one instance never relfect on another instance.  

**Reference of a class:**
References is copy of the class that is initialized by using an existing instance and references of class will not have any memory allocation they will be sharing the same
memory of the instance that assigned for initializing the variable.

- Reference of class can be called as a pointer to the instance and every modification we perform on the members using instance reflects when access those members thru refernce and vice-versa.

First f1 = new First(); // f1 is instance of class
First f2 = f1; // f2 is reference of the class;  f2 is pointer to f1; f2 doesn't have any separate memory location. f1 and f2 will be consuming the same memory in this context.


