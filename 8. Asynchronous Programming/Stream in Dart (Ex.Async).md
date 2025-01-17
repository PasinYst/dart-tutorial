# Stream in Dart (Ex.Async)😧
## ภาษา Dart
### Example Of async
```dart
Future<int> doSomeLongTask() async {
  await Future.delayed(const Duration(seconds: 2));
  return 21;
}main() async {
  int result = await doSomeLongTask();
  print(result); // prints '42' after waiting 2 second
}
   ```

<details>
<summary><strong>Output</strong></summary>
<pre><code>21
</code></pre>
</details>

### Example Of async*

```dart
Stream<int> countForOneMinute() async* {
  for (int i = 1; i <= 5; i++) {
    await Future.delayed(const Duration(seconds: 1));
    yield i;
  }
} main() async {
  await for (int i in countForOneMinute()) {
    print(i); // prints 1 to 5, one integer per second
  }
}
   ```
<details>
<summary><strong>Output</strong></summary>
<pre><code>1
2
3
4
5
</code></pre>
</details>

### Example Of yield*
```dart
Stream<int> str(int n) async* {
 if (n > 0) {  
   await Future.delayed(Duration(seconds: 2));
   yield n;
   yield* str(n - 2);
 }
}

void main() {
 str(10).forEach(print);
}
```

<details>
<summary><strong>Output</strong></summary>
<pre><code>10
8
6
4
2
</code></pre>
</details>


## Some More Example OF Stream

### Example 1

```dart
import 'dart:async';

void main() {
  var controller = StreamController();
  controller.stream.listen((event) {
    print(event);
  });
  controller.add('Hello');
  controller.add(42);
  controller.addError('Error!');
  controller.close();
}
```
<details>
<summary><strong>Output</strong></summary>
<pre><code>Hello
42
Uncaught Error: Error!
</code></pre>
</details>


### Example 2

```dart
Stream<int> numberOfStream(int number) async* {
  for (int i = 0; i <= number; i++) {
    yield i;
  }
}

void main(List<String> arguments) {
  // Calling the Stream 
  var stream = numberOfStream(6);
  // Listening to Stream yielding each number
  stream.listen((s) => print(s));
}
```

<details>
<summary><strong>Output</strong></summary>
<pre><code>0
1
2
3
4
5
6
</code></pre>
</details>



### Example 3

```dart
Stream<int> str(int n) async* {
 for (var i = 1; i <= n; i++) {
   await Future.delayed(Duration(seconds: 1));
   yield i;
 }
}

void main() {
 str(10).forEach(print);
}
```

<details>
<summary><strong>Output</strong></summary>
<pre><code>1
2
3
4
5
</code></pre>
</details>

## async vs async*
|async                             |async*                                             |
|----------------------------------|---------------------------------------------------|
|ใช้กับ  Future                      |ใช้กับ  Stream                                       |
|async อาจใช้เวลาในการทำงานที่อาจยาวนาน|async* ส่งค่าผลลัพธ์ที่เป็น Future values หลายๆ ครั้งพร้อมกัน|
|ส่งผลลัพธ์กลับมาในรูปแบบของ Future    |ส่งผลลัพธ์กลับมาในรูปแบบของ Stream                     |

## yield vs yield*
|yield                                               |yield*                           |
|----------------------------------------------------|---------------------------------|
|ใช้สำหรับคืนค่าผลลัพธ์แบบค่าเดียว แต่ไม่หยุดการทำงานของฟังก์ชัน |ใช้สำหรับคืนค่าผลลัพธ์ recursive      |




## Asynchronous Programming ในภาษาอื่นๆ
## ภาษา C

ในภาษา C แท้จริงไม่มีระบบ Asynchronous แบบ Native อย่างที่มีในภาษาอื่น ๆ เช่น Dart หรือ Java โดยตรง ดังนั้นการจัดการกับ Asynchronous ใน C จะต้องใช้เทคนิคและเครื่องมือที่อยู่นอกเหนือจากภาษามาช่วย โดยทั่วไปแล้วจะใช้การทำงานแบบ Thread และการจัดการกับเวลาเพื่อจำลองการทำงานแบบ Asynchronous

## ภาษา Java

### Example Of async

```dart
class ThreadClass extends Thread{
    public void run(){
    System.out.println("Thread is running");
    }
}
class AsyncExample {
    public static void main(String[] args) {
        ThreadClass thread1 = new ThreadClass();
        thread1.start(); 
    }
}
```

<details>
<summary><strong>Output</strong></summary>
<pre><code>Thread is running
</code></pre>
</details>

## ภาษา Python

### Example Of async

```dart
import asyncio
async def do_task(task_name):
    print(f"Start {task_name}")
    await asyncio.sleep(2)  # Simulate some asynchronous task
    print(f"End {task_name}")
async def main():
    task1 = do_task("Task 1")
    task2 = do_task("Task 2")
    await asyncio.gather(task1, task2)
asyncio.run(main())
```
<details>
<summary><strong>Output</strong></summary>
<pre><code>Start Task 1
End Task 1
</code></pre>
</details>

## อ้างอิง
:https://www.tamemo.com/post/178/async-in-dart-1-isolates-event-loop/<br>
:https://www.tamemo.com/post/179/async-in-dart-2-future/<br>
:https://www.tamemo.com/post/180/async-in-dart-3-stream/

