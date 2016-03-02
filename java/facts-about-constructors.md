# Facts About Constructors

### Default constructor

If class has no implemented constructor, compiler will create default, non-parameter constructor during compilation process. If there is any implemented constructor in the class (even the only one with parameters) then compiler won't create default constructor.

Default constructor will not be created:
```java
class SomeClass {
  SomeClass(int someInt) {}
}
```
