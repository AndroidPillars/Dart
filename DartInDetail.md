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

## Dart

- It is a open source and powerful language very similar to Oops.
- It is a Statically typed programming language (i.e.) If we define a variable as String, We cannot assign other Values like Int, Bool, etc.. 
- Dart also supports a dynamic variable that is checked during the runtime.
- It is also a compiled programming Language (i.e.) It supports Two Types of Compilation -> AOT(Ahead of Time during Development time) and JIT(Just in Time during Production Mode)

## Enum(Enumeration)

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
  }
}

enum Gender { male, female }
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

## const vs final

- Both represent immutability and read only.
- Final keyword will be used to declare run time values.
- Const keyword will be used to declare compile time values.
- Variables declared using the const keyword are implicitly final.

__Need to Know,__

- Prefer using const for constant declarations.
- Const declarations are more hot-reload friendly and allow to use const constructors if an instantiation references this declaration.

__Example__

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

## List

- Dart represents arrays in the form of List objects.
- A List is simply an ordered group of objects. 

__Example__

```ruby
void main() {
  var mList = ['Android', 'Flutter', 'IOS'];

  // TODO Using For in Loop
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

## Conditionals - IF/ELSE

- IF statement basically just checks to see if a condition is true then it carry out the instruction inside a set of curlybraces or else it move in to the else part.
- Different types of Operators [ ==, !=, >, <, >=, <=, &&, ||, ! ] 

__Example__

```ruby
import 'dart:math';

void main() {
  loveCalculator();
}

void loveCalculator() {
  int loveScore = Random().nextInt(100) + 1;

  print(loveScore);

  if (loveScore > 70) {
    print('You Love Each Other very much');
  } else if (loveScore > 50) {
    print('You Love Each Other');
  } else {
    print('You Love Each Other but have to understand');
  }
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
