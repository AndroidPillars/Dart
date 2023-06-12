# Topics

| S.No | Content |
| --------	 | ------------ |
| 1 | [Key - Points](DartInDetail.md#key---points) |
| 2 | [Dart](DartInDetail.md#dart) |
| 3 | [Dart - Entry Point](DartInDetail.md#dart---entry-point) |  
| 4 | [Comments](DartInDetail.md#Comments) |
| 5 | [Variables](DartInDetail.md#variables) |
| 6 | [Data Types](DartInDetail.md#data-types) |  
| 7 | [Const vs Final](DartInDetail.md#const-vs-final) |  
| 8 | [String Interpolation, concatenation and Type inference](DartInDetail.md#string-interpolation-concatenation-and-type-inference) |  
| 9 | [Type Conversion](DartInDetail.md#type-conversion) |  
| 10 | [Operators](DartInDetail.md#operators) |  
| 11 | [Ternary Operator](DartInDetail.md#ternary-operator) |  
| 12 | [Type Test Operator](DartInDetail.md#type-test-operator) |  
| 13 | [Null Aware Operators & Null Safety](DartInDetail.md#null-aware-operators--null-safety) |  
| 14 | [Conditionals - IF/ELSE](DartInDetail.md#conditionals---ifelse) |  
| 15 | [Enum(Enumeration) using Switch Case](DartInDetail.md#enumenumeration-using-switch-case) |  

## Key - Points

- Current Dart Version as on 10 May 2023 -> Dart 3.0 
- Editor -> Android Studio, Visual Studio Code and DartPad.

:arrow_up: [__Back to Top__](DartInDetail.md#topics)

## Dart

- It is a open source and powerful language very similar to Oops.
- It is a Statically typed programming language (i.e.) If we define a variable as String, We cannot assign other Values like Int, Bool, etc.. 
- Dart also supports a dynamic variable that is checked during the runtime.
- It is also a compiled programming Language (i.e.) It supports Two Types of Compilation -> AOT(Ahead of Time during Development time) and JIT(Just in Time during Production Mode)  

:arrow_up: [__Back to Top__](DartInDetail.md#topics)

## Dart - Entry Point

```ruby
// TODO main() is the Entry point of our Application.
// TODO void means it will return nothing and void is Optional (i.e.) We can also remove void.
void main() {
  // TODO We can assign a String either by using single or double quotes.
  print('Hello World');
  print("Hello World");
  
  // TODO For Using Apostrophe and new line we have to do as of below.
  print("Github - It's is a Awesome Place to Learn \n the New Technology");
  print('Github - It\'s is a Awesome Place to Learn \n the New Technology'); 
  
  // TODO Using Raw String - Special Character will not be Evaluated.
  var s = r'Github is a Awesome Place to Learn \n the New Technology';
  print(s);
  
  // TODO We can also print the Multi-line String as of below.
  print('''Hello
  World''');
  
  print("""Hello
  World""");
}
```  
:arrow_up: [__Back to Top__](DartInDetail.md#topics)

## Comments

- Comments are the set of statements that are ignored by the dart compiler during program execution. 
- They are used to explain the code so that you or other people can understand it easily.
- Types -> In-line Comment, Block Comment and Documentation.

__Example__

```ruby
void main() {
  // TODO - This is the In-line Comment Line which will be used for Single Line Comment.

  /*
   TODO - This is the Block Comment Line which will be used for Multiple Line Comment.
   */

  /// TODO - This is For Documentation

  print("Hello World");
}
```  
:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## Variables

- Variable is a just a value that can change, depending on conditions or on information passed to the program. 

__Example__

```ruby
void main() {
  // TODO var keyword is the Type inference.
  var myName = 'Android';

  print(myName.runtimeType);
}
```  
:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## Data Types

- Dart the following Data Types.
- Numbers
  - int(1,2,3) - It Supports only int.
  - double(1.0,2.0) - It Supports only double.
  - num(1,1.0,2,2.0) - It Supports both int and double.
- Srting
- bool
- var - DataType will create implicitly based on the values we provide.
- List (or Arrays)
- dynamic - For Assigning Mixed Data Type.
- map - For defining a vlaues in Key Value pairs.
- Set, runes

__Need to Know,__

- Dart is a Object Oriented Programming Language and So everything is object in here even the null type.

__Example__

```ruby
void main() {
  // TODO Explicitly defining the datatype - String
  String a = 'Flutter';
  print(a);

  // TODO Implicitly defining the datatype - dynamic
  var b;
  b = 'Android';
  b = 123;
  print(b);

  // TODO Explicitly defining the datatype - dynamic
  dynamic c;
  c = 'IOS';
  c = 123;
  print(c);
}
```  
:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## Const vs Final

- Both represent immutability and read only.
- Final keyword will be used to declare run time values.
- Const keyword will be used to declare compile time values.
- Variables declared using the const keyword are implicitly final.

__Need to Know,__

- Prefer using const for constant declarations.
- Const declarations are more hot-reload friendly and allow to use const constructors if an instantiation references this declaration.

__Example 1__

```ruby
void main() {
  // TODO Using final keyword
  DateTime nowDate = DateTime.now();
  final int currYear = nowDate.year;
  print(currYear.toString());

  // TODO final keyword using late
  late final int mCurrentYear;
  mCurrentYear = nowDate.year;
  print(mCurrentYear?.toString());

  // TODO Using const keyword
  const birthday = "2023/12/25";
  print(birthday);
}
``` 

__Example 2__

```ruby
void main() {
  // TODO The Below Line defines the Object
  Car myCar = Car("Hyundai");

  // TODO Where myCar.mName is the Object Property and Car.mType is the Class Property
  print('Company is ${myCar.mName} and the Car Type is ${Car.mType}');
}

class Car {
  // TODO final keyword with in a class we can change it using the Constructor so this will be possible at runtime
  final String? mName;

  // TODO Const will not be changed at any time.
  static const String mType = "Hatchback";

  // TODO Alternative way of using Constructor
  Car(this.mName);
}
```

:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## String Interpolation, concatenation and Type inference

- __Type Inference__ which allows us to declare a variable without explicitly mentioning the data type. 
- __String Concatenation__ is used to combine Multiple Strings.
- __String Interpolation__ is a method of concatenating, formatting, and manipulating strings (i.e.) Used to replace a Variables actual value with in a String. 

__Example__

```ruby
void main() {
  // TODO var keyword is the Type inference. 
  var mStringValueOne = 'Hello';
  
   // TODO In String keyword we are explicitly defined the Data Type. 
  String mStringValueTwo = 'World';
  
  // TODO String Interpolation
  print('The Value is $mStringValueOne $mStringValueTwo');
  
  // TODO String concatenation - Combining Multiple Strings
  print('The Value is ' + mStringValueOne + ' ' + mStringValueTwo);
  print('The Values Length is ${mStringValueOne.length} + ${mStringValueTwo.length}');
  
}
```  
:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## Type Conversion

- Conversion of one Data Type to another Data Type.

__Example__

```ruby
void main() {
  // TODO Converting int to String
  int a = 10;
  print(a.toString());

  // TODO Converting String to int
  String b = '10';
  print(int.parse(b));

  // TODO Converting double to String
  double c = 10.504343;
  print(c.toStringAsFixed(2));
}
```  
:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## Operators

- Operators are used to perform mathematical and logical operations on the variables.
- The Word 'Operands' represents the data.
- The Word 'Operator' represents how the operands will be processed to produce a value.
- Types -> Arithmetic Operators, Increment and Decrement Operators, Assignment Operators, Logical Operators and Type Test Operators.

__Example_1 (Arithmetic Operators)__

```ruby
void main() {
    int a = 10;
    int b = 3;

    // TODO using Arithmetic Operator includes +, -, *, /, ~/, %, -expr

    // TODO Addition
    int c = a + b;
    // TODO Subtraction
    int d = a - b;
    // TODO Multiplication
    int e = a * b;
    // TODO Division
    double f = a / b;
    // TODO Integer Division (i.e.) For dividing two operands and give output in integer
    int g = a ~/ b;
    // TODO Modulus (i.e.) Remainder after doing the Division
    int h = a % b;
    // TODO Unary Minus (i.e.) For reversing the sign of the expression
    int i = -b;

    print(i);
}
``` 

__Example_2 (Increment and Decrement Operators or Unary Operators)__ 

```ruby
void main() {
    int a = 10;
    int b = 3;
    int c = 31;
    int d = 35;

    // TODO using Increment and Decrement Operator includes ++var, --var, var++, var--
    // TODO ++var increases the value of operands, whereas var++ returns the actual value of operands before the increment.

    // TODO Post Increment -> Increase Value By 1. var = var + 1 (i.e.) a++ -> a = a + 1;
    // TODO First it will print and then increment the Value.
    a++;
    print(a);

    // TODO Post Increment.
    b--;
    print(b);

    // TODO Pre Increment
    // TODO First it will increment the Value and then it will print.
    ++c;
    print(c);

    // TODO Pre Increment
    ++d;
    print(d);

}
```

__Example_3 (Assignment Operators)__ 

```ruby
void main() {

    // TODO using Assignment Operator includes =, +=, -=, *=, /=
    // TODO Assigning value to a Variable
    int a = 10;
    int b = 20;
    int c = 30;
    double d = 40;

    // TODO Adding a Value to a Variable -> a += 5 (i.e.) age = age + 5
    a += 5;
    print(a);

    // TODO Subtracting a Value to a Variable
    b -= 10;
    print(b);

    // TODO Multiplying a Value to a Variable
    c *= 15;
    print(c);

    // TODO Dividing a Value to a Variable
    d /= 20;
    print(d);

}
```

__Example_4 (Relational Operators)__  

```ruby
void main() {

    // TODO using Relational Operators includes ==, >, <, >=, <=, !=
    int a = 10;
    int b = 20;

    print(a == b);
    print(a > b);
    print(a < b);
    print(a >= b);
    print(a <= b);

}
```  

__Example_5 (Logical Operators)__  

```ruby
void main() {

    // TODO using Logical Operators includes &&, ||, !
    int a = 10;
    int b = 20;

    print(a == b && a > b);
    print(a > b || a < b);
    print(a > b != a < b);

}
```  

__Example_6 (Type Test Operators)__  

- We can use this in dart code to check the type or set the typecast in dart using as, is and is!.

```ruby
void main() {

    // TODO using Type Test Operators includes is, is!
    var value1 = "Dart Tutorial" as String;
    int age = 10;

    // TODO is -> Gives boolean value true if the object has a specific type
    print(value1 is String);
    // TODO is! -> Gives boolean value false if the object has a specific type
    print(age is! int);

}
```
:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## Null Aware Operators & Null Safety

- Dart provides Null Aware Operators to make us deal with nullable variables.
- If a variable is null we cannot perform an action and if we do so this may lead to null pointer exception & our application will crash during run-time.

__Example 1__ 

```ruby
void main() {
  employeeName();
}

void employeeName({String? mName}) {
  if (mName == null) {
    print('No Employee exists');
  } else {
    print('Employee Name is $mName');
  }
}
```

__Example 2 (Using Null Aware Operators)__ 

```ruby
void main() {
  // TODO ? -> If the values is not initialized it returns null during the runtime.
  String? mValue;
  print(mValue);

  // TODO late -> If the values is not initialized it throws an exception during the runtime.
  late String mValueTwo;

  // TODO ?. (Safe Navigation Operator) -> If the values is null it returns null during the runtime.
  print(mValue?.length);

  // TODO ! -> If the values is null it will throws an exception during the runtime.
  print(mValue!.length);

  // TODO ?? (Default Operator) -> If the values is null it will set the default keyword during the runtime.
  print(mValue ?? 'Default keyword');

  // TODO ??= (Fallback Assignment Operator) -> If the values is null it will set the default keyword during the runtime.
  mValue ??= 'Default keyword';
  print(mValue);

  // TODO ...? (Operational spread operator) -> If the values is null then it will not add or else it will add during the runtime.
  List<int> lowerNumber = [1, 2, 3, 4, 5];
  List<int>? upperNumbers;
  lowerNumber = [...?lowerNumber, ...?upperNumbers];
  print('The Numbers are ${lowerNumber}');
}
```  
:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## Conditions & Loops

## Conditions 

-  By using the conditions, you can control the flow of the dart program. 
-  Suppose you need to execute a specific code when a particular situation is true.
-  Types -> If Condition, If-Else Condition, If-Else-If Condition, Switch Case

__Example__

```ruby
import 'dart:math';

void main() {
    int loveScore = Random().nextInt(100) + 1;

    if (loveScore > 70) {
        print('You Love Each Other very much');
    } else if (loveScore > 50) {
        print('You Love Each Other');
    } else {
        print('You Love Each Other but have to understand');
    }
}
```
:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## Switch Case

- A Switch case is used to execute the code block based on the condition.  

__Example__

```ruby
void main() {
  const weather = "cloudy";

  switch (weather) {
    case "sunny":
      print("It's a sunny day.");
      break;
    case "cloudy":
      print("It's a cloudy day.");
      break;
    case "rainy":
      print("It's a rainy day.");
      break;
    default:
      print("No Results Found.");
      break;
  }
}
```
:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## Assert

- Dart provide a assert method to check for the error. 
- It takes conditions as an argument. 
- If the condition is true, nothing happens but incase a condition is false, it will raise an error. 

__Example__

```ruby
void main() {
    var myAge = 25;

    assert(myAge != 25);

    // TODO We can also use assert with a custom message.
    assert(myAge!=25, "My age is not 25");
}
```  

## Ternary Operator

- Ternary operator can be used to replace an if..else statement in certain situations.
- It evaluates and executes a block of code based on the condition.

__Example__

```ruby
void main() {
  var myAge = 18;

  // TODO using if,else
  if (myAge > 18) {
    print("you are eligible for Marriage");
  } else {
    print("you are not eligible for Marriage");
  }

  // TODO using Ternary Operator
  (myAge > 18)
      ? print("you are eligible for Marriage")
      : print("you are not eligible for Marriage");
}
```  
:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## Loops

- loops are used to repeat a block of code until certain conditions are not completed.
- Types -> For Loop, For-In Loop, For-Each, While Loop, DO-While Loop.

## For Loop

```ruby
void main() {
  var mList = [1, 2, 3, 4];

  // TODO Using Standard For Loop
  for (int i = 0; i < mList.length; i++) {
    print(mList[i]);
  }
}
```  

## For-In Loop

```ruby
void main() {
  var mList = [1, 2, 3, 4, 5];

  for (var n in mList) {
    print(n);
  }
}
```

## For-Each

- forEach Loop is an Higher Order Function because it takes anonther function as a parameter.

```ruby
void main() {
  var mList = [1, 2, 3, 4];

  // TODO Using Arrow Function
  mList.forEach((element) => print(element));

  // TODO Using Normal Function
  mList.forEach((element) {
    print(element);
  });
}
```

## While Loop

```ruby
void main() {
  var mList = [1, 2, 3, 4, 5];

  int i = 0;
  while (i < mList.length) {
    print(i);
    i++;
  }
}
```

## DO-While Loop

```ruby
void main() {
  var mList = [1, 2, 3, 4, 5];

  int i = 0;

  do {
    print(i);
    i++;
  } while (i < mList.length);
}
```

## Break

```ruby
void main() {
  var mList = [1, 2, 3, 4, 5];

  for (int i = 0; i < 5; i++) {
    if (i == 3) break;
    print(mList[i]);
  }
}
```

## Continue

```ruby
void main() {
  var mList = [1, 2, 3, 4, 5];

  // TODO Using Standard For Loop
  for (int i = 0; i < mList.length; i++) {
    if (i % 2 == 0) continue;
    print(mList[i]);
  }
}
```  

## Exception Handling

- The Exception Handling is a mechanism to handle the runtime errors so that normal flow of the application can be maintained.
- four keyword Types -> try, catch, finally and throw.

__Example__

```ruby
void main() {
  int a = 1;
  int b = 0;

  try {
    // TODO (~/) -> Divide, returning an integer result
    int result = a ~/ b;
    print(result.toString());

    validateAge(-1);
  } on UnsupportedError {
    print('UnsupportedError');
  } catch (ex) {
    print(ex);
  } finally {
    print('finally block executed');
  }
}

void validateAge(int age) {
  if (age < 0) {
    throw new FormatException();
  }
}
```  

## Enum(Enumeration) using Switch Case

- It is just a data type that contains some fixed set of constants which is declared using the keyword enum. 
- When we require a predefined set of values which represents some kind of data, we use enum. 

__Example__

```ruby
void main() {
  var mSelectedGender = Gender.male;

  switch (mSelectedGender) {
    case Gender.male:
      {
        print(mSelectedGender.name);
      }
      break;

    case Gender.female:
      {
        print(mSelectedGender.name);
      }
      break;

    default:
      print('No Data Found');
  }
}

enum Gender { male, female }
```  
:arrow_up: [__Back to Top__](DartInDetail.md#topics)  

## Functions

- A Function is a block of organized, reusable code that is used to perform some action.
- In Dart Programming Language, each Function is an object of Class Function.
- __Anonymous Function__ is just a Function just as its name implies it has no name.
- Parameter Types - Positional Paramter, Optional Positional Parameter, Named Parameter
- By using Positional Parameter we can't skip or interchange the Parameters.
- By using Optional Positional Parameter we can skip the parameter but we can't interchange the Parameters.
- By using Named Parameter we can skip the parameter or interchange the Parameters.

__Example 1 (Named Function With No Parameter)__

```ruby
void methodNameOne() {
  print('Hello World');
}
```

__Example 2 (Named Function With Parameter)__

```ruby
void main() {
  var addedValue = addTwoNumbers(1, 2);
  print(addedValue.toString());
}

int addTwoNumbers(int a, int b) {
  return a + b;
}
```

__Example 3 (Anonymous Function)__

```ruby
void main() {
  var mList = {'Android', 'Flutter', 'IOS', 'Android'};
  
  mList.forEach((element) {
    print(element);
  });
}
```

```ruby
onPressed: (){
//TODO Something
}
```

__Example 4 (Named Function Using Positional Paramters)__

```ruby
bool methodNameTwo(int mValueOne, int mValueTwo) {
  return true;
}
```

__Example 5 (Named Function Using Optional Positional Parameters)__

```ruby
void main() {
  print(methodNameThree(1));
}

int methodNameThree(int mValueOne, [String? mValueTwo]) {
  return mValueOne;
}
```

__Example 6 (Named Function Using Named Parameters)__

```ruby
void main() {
  print(methodNameThree(mValueOne: 1));
}

int? methodNameThree({int? mValueOne, String? mValueTwo}) {
  return mValueOne;
}
```  

__Example 7 (Named Function Using Named Parameters and Default Value)__

```ruby
main() {
  print(methodNameThree(mValueOne: 1));
}

int methodNameThree({required int mValueOne, int mValueTwo = 0}) =>
    mValueOne + mValueTwo;
```

__Example 8 (Dynamic Return Type)__

```ruby
void main() {
  methodNameOne(methodNameTwo(1, 2));
}

void methodNameOne(var msg) {
  print(msg);
}

dynamic methodNameTwo(var a, var b) {
  return a + b;
}
```

## Arrow Function

- A fat arrow is used to define a single expression in a function. 

__Example 1 (Using Regular Function)__

```ruby
int sum(int x, int y) {
  return x + y;
}
```  

__Example 2 (Using Arrow Function)__

```ruby
int sum(int x, int y) => x + y;
```

## Higher Order Function

- The Function passed as parameter to another function or a Function can return another function or It can do both.

__Example 1__

```ruby
void main() {
  var mValueOne = calculator(4, 6, add);
  print(mValueOne);

  var mValueTwo = calculatorFunction(4, 6, add);
  print(mValueTwo);
}

int calculator(int n1, int n2, Function calculation) {
  return calculation(n1, n2);
}

Function calculatorFunction = (int n1, int n2, Function calculation) {
  return calculation(n1, n2);
};

int add(int n1, int n2) {
  return n1 + n2;
}
```  

__Example 2__

```ruby
void main() {
  var mFunction = Car(mDrive: slowDrive);
  mFunction.mDrive();

  mFunction.mDrive = fastDrive;
  mFunction.mDrive();
}

class Car {
  Car({required this.mDrive});

  Function mDrive;
}

void slowDrive() {
  print('The Car is driving Slowly');
}

void fastDrive() {
  print('The Car is driving Fastly');
}
```  

## Collections 

## List

- Dart represents arrays in the form of List objects.
- A List is simply an ordered group of objects. 

__Example 1__

```ruby
void main() {
  var mList = ['Android', 'Flutter', 'IOS'];

  // TODO By using const it makes the List immutable
  var mListOne = const ['Android', 'Flutter', 'IOS'];

  // TODO Using Standard For Loop
  for (int i = 0; i < mList.length; i++) {
    print(mList[i]);
  }

  // TODO For getting the index Value
  print(mList.indexOf('Android'));
  // TODO For adding an item
  mList.add('React');
  // TODO For adding the item in specific position
  mList.insert(1,'List');

  // TODO Using For...In in Loop
  for (String mStringValues in mList) {
    print(mStringValues);
  }
}
```

__Example 2__

```ruby
void main() {
  var mList = ['Android', 'Flutter', 'IOS'];

  // TODO Simply copying the mList using the Spread Operator to mListOne
  var mListOne = [...mList];

  // TODO Using Standard For Loop
  for (int i = 0; i < mListOne.length; i++) {
    print(mList[i]);
  }
}
```  

## Set

- It is an unordered collection of unique items.

__Example__

```ruby
void main() {
  var mList = {'Android', 'Flutter', 'IOS', 'Android'};

  // TODO Using Standard For Loop
  for (String mListValues in mList) {
    print(mListValues);
  }
}
```  

## Maps

- Map is an object that stores data in the form of a key-value pair.
- Each value is associated with its key, and it is used to access its corresponding value.
- Both keys and values can be any type. 

__Need to Know,__

- In Map, each key must be unique, but the same value can occur multiple times.
- But Unlike Lists Maps are unOrdered.

__Example__

```ruby
void main() {
  Map<String, int> phoneBook = {
    'Android': 99998888,
    'Flutter': 99956565,
    'IOS': 99778888,
  };
  
  print(phoneBook['Android']);

  phoneBook['Android'] = 888888888;
  print(phoneBook['Android']);

  print(phoneBook.length);

  print(phoneBook.keys);

  print(phoneBook.values);
}
``` 

## Future, Async and Await

- __Async__ means that this function is asynchronous and you might need to wait a bit to get its result.
- It will be used when we want to define an async method.
- __Await__ literally means - wait here until this function is finished and you will get its return value.
- It will be used When we need to wait there for the method to finish and then proceed with your code execution.
- __Future__ is a type that comes from the future and returns value from your asynchronous function.
- When we want to get a result from an async function.
- __Then((value){…})__ is a callback that’s called when future completes successfully(with a value).
- When you want to process Future after it was successfully finished in an async way - program will continue execution after this async method was called, but .then() callback will be executed later.

__Example 1__

```ruby
void main() async {
  print(createTable());
  print(await addTable());
  updateTable().then((String value) {
    print(value);
  });
}
Future<String> createTable() async {
  return "Create";
}
Future<String> addTable() async {
  return "Adding";
}
Future<String> updateTable() async {
  return "Update";
}

//TODO Throws compile Error need to add async
// Future<String> deleteTable() {
//   return "Delete";
// }
```

__Example 2__

```ruby
void main() {
  printOrderMessage();
}

Future<void> printOrderMessage() async {
  try {
    // TODO We use the await keyword get the async code
    var order = await fetchUserOrder();
    print('Awaiting user order...');
    print(order);
  } catch (err) {
    print('Caught error: $err');
  }
}

Future<String> fetchUserOrder() async {
  return 'Ordered for Salads';
}
```

## Classes and Objects

- A template (blueprint) for creating objects (the real thing) that we're going to showing in our app.
- A class has two important things (i.e.) Properties and Methods.
- Objects represent real life entities.
- In Other words, it is an instance of a class which has state and Behaviour.

__Example__

```ruby
void main() {
  // TODO The Below Line defines the Object
  Car myCar = Car();
  myCar.drive();
}

class Car {
  // TODO numberOfDoors is the Variable (i.e.) Properties
  int numberOfDoors = 5;

  // TODO drive is the Method
  void drive() {
    print('wheels start turning');
  }
}
```  

## Constructor

- Constructor is a block of code which is called when an instance of the class is created.
- At the time of calling the constructor, memory for the object is allocated in the memory.
- It doesn’t have a return type.
- It calls a default constructor if there is no constructor available in the class.

__Example__

```ruby
void main() {
  // TODO The Below Line defines the Object
  Car myCar = Car("Hyundai", "SUV");
  myCar.drive();

  Car mOffers = Car.Offers();
  mOffers.drive();
}

class Car {
  // TODO numberOfDoors is the Variable (i.e.) Properties
  int numberOfDoors = 5;
  String? mName;
  String? mType;

  // TODO Constructor
  // Car(String mName, [String mType = "Hatchback"]) {
  //   this.mName = mName;
  //   this.mType = mType;
  // }

  // TODO Alternative way of using Constructor
  // this - means the instance which it is called
  Car(this.mName, [this.mType = "Hatchback"]);

  // TODO Using Named Constructor
  Car.Offers() {
    mName = "Tata";
    mType = "SUV";
  }

  // TODO drive is the Method
  void drive() {
    print('wheels start turning');
    print('Company is $mName and the Car Type is $mType');
  }
}
```

## Encapsulation

- Binding (or wrapping) code and data together into a single unit are known as Encapsulation.
- The whole idea behind Encapsulation is to hide the implementation details from the users.
- By making the data members public which can be accessed anywhere which is unsafe.
- So We will make our data members private which can be accessible only within the class.
- By providing a getter or setter method, we can make our class read-only or write-only.

__Example 1 (Without Encapsulation)__

```ruby
void main() {
  final john = BankDetails();
  john.bankBalance = 1000;

  print(john.bankBalance);
}

class BankDetails {
  int? bankBalance;
}
```

__Example 2 (With Encapsulation)__

```ruby
void main() {
  final flutter = BankDetails();
  flutter.bankBalance = 1000;

  print(flutter.getBalance);
}

class BankDetails {
  int? _bankBalance;

  set bankBalance(int value) => _bankBalance = value;

  get getBalance => _bankBalance ?? 'UnAuthorized Access';
}
```

## Inheritance

- Inheritance is the Process from which one object acquires all the properties and methods from its Parent Class.
- We can't access private data members of a class through inheritance.
- It provides Code Reusability and Method Overriding.
- Types - Single Inheritance, Multilevel Inheritance and Hierarchical Inheritance.

__Example__

```ruby
void main() {
  PrivateBank mWithdrawValue = PrivateBank();
  print(mWithdrawValue.mBalance);
  print(mWithdrawValue.minimalWithdrawal());
}

class Banks {
  int? mBalance = 1000;
}

class PrivateBank extends Banks {
  String minimalWithdrawal() => 'Minimal withdrawal is 500';
}
```


## Extras

## Difference Between Static and Dynamic Typed Language

- The statically typed languages are those which check the variable types during compile time including languages like C, C++, Java, Swift, and Kotlin.
- In Static programming languages, data types are known and checked during the compile time itself. 
- But in Dynamic programming languages data types are checked only at the run-time including languages like JS, Python R.
- Now coming to Dart, It is a Statically typed programming language.
- Dart also offers a dynamic variable that is checked during the runtime, also you can store any type of data in dynamic at runtime.
- Now we can say that Dart is a statically typed language with the perk of dynamically typed programming languages. 
- Mean Dart is an optionally typed programming language that offers both static and dynamic.

## JIT(Just-In-Time) VS AOT(Ahead-of-Time)  

- __JIT compiler__ converts program source code into native machine code just before program execution. 
- It can be used to improve performance speed and improve application runtime.
- __AOT compiler__ works by compiling your code before it is delivered to whatever runtime environment runs the code. 
- The __AOT compiler__ is typically used when the app is ready to be deployed to either an appstore or an in-house production backend.
- The major difference that exists between Ahead-Of-Time and Just-In-Time compilation is the time in which the compilation happens.  

## Credits

- https://dart-tutorial.com/ (Notes)
- https://www.youtube.com/watch?v=Ej_Pcr4uC2Q (Tutorial)

