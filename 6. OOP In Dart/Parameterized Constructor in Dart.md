# Parameterized Constructor in Dart
**Parameterized Constructor** เป็น **constructor** ที่มีการกำหนด **parameters** และ ค่าที่รับมาจะถูกส่งไปใน **constructor** ขณะที่กำลังมีการสร้าง **object** อาจเพื่อใช้กำหนดค่าให้  **instance variables** หรือ **ตัวแปร** ของ **Class**

## Syntax
```dart
    class ClassName {
      // Instance Variables
      int? number;
      String? name;
      // Parameterized Constructor
      ClassName(this.number, this.name);
    }
```
หรือจะเขียนแบบนี้ก็ได้
```dart
    class ClassName {
      // Instance Variables
      int? number;
      String? name;
      // Parameterized Constructor
      ClassName(int number, String name){
	      this.number = number;
	      this.name = name;
      }
    }
```
### Example 1: Parameterized Constructor In Dart
ในตัวอย่างที่ 1 มี **Class Student** ที่มี ตัวแปร 3 ตัว คือ **name** , **age** และ **rollNumber**
ใน **Class Student** มี **constructor** ตัวเดียว ที่มีการรับ **parameters** มากำหนดค่าให้**ตัวแปร**ใน class ทั้ง 3 ตัว
```dart
    class Student {
      String? name;
      int? age;
      int? rollNumber;
      // Constructor
      Student(this.name, this.age, this.rollNumber);
    }
    
    void main(){
        // Here student is object of class Student. 
        Student student = Student("John", 20, 1);
        print("Name: ${student.name}");
        print("Age: ${student.age}");
        print("Roll Number: ${student.rollNumber}");
    }
```
ในภาษา **Dart** สามารถกำหนดค่าตัวแปรของ **Class** ใน **parameters** ของ **constructor** ได้เลย โดยใช้ ***this*.*ชื่อตัวแปร*** ของ **Class** เช่นในตัวอย่าง ***this*.*name*** 

> Output
> 
```dart
    Name: John
    Age: 20
    Roll Number: 1
```
## 

### Example 2: Parameterized Constructor With Named Parameters In Dart
```dart
    class Student {
      String? name;
      int? age;
      int? rollNumber;
    
      // Constructor
      Student({String? name, int? age, int? rollNumber}) {
        this.name = name;
        this.age = age;
        this.rollNumber = rollNumber;
      }**strong text**
    }
    
    void main(){
        // Here student is object of class Student. 
        Student student = Student(name: "John", age: 20, rollNumber: 1);
        print("Name: ${student.name}");
        print("Age: ${student.age}");
        print("Roll Number: ${student.rollNumber}");
    }
```
ในตัวอย่างที่ 2 ต่างจากตัวอย่างที่ 1 คือ มีการใช้ **name parameters** ใน **constructor** 
ทำให้การสร้าง **object** ง่ายขึ้น เพราะ ไม่จำเป็นต้อง เรียง **argument** ที่จะส่งไปให้ตรงกับ **parameter** ของ **constructor** เช่น **constructor** ของ **Class Student** มี **parameters** เป็น **name** , **age** และ **rollNumber** ตามลำดับ
```dart
    class Student {
      String? name;
      int? age;
      int? rollNumber;
    
      // Constructor
      Student({String? name, int? age, int? rollNumber}) {
        this.name = name;
        this.age = age;
        this.rollNumber = rollNumber;
      } 
    }
```
เราสามารถสร้าง **object** โดยส่ง **argument** ไม่ตรงกับ **parameters** ได้ เพระ มี **name parameters** คอยกำกับอยู่ เช่น
```dart
    void main(){
        Student student = Student(rollNumber: 1, age: 20, name: "John" );
        print("Name: ${student.name}");
        print("Age: ${student.age}");
        print("Roll Number: ${student.rollNumber}");
    }
```

> Output
> 
```dart
	Name: John
	Age: 20
	Roll Number: 1
```
## 


