## I. Pagekage trong Java

### 1. Khái niệm về package trong java

Một **Package (gói) trong Java** là một nhóm các class, interface và các package con tương tự, liên quan đến nhau.


Chúng ta có thể coi package giống như là một folder vậy.


Các package trong Java được sử dụng để tránh việc xung đột trong khi đặt tên, để kiểm soát truy cập, giúp bạn tìm kiếm và sử dụng các class, interface… một các dễ dàng hơn.


Các package được chia làm hai loại:


* Các package được tích hợp sẵn từ Java API (Built-in packages)
* Các package do người dùng tự định nghĩa (đây là package do bạn tự tạo ra) – User defined packages

### 2. Các package có sẵn trong Java API

 Package trong java được chia làm 2 loại:

* Một loại được tích hợp từ Java API

* Loại package thứ 2 là package do người dùng tự định nghĩa.

![example](https://niithanoi.edu.vn/pic/News/images/tin-tuc-cong-nghe-va-lap-trinh/so-do-minh-hoa-cau-truc-package-trong-java.jpg)

*Các package hay dùng (phổ biến) được tích hợp sẵn trong Java bao gồm:*


* **java.lang:** Chứa các lớp hỗ trợ ngôn ngữ (ví dụ: lớp được định nghĩa các kiểu dữ liệu nguyên thủy, các phép toán). Package này được import tự động.
* **java.io:** Chứa lớp để hỗ trợ input / output (I/O)
* **java.util:** Chứa các lớp tiện ích thực hiện các cấu trúc dữ liệu như danh sách liên kết, dictionary và hỗ trợ cho các hoạt động date / time.
* **java.applet:** Chứa các lớp để tạo Applet.
* **java.awt:** Chứa các class để triển khai các thành phần cho giao diện người dùng đồ họa (ví dụ như button, menu,…).
* **java.net:** Chứa các lớp để hỗ trợ các thao tác trong mạng (network).

### 3. Lợi ích của việc sử dụng package trong java

* Tìm kiếm và sử dụng các class, interface,… một các dễ dàng hơn.

* Package cung cấp bảo vệ truy cập

* Package ngăn chặn được xung đột khi đặt tên. Ví dụ: Có thể có 2 class People (tên class giống hệt nhau) trong 2 package khác nhau.

* Các package có thể được coi là đóng gói dữ liệu (hoặc ẩn dữ liệu)

* ...

### 4. Cách sử dụng package trong java

#### Quy ước đặt tên package trong Java

 
Tên package trong Java và cấu trúc thư mục có liên quan chặt chẽ với nhau.


Ví dụ: Nếu tên package là college.staff.cse, khi đó có 3 thư mục là: college, staff và cse sao cho cse nằm trong staff và staff nằm trong college.


Tên packages nên được viết thường hết tất cả các chữ cái.

#### Cách tạo package trong Java


Để tạo package trong Java cũng rất đơn giản, bạn click chuột phải vào thư mục `src` trong project của bạn, chọn `New -> Package`

![example](https://niithanoi.edu.vn/pic/News/images/tin-tuc-cong-nghe-va-lap-trinh/huong-dan-tao-package-trong-java-1.jpg)

Gõ vào ô name tên package bạn muốn đặt (nên đặt có ý nghĩa chút nha) rồi gõ `Enter` là xong.


Sau đó bạn sẽ New các class, interface,… có liên quan đến nhau trong package vừa đặt để gõ code.

Một package này có thể nằm trong một package khác, nên trong package, bạn cũng có thể New một package mới.


Để sử dụng được các class ở package `package1` trong class `class1` ở package `package2`, thì bạn phải import class đó vào.


Cú pháp là: `import + <tên package>.<tên class>`

Hoặc để import tất cả các class trong một package, thì bạn chỉ cần sử dụng ký tự hoa thị * như thế này:


`import <tên package>.*` 

(Ví dụ `import package2.*`)


Vậy là trong class `class1` ở package `package1` đã có thể sử dụng tất cả các class trong có trong package `package2`.

**Lưu ý!**

*-> Các class trong cùng một package thì không cần import.*


Tóm lại hiểu một cách đơn giản là package sẽ dùng để gom các class, interface,… có liên quan với nhau thành một package để tiện sử dụng.

## II. Xử lý ngoại lệ trong java

### 1. Khái quát chung về xử lý Exception 

**Exception Handling trong java** hay xử lý ngoại lệ trong java là một cơ chế mạnh mẽ để xử lý các lỗi runtime để có thể duy trì luồng bình thường của ứng dụng.

#### Exception là gì?
Theo từ điển: Exception (ngoại lệ) là một tình trạng bất thường.

Trong java, ngoại lệ là một sự kiện làm gián đoạn luồng bình thường của chương trình. Nó là một đối tượng được ném ra tại runtime.

**Exception Handling là gì?**

Exception Handling (xử lý ngoại lệ) là một cơ chế xử lý các lỗi runtime như ClassNotFound, IO, SQL, Remote, vv

**Lợi thế của Exception Handling trong java**

Lợi thế cốt lõi của việc xử lý ngoại lệ là duy trì luồng bình thường của ứng dụng. Ngoại lệ thường làm gián đoạn luồng bình thường của ứng dụng đó là lý do tại sao chúng ta sử dụng xử lý ngoại lệ. Hãy xem xét kịch bản sau:
```c
statement 1;  
statement 2;  
statement 3;  
statement 4;  
statement 5; //ngoại lệ xảy ra
statement 6;  
statement 7;  
statement 8;  
statement 9;  
statement 10;  
```

Giả sử có 10 câu lệnh trong chương trình của bạn và xảy ra trường hợp ngoại lệ ở câu lệnh 5, phần còn lại của chương trình sẽ không được thực thi, nghĩa là câu lệnh 6 đến 10 sẽ không chạy. Nếu chúng ta thực hiện xử lý ngoại lệ, phần còn lại của câu lệnh sẽ được thực hiện. Đó là lý do tại sao chúng ta sử dụng xử lý ngoại lệ trong java.

**Hệ thống cấp bậc của các lớp ngoại lệ trong Java**

![example](https://viettuts.vn/images/java/exception-handling/exception-handling-trong-java.png)


**Các kiểu của ngoại lệ**

Có hai loại ngoại lệ chính là: checked và unchecked. Còn Sun Microsystem nói rằng có ba loại ngoại lệ:

1. Checked Exception
2. Unchecked Exception
3. Error

***Sự khác nhau giữa các ngoại lệ checked và unchecked***

**1. Checked Exception**

Các lớp extends từ lớp Throwable ngoại trừ RuntimeException và Error được gọi là checked exception, ví dụ như Exception, SQLException vv. Các checked exception được kiểm tra tại compile-time.

Ví dụ: ta có hàm testCheckedException() ném ra một ngoại lệ được extends từ lớp Exception, nên khi nó được gọi ra trong hàm main, trình biên dịch sẽ check(báo lỗi) tức là trình biên dịch sẽ nói ràng hàm này có ném lỗi ra đấy phải xử lý lỗi đi.

![example](https://viettuts.vn/images/java/exception-handling/vi-du-checked-exception-trong-java.png)

**2. Unchecked Exception**

Các lớp extends từ RuntimeException được gọi là unchecked exception, ví dụ: ArithmeticException, NullPointerException, ArrayIndexOutOfBoundsException,... Các ngoại lệ unchecked không được kiểm tra tại compile-time mà chúng được kiểm tra tại runtime.

Ví dụ: ta có hàm testUncheckedException() ném ra một ngoại lệ được extends từ lớp RuntimeException, nên khi nó được gọi ra trong hàm main, trình biên dịch sẽ không check (không báo lỗi). Mà khi chạy nếu có lỗi sẽ bắn ra tại runtime.

![example](https://viettuts.vn/images/java/exception-handling/vi-du-unchecked-exception-trong-java.png)

**3. Error**
Error là lỗi không thể cứu chữa được, ví dụ: OutOfMemoryError, VirtualMachineError, AssertionError, vv

***Các kịch bản phổ biến nơi ngoại lệ có thể xảy ra***

**1. ArithmeticException**

Nếu chúng ta chia bất kỳ số nào cho số 0, xảy ra ngoại lệ ArithmeticException.
```c
int a = 50 / 0;//ArithmeticException

```

**2. NullPointerException**
Nếu chúng ta có bất kỳ biến nào có giá trị null , thực hiện bất kỳ hoạt động nào bởi biến đó sẽ xảy ra ngoại lệ NullPointerException.

```c
String s=null;  
System.out.println(s.length());//NullPointerException

```

**3. NumberFormatException**

Sự định dạng sai của bất kỳ giá trị nào, có thể xảy ra NumberFormatException. Giả sử ta có một biến String có giá trị là các ký tự, chuyển đổi biến này thành số sẽ xảy ra NumberFormatException

```c
String s="abc";  
int i=Integer.parseInt(s);//NumberFormatException 
```

**4. ArrayIndexOutOfBoundsException**

Nếu bạn chèn bất kỳ giá trị nào vào index sai, sẽ xảy ra ngoại lệ ArrayIndexOutOfBoundsException như thể hiện dưới đây:

```c
int a[]=new int[5];  
a[10]=50; //ArrayIndexOutOfBoundsException  
```

***Các từ khóa xử lý ngoại lệ trong java***

Có 5 từ khóa được sử dụng để xử lý ngoại lệ trong java, đó là:

* try
* catch
* finally
* throw
* throws

### 2. Khối lệnh try-catch trong java

#### Khối lệnh try trong java

Khối lệnh try trong java được sử dụng để chứa một đoạn code có thế xảy ra một ngoại lệ. Nó phải được khai báo trong phương thức.

Sau một khối lệnh try bạn phải khai báo khối lệnh catch hoặc finally hoặc cả hai.

**Cú pháp của khối lệnh try-catch trong java**

```c
try {  
    // code có thể ném ra ngoại lệ
} catch(Exception_class_Name ref) {
    // code xử lý ngoại lệ
}  
```

**Cú pháp của khối lệnh try-finally trong java**

```c
try {  
    // code có thể ném ra ngoại lệ
} finally {
    // code trong khối này luôn được thực thi
}  
```

**Khối lệnh catch trong java**

Khối catch trong java được sử dụng để xử lý các Exception. Nó phải được sử dụng sau khối try.

Bạn có thể sử dụng nhiều khối catch với một khối try duy nhất.

**Vấn đề không có ngoại lệ xử lý**

```c
public class TestTryCatch1 {
    public static void main(String args[]) {
        int data = 50 / 0;  // ném ra ngoại lê ở đây
        System.out.println("rest of the code...");
    }
}
//output:
Exception in thread "main" java.lang.ArithmeticException: / by zero
 at vn.tpv.exception1.TestTryCatch1.main(TestTryCatch1.java:5)
```

Trong ví dụ trên, phần còn lại của code không được thực thi (dòng chữ "rest of the code..." không được in ra màn hình). Tất cả các lệnh không được thực thi sau khi xảy ra ngoại lệ.

**Giải quyết bằng xử lý ngoại lệ**

```c
public class TestTryCatch2 {
    public static void main(String args[]) {
        try {
            int data = 50 / 0;
        } catch (ArithmeticException e) {
            System.out.println(e);
        }
        System.out.println("rest of the code...");
    }
}

//output
java.lang.ArithmeticException: / by zero
rest of the code...
```

Trong ví dụ này, phần còn lại của code được thực thi nghĩa là dòng chữ "rest of the code..." được in ra màn hình.

### 2. Từ khóa throw trong java

Từ khoá throw trong java được sử dụng để ném ra một ngoại lệ cụ thể.

Chúng ta có thể ném một trong hai ngoại lệ checked hoặc unchecked trong java bằng từ khóa throw. Từ khóa throw chủ yếu được sử dụng để ném ngoại lệ tùy chỉnh (ngoại lệ do người dùng tự định nghĩa). Chúng ta sẽ học ngoại lệ tùy chỉnh trong bài sau.

Cú pháp từ khóa throw:

```c
throw exception;
```

Ví dụ về throw IOException.

```c
throw new IOException("File không tồn tại");
```

**Ví dụ về từ khóa throw trong java**
Ví dụ 1: throw ra ngoại lệ nhưng không xử lý

Trong ví dụ này, chúng ta tạo ra phương thức validate() với tham số truyền vào là giá trị integer. Nếu tuổi dưới 18, chúng ta ném ra ngoại lệ ArithmeticException nếu không in ra một thông báo "welcome".

```c
public class TestThrow1 {
    static void validate(int age) {
        if (age < 18)
            throw new ArithmeticException("not valid");
        else
            System.out.println("welcome");
    }
 
    public static void main(String args[]) {
        validate(13);
        System.out.println("rest of the code...");
    }
}

//Output
Exception in thread "main" java.lang.ArithmeticException: not valid
```

Ví dụ 2: throw ra ngoại lệ nhưng có xử lý

```c
public class TestThrow2 {
    static void validate(int age) {
        try {
            if (age < 18)
                throw new ArithmeticException("not valid");
            else
                System.out.println("welcome");
        } catch (ArithmeticException ex) {
            System.out.println(ex.getMessage());
        }
    }
 
    public static void main(String args[]) {
        validate(13);
        System.out.println("rest of the code...");
    }
}

//Output:
not valid
rest of the code...
```

### 3. Khối lệnh finally trong java

Khối lệnh finally trong java được sử dụng để thực thi các lệnh quan trọng như đóng kết nối, đóng cá stream,...

Khối lệnh finally trong java luôn được thực thi cho dù có ngoại lệ xảy ra hay không hoặc gặp lệnh return trong khối try.

Khối lệnh finally trong java được khai báo sau khối lệnh try hoặc sau khối lệnh catch.

![example](https://viettuts.vn/images/java/exception-handling/flow-cua-khoi-lenh-finally-trong-java.png)


## III. Custom Exception trong Java

Custom Exception trong Java
Đăng vào 07/11/2017 . Được đăng bởi GP Coder . 7974 Lượt xem . Toàn màn hình

**Custom Exception** là ngoại lệ do người dùng tự định nghĩa. **Custom Exception** trong Java được sử dụng để tùy biến ngoại lệ theo yêu cầu của người dùng. Bởi sự giúp đỡ của loại ngoại lệ này, người dùng có thể có riêng kiểu và thông điệp ngoại lệ riêng cho mình.

Thông thường, để tạo ra custom exception thuộc loại `checker` chúng ta kế thừa từ lớp **Exception**. Để tạo custom exception thuộc loại `unchecked` chúng ta kế thừa từ lớp `RuntimeException`.

Trong các ứng dụng thực tế, thông thường custom exception được tạo là **checked exception**.

Ví dụ:

Tạo ngoại lệ tùy chỉnh thuộc loại checked exception:

```c
class InvalidAgeException extends Exception {
    InvalidAgeException(String s) {
        super(s);
    }
}
```

Sử dụng ngoại lệ tùy chỉnh:

```c
class CustomExceptionExample {
 
    static void validate(int age) throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("not valid");
        } else {
            System.out.println("welcome to vote");
        }
    }
 
    public static void main(String args[]) {
        try {
            validate(13);
        } catch (Exception m) {
            System.out.println("Exception occured: " + m);
        }
 
        System.out.println("rest of the code...");
    }
}
```



