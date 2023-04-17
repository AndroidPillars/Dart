# Dart

- Learn Dart in 12 Minutes

## 1. Flutter Programming Entry Point

```ruby
void main() {
  print('Hello World');
  print("Hello World");
}
```  

## 2. DataTypes

- Supports the following Data Types.
- Numbers
  - int(1,2,3) - It Supports only int.
  - double(1.0,2.0) - It Supports only double.
  - num(1,1.0,2,2.0) - It Supports both int and double.
- Strings
- Boolean
- var - DataType will create implicitly based on the values we provide.
- Lists (or Arrays)
- Dynamic - For Assigning Mixed Data Type.
- Map - For defining a vlaues in Key Value pairs.
- Set, Runes

## 3. String Interpolation

```ruby
void main() {
  String mStringValueOne = 'Hello';
  String mStringValueTwo = 'World';
  print('The Value is $mStringValueOne $mStringValueTwo');
  print('The Values Length is ${mStringValueOne.length} + ${mStringValueTwo.length}');
}
```  

## 4. Functions and Parameters

- Functions with No Parameters.
- Parameter Types - Positional Paramter, Optional Positional Parameter, Named Parameter
- By using Positional Parameter we can't skip or interchange the Parameters.
- By using Optional Positional Parameter we can skip the parameter but we can't interchange the Parameters.
- By using Named Parameter we can skip the parameter or interchange the Parameters.

__Example 1__

```ruby
void methodNameOne() {
  print('Hello World');
}
```

__Example 2 (Using Positional Paramters)__

```ruby
bool methodNameTwo(int mValueOne, int mValueTwo) {
  return true;
}
```

__Example 3 (Using Optional Positional Parameters)__

```ruby
void main() {
  print(methodNameThree(1));
}

int methodNameThree(int mValueOne, [String? mValueTwo]) {
  return mValueOne;
}
```

__Example 4 (Using Named Parameters)__

```ruby
void main() {
  print(methodNameThree(mValueOne: 1));
}

int? methodNameThree({int? mValueOne, String? mValueTwo}) {
  return mValueOne;
}
```  

## 5. Arrow Functions

- It is not applicable for the Functions which is having more than one expression.

```ruby
void main() => print('Hello World');
```

## 6. Null Safety

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

  // TODO ?. -> If the values is null it returns null during the runtime.
  print(mValue?.length);

  // TODO ! -> If the values is null it will throws an exception during the runtime.
  print(mValue!.length);

  // TODO ?? (Default Operator) -> If the values is null it will set the default keyword during the runtime.
  print(mValue ?? 'Default keyword');

  // TODO ??= -> If the values is null it will set the default keyword during the runtime.
  mValue ??= 'Default keyword';
  print(mValue);

  // TODO ...? (Operational spread operator) -> If the values is null then it will not add or else it will add during the runtime.
  List<int> lowerNumber = [1, 2, 3, 4, 5];
  List<int>? upperNumbers;
  lowerNumber = [...?lowerNumber, ...?upperNumbers];
  print('The Numbers are ${lowerNumber}');
}
```

## 7. Classes & Constructor

```ruby
void main() {
  Student mStudent = Student(name: 'Hello World');
  print(mStudent?.name);
}

class Student {
  String? name;
  int? age;

  Student({String? name, int? age}) {
    this.name = name;
    this.age = age;
  }
}
```

## 8. Constructors

__Example 1__

```ruby
void main() {
  Student mStudent = Student(name: 'Hello World');
  print(mStudent?.name);
}

class Student {
  String? name;
  int? age;

  Student({this.name, this.age});
}
```  

__Example 2 (Using Default Constructor)__

```ruby  
void main() {
  Student mStudent = Student();
  mStudent.name = "Flutter";
  print(mStudent?.name);
}

class Student {
  String? name;
  int? age;
}
```  

## 9. Credits 

- https://www.youtube.com/watch?v=yOelmLdhJwk (Dart Language)
- https://www.youtube.com/watch?v=5Ro-CZ8Msno (NULL Safety)
