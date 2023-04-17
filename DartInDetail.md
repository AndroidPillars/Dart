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
