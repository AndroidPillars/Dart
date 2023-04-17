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
