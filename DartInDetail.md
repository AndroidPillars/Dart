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
- final keyword will be used to declare run time values.
- const keyword will be used to declare compile time values.
- Variables declared using the const keyword are implicitly final.

__Need to Know,__

- PREFER using const for const declarations.
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
