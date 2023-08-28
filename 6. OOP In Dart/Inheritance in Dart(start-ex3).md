# Inheritance In Dart
  การสืบทอด(Inheritance) คือ การที่ class หรือ object ได้รับการถ่ายทอด attributeและ method จากclassอื่น นั่นจะทำให้คลาสดังกล่าวมี attribute และ method เหมือน class ที่มันสืบทอดมา จะเรียกว่า Parent Class,base class หรือ superclass. ส่วน class ที่ได้รับการสืบทอดเรียกว่า Child Class,deprived class หรือ subclass 
# Syntax ใน ภาษา Dart
```dart
class ParentClass {
  // Parent class code
}

class ChildClass extends ParentClass {
  // Child class code
}
```
# Syntax ใน ภาษา ภาษาอื่นๆ
- Java
```java
class Employee{  
   //code
}  
class Programmer extends Employee{  
  //code
} 
```
เมื่อเปรียบเทียบ syntax ของ ภาษา dart กัย java จะมี syntaxที่ใช้ในการ Inheritance ที่เหมือนกัน

- Python
```python
class Parent:
  #code
class Child(Parent):
  #code
```
แต่เมื่อเปรียบเทียบ syntax กับภาษา python แล้ว ตัวภาษา pythonจะใช้ () แทน keyword extand

#  Example 1: Inheritance In Dart
```dart
class Person {
  // Properties
  String? name;
  int? age;

  // Method
  void display() {
    print("Name: $name");
    print("Age: $age");
  }
}
// Here In student class, we are extending the
// properties and methods of the Person class
class Student extends Person {
  // Fields
  String? schoolName;
  String? schoolAddress;

  // Method
  void displaySchoolInfo() {
    print("School Name: $schoolName");
    print("School Address: $schoolAddress");
  }
}

void main() {
  // Creating an object of the Student class
  var student = Student();
  student.name = "John";
  student.age = 20;
  student.schoolName = "ABC School";
  student.schoolAddress = "New York";
  student.display();
  student.displaySchoolInfo();
}
```
จากในตัวอย่าง เราจะสร้างclass Person จากนั้นสร้างclass Student ที่สืบทอด คุณสมบัติและ methodของclass Person
```
Name: John
Age: 20
School Name: ABC School
School Address: New York
```
## ข้อดีของInheritance ใน Dart
- ส่งเสริมการนำ code กลับมาใช้ซ้ำได้และลด code ที่ซ้ำซ้อน
- ช่วยในการออกแบบโปรแกรมให้ดีขึ้น
- ช่วยให้ code ง่ายขึ้น สะอาดขึ้น และประหยัดเวลา
- อำนวยความสะดวกในการสร้างclass libraries