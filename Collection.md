
##I.Collection và collections
"Collection" và "Collections" trong java là hai khái niệm khác nhau.
**Collections trong java** là một khuôn khổ cung cấp một kiến trúc để lưu trữ và thao tác tới nhóm các đối tượng. Tất cả các hoạt động mà bạn thực hiện trên một dữ liệu như tìm kiếm, phân loại, chèn, xóa,... có thể được thực hiện bởi Java Collections.

**Collection trong java** là một root interface trong hệ thống cấp bậc Collection. Java Collection cung cấp nhiều interface (Set, List, Queue, Deque vv) và các lớp (ArrayList, Vector, LinkedList, PriorityQueue, HashSet, LinkedHashSet, TreeSet vv).
![example](https://viettuts.vn/images/java/java-collection/colection-vs-collections-trong-java.png)
###1.Hệ thống cấp bậc Collection trong java
Gói java.util chứa tất cả các lớp và interface của Collection.
![example](https://viettuts.vn/images/java/java-collection/he-thong-cap-bac-colection-trong-java.png)

###2.Dưới đây là mô tả những interface chính của Collection
* **Set:** là một collection không thể chứa 2 giá trị trùng lặp. Set được sử dụng để biểu diễn các bộ, chẳng hạn như bộ tú lu khơ, thời khóa biểu của học sinh, các tiến trình đang chạy trên máy tính...
* **List:** là một collection có thứ tự (đôi khi còn được gọi là một chuỗi). List có thể chứa các phần tử trùng lặp. Thường có quyền kiểm soát chính xác vị trí các phần tử được chèn vào và có thể truy cập chúng bằng chỉ số (vị trí của chúng).
* **Queue (hàng đợi):** là một collection được sử dụng để chứa nhiều phần tử trước khi xử lý. Bên cạnh các thao tác cơ bản của collection, Queue cung cấp các thao tác bổ sung như chèn, lấy ra và kiểm tra. Queue có thể được sử dụng như là FIFO (first-in, first-out - vào trước, ra trước)
* **Deque:** là một collection được sử dụng để chứa nhiều phần tử trước khi xử lý. Ngoài các thao tác cơ bản của collection, một Deque cung cấp các thao tác bổ sung như chèn, lấy ra và kiểm tra. Deques có thể được sử dụng như là FIFO (first-in, first-out - vào trước, ra trước) và LIFO (last-in, first-out - vào sau, ra trước). Trong một Deque, tất cả các phần tử mới có thể được chèn vào, lấy ra và lấy ra ở cả hai đầu.
* **Map:** là một đối tượng ánh xạ mỗi key tương úng với một giá trị. Map không thể chứa giá trị trùng lặp. Mỗi key có thể ánh xạ đến nhiều nhất một giá trị.

###3.Dưới đây là mô tả 2 interface được sắp xếp của Set mà Map
* **SortedSet:** là một Set chứa các phần tử theo thứ tự tăng dần.
* **SortedMap:** là một Map chứa các phần tử được sắp xếp theo thứ tự tăng dần của key của chúng. Các SortedMap được sử dụng cho các collection theo thứ tự tự nhiên của cặp key/value, chẳng hạn như từ điển và danh bạ điện thoại.

###4.Các phương thức của interface Collection trong java
Có nhiều phương thức được khai báo trong interface Collection như sau:
| Phương thức                              | Mô tả                                                                                                           |
| ---------------------------------------- | --------------------------------------------------------------------------------------------------------------- |
| public boolean add(Object element)       | Được sử dụng để chèn một phần tử vào collection.                                                                |
| public boolean addAll(Collection c)      | Được sử dụng để chèn các phần tử collection được chỉ định vào collection gọi phương thức này.                   |
| public boolean remove(Object element)    | Được sử dụng để xóa phần tử từ collection.                                                                      |
| public boolean removeAll(Collection c)   | Được sử dụng để xóa tất cả các phần tử của collection được chỉ định từ collection gọi phương thức này.          |
| public boolean retainAll(Collection c)   | Được sử dụng để xóa tất cả các thành phần từ collection gọi phương thức này ngoại trừ collection được chỉ định. |
| public int size()                        | Trả lại tổng số các phần tử trong collection.                                                                   |
| public void clear()                      | Loại bỏ tổng số của phần tử khỏi collection.                                                                    |
| public boolean contains(Object element)  | Được sử dụng để tìm kiếm phần tử.                                                                               |
| public boolean containsAll(Collection c) | Được sử dụng để tìm kiếm collection được chỉ định trong collection.                                             |
| public Iterator iterator()               | Trả về một iterator.                                                                                            |
| public Object[] toArray()                | Chuyển đổi collection thành mảng (array).                                                                       |
| public boolean isEmpty()                 | Kiểm tra nếu collection trống.                                                                                  |
| public boolean equals(Object element)    | So sánh 2 collection.                                                                                           |

Ví dụ về collection trong java:
```c
import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;
import java.util.List;
public class Main {
    public static void main(String[] args) {
        //khai bao collection ArrayList ke thua tu List
        List<Integer> list = new ArrayList<Integer>();
        //them cac phan tu vao danh sach
        list.add(5);
        list.add(4);
        list.add(3);
        list.add(2);
        list.add(1);
        //dung phuong thuc sort cua Collections de sap xep mang tang dan
        Collections.sort(list);
        //cuoi cung in ra cac phan tu da duoc sap xep
        for(int x : list) System.out.print(x+" ");

    }

}

//Output: 1 2 3 4 5
```
##II.Các collection phổ biến
###1.List
List là một interface trong Collection. List là một danh sách các phần tử được sắp xếp theo thứ tự. List cho phép các phần tử trùng lặp và cho phép các phần tử null. List cung cấp các phương thức để truy cập các phần tử theo chỉ số và cho phép thay đổi các phần tử.

Cú pháp khai báo List:
`List<O> list = new ArrayList<O>();`
***Các phương thức của interface List trong java:***
| Phương thức                            | Miêu tả                                                                                 |
| -------------------------------------- | --------------------------------------------------------------------------------------- |
| void add(int index,Object element)     | Chèn các phần tử vào list tại chỉ số index.                                             |
| boolean addAll(int index,Collection c) | Chèn tất cả các yếu tố của c vào danh sách tại chỉ số index.                            |
| object get(int index)                  | Trả về đối tượng được lưu trữ tại chỉ số index trong list.                              |
| object set(int index,Object element)   | Gán phần tử cho vị trí được chỉ định index trong list.                                  |
| object remove(int index)               | Nó được sử dụng để xóa các phần tử tại vị trí có chỉ số index và trả về phần tử đã xóa. |

**Ví dụ về List trong Java:**
```c
import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;
import java.util.List;
public class Main {
    public static void main(String[] args) {
        List<Integer> list = new ArrayList<Integer>();
        //them cac phan tu vao danh sach bang phuong thuc add
        list.add(5);
        list.add(4);
        list.add(3);
        list.add(2);
        list.add(1);
        //set cho phan tu o index 0 la 1
        list.set(0,1);
        for(int i=0;i<list.size();i++)
        {
            System.out.print(list.get(i)+" ");
        }

    }

}
//Output:
1 4 3 2 1
```

###2.ArrayList
**Lớp ArrayList** trong java là một lớp kế thừa lớp AbstractList và triển khai của List Interface trong Collections Framework nên nó sẽ có một vài đặc điểm và phương thức tương đồng với List. ArrayList được sử dụng như một mảng động để lưu trữ các phần tử.

***Những điểm cần ghi nhớ về ArrayList:***

* Lớp ArrayList trong java có thể chứa các phần tử trùng lặp.
* Lớp ArrayList duy trì thứ tự của phần tử được thêm vào.
* Lớp ArrayList là không đồng bộ (non-synchronized).
* Lớp ArrayList cho phép truy cập ngẫu nhiên vì nó lưu dữ liệu theo chỉ mục.
* Lớp ArrayList trong java, thao tác chậm vì cần nhiều sự dịch chuyển nếu bất kỳ phần tử nào bị xoá khỏi danh sách.

*Hierarchy của lớp ArrayList trong java:*
![example](https://viettuts.vn/images/java/java-collection/hiararchy-lop-arraylist-trong-java.png)

**Cú pháp khai báo ArrayList:**

``ArrayList<O> arr = new ArrayList<O>();``

***Các phương thức của interface ArrayList trong java:***
| Phương thức                                          | Miêu tả                                                                                                                            |
| ---------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------- |
| void add(int index,Object element)                   | Chèn các phần tử vào list tại chỉ số index.                                                                                        |
| boolean addAll(int index, Collection<? extends E> c) | Chèn tất cả các phần tử của một Collection vào danh sách tại vị trí chỉ định                                                       |
| object get(int index)                                | Trả về đối tượng được lưu trữ tại chỉ số index trong list.                                                                         |
| object set(int index,Object element)                 | Gán phần tử cho vị trí được chỉ định index trong list.                                                                             |
| object remove(int index)                             | Xóa các phần tử tại vị trí có chỉ số index và trả về phần tử đã xóa.                                                               |
| void retainAll(Collection c)                         | xóa những phần tử không thuộc collection c ra khỏi danh sách.                                                                      |
| int indexOf(Object o)                                | Trả về chỉ mục trong danh sách với sự xuất hiện đầu tiên của phần tử được chỉ định, hoặc -1 nếu danh sách không chứa phần tử này.  |
| int lastIndexOf(Object o)                            | Trả về chỉ mục trong danh sách với sự xuất hiện cuối cùng của phần tử được chỉ định, hoặc -1 nếu danh sách không chứa phần tử này. |
| Object[] toArray()                                   | Trả về một mảng chứa tất cả các phần tử trong danh sách này theo đúng thứ tự.                                                      |
| Object clone()                                       | Trả về một bản sao của ArrayList.                                                                                                  |
| void clear()                                         | Xóa tất cả các phần tử từ danh sách này.                                                                                           |
| boolean contains(element)                            | Kết quả trả về là true nếu tìm thấy element trong danh sách, ngược lại trả về false.                                               |

**Ví dụ về ArrayList:**
```c
import java.util.ArrayList;
import java.util.Collections;
import java.util.Scanner;
import java.util.List;
public class Main {
    public static void main(String[] args) {
        ArrayList<Integer> list = new ArrayList<Integer>();
        //them cac phan tu vao danh sach bang phuong thuc add
        list.add(5);
        list.add(4);
        list.add(3);
        list.add(2);
        list.add(1);
        //set cho phan tu o index 0 la 1
        list.set(0,1);
        for(int i=0;i<list.size();i++)
        {
            System.out.print(list.get(i)+" ");
        }

    }

}
//Output
1 4 3 2 1
```
###3.Map
Trong java, map được sử dụng để lưu trữ và truy xuất dữ liệu theo cặp key và value. Mỗi cặp key và value được gọi là mục nhập (entry). Map trong java chỉ chứa các giá trị key duy nhất. Map rất hữu ích nếu bạn phải tìm kiếm, cập nhật hoặc xóa các phần tử trên dựa vào các key.
***Những điểm cần ghi nhớ về Map:***
```c* Map là một lớp kế thừa lớp Collection nên nó sẽ có một vài đặc điểm và phương thức tương đồng với Collection.
* Map không chứa các phần tử trùng lặp.
* Map không chứa các phần tử null.
* Map không đồng bộ, nó không là thread-safe và không đảm bảo sự đồng bộ.
* Map là một lớp không có thứ tự.
```
**Cú pháp khai báo Map:**

``Map<K, V> map = new HashMap<K, V>();``
**Các phương thức hữu ích của Map interface**
| Phương thức                          | Miêu tả                                                  |
| ------------------------------------ | -------------------------------------------------------- |
| Object put(Object key, Object value) | Chèn một mục nhập trong map hiện tại.                    |
| void putAll(Map map)                 | Chèn map chỉ định vào map hiện tại.                      |
| Object remove(Object key)            | Xóa một mục nhập của key được chỉ định.                  |
| Object get(Object key)               | Trả lại giá trị cho khoá được chỉ định.                  |
| boolean containsKey(Object key)      | Tìm kiếm key được chỉ định từ map hiện tại.              |
| Set keySet()                         | Trả đối tượng Set có chứa tất cả các keys.               |
| Set entrySet()                       | Trả lại đối tượng Set có chứa tất cả các keys và values. |

**Map.Entry Interface**
Entry là một interface con của Map. Vì vậy, chúng ta được truy cập nó bằng tên Map.Entry. Nó cung cấp các phương pháp để truy xuất các key và value.

**Các phương thức của Map.Entry interface**
| Phương thức       | Miêu tả                       |
| ----------------- | ----------------------------- |
| Object getKey()   | Nó được dùng để lấy key.      |
| Object getValue() | Nó được sử dụng để lấy value. |

**Ví dụ về Map trong java**
```c
import java.util.*;

public class Main {
    public static void main(String[] args) {
        Map<String, String> map = new HashMap<String, String>();
        map.put("VDT","Vu Dinh Thiet");
        map.put("DHA","Dinh Hoang Anh");
        map.put("LMH","Luu Minh Hieu");
        //In ra cac key va value
        Set<String> set=map.keySet();
        for(String x : set)
        {
            System.out.println("Key: "+x+" -> Value: "+map.get(x));
        }

    }

}
//Output:
Key: LMH -> Value: Luu Minh Hieu
Key: VDT -> Value: Vu Dinh Thiet
Key: DHA -> Value: Dinh Hoang Anh
```

##III.Phân biệt List và ArrayList
###1.Điểm khác nhau
***List*** là một kiểu Collection và là Interface dành cho kiểu danh sách.

***ArrayList*** là một danh sách kiểu mảng, là một lớp thực thể (concrete) của List.

-> *Trong Java ``List`` là interface, là giao diện bên ngoài chứ bản thân nó k có gì vì vậy nó không thể tạo ra đối tượng mới. Muốn sử dụng List bạn phải implement nó qua ``ArrayList`` và ``LinkList``.*

###2.Lúc nào cần dùng List, lúc nào cần dùng ArrayList

Nếu dùng ``List (List a = new ArrayList(); )`` sẽ có ưu điểm là bạn có thể chuyển đổi ``ArrayList`` sang ``Vector``, ``LinkedList`` dễ dàng thông qua các method có trong List interface, còn nếu dùng kiểu: ``ArrayList a = new ArrayList();`` thì bạn sẽ khó làm được điều này, bạn sẽ chỉ dùng được những method trong ``ArrayList``.

Điều đặc biệt quan trọng là nếu bạn dùng ``List``. Bạn không cần ép kiểu trong trường hợp dùng các obj khác nhau như ``ArrayList``
##IV.Một số method thường dùng trong Collections
Ví dụ: 
``List<Integer> list = new ArrayList<Integer>();``
| Method         | Mô tả                                                     | Ví dụ                              |
| -------------- | --------------------------------------------------------- | ---------------------------------- |
| sort()         | Sắp xếp các phần tử trong Collection theo thứ tự tăng dần | Collections.sort(list);            |
| reverse()      | Đảo ngược thứ tự các phần tử trong Collection             | Collections.reverse(list);         |
| swap()         | Hoán đổi vị trí của 2 phần tử trong Collection            | Collections.swap(list, 0, 1);      |
| binarySearch() | Tìm kiếm một phần tử trong Collection                     | Collections.binarySearch(list, 2); |
| max()          | Tìm phần tử có giá trị lớn nhất trong Collection          | Collections.max(list);             |
| min()          | Tìm phần tử có giá trị nhỏ nhất trong Collection          | Collections.min(list);             |
| frequency()    | Đếm số lần xuất hiện của một phần tử trong Collection     | Collections.frequency(list, 2);    |
| fill()         | Điền giá trị cho tất cả các phần tử trong Collection      | Collections.fill(list, 2);         |

**Method sort trong Collections**
Lớp Collections cung cấp các phương thức tĩnh(static) cho việc sắp xếp các phần tử của collection. Chúng ta có thể sắp xếp các phần tử của:

* String objects
* Wrapper class objects
* Người dùng tự định nghĩa(User-defined) class objects
Phương thức của Collections class dùng cho việc sắp xếp các phần tử của List:

``public void sort(List list): được sử dụng để sắp xếp các phần tử của List. Các phần tử của List phải là kiểu Comparable.``

***Note:*** String class và Wrapper classes implements Comparable interface vì vậy nên mặc định là nó có thể sắp xếp được.

*Ví dụ về sắp xếp List chứa các đối tượng String*

```c
import java.util.*;

public class Main {
    public static void main(String[] args) {
        ArrayList<String> list = new ArrayList<String>();
        list.add("Thiet");
        list.add("Thao");
        list.add("Hung");
        list.add("Anh");
        Collections.sort(list);
        for(String x : list) System.out.println(x);

    }

}
//Output
Anh
Hung
Thao
Thiet
```
*Ví dụ về sắp xếp List chứa các đối tượng Wrapper*
```c
import java.util.*;

class TestSort2 {
	public static void main(String args[]) {

		ArrayList al = new ArrayList();
		al.add(Integer.valueOf(201));
		al.add(Integer.valueOf(101));
		al.add(230);// nó sẽ được convert thành Integer.valueOf(230)

		Collections.sort(al);

		Iterator itr = al.iterator();
		while (itr.hasNext()) {
			System.out.println(itr.next());
		}
	}
}
//Output
101
201
230
```
**Java Comparable interface**
Java Comparable interface được sử dụng để chỉ ra thứ tự của các đối tượng Người dùng tự định nghĩa(User-defined). Interface này chỉ chứa duy nhất 1 phương thức tên là compareTo(Object). Nó cung cấp duy nhất 1 trình tự sắp xếp ví dụ như bạn chỉ có thể sắp các phần tử của đối tượng Nhân viên theo 'mã số' hoặc 'tên' hoặc tuổi',...

```c
class Employee implements Comparable<Employee> {
	int id;
	String name;
	int age;

	Employee(int id, String name, int age) {
		this.id = id;
		this.name = name;
		this.age = age;
	}

	public int compareTo(Employee employee) {
		if (age == employee.age)
			return 0;
		else if (age > employee.age)
			return 1;
		else
			return -1;
	}
}
```

```c
import java.util.*;

class TestSort3 {
	public static void main(String args[]) {
		ArrayList<Employee> al = new ArrayList<Employee>();
		al.add(new Employee(101, "Peter", 23));
		al.add(new Employee(106, "Marry", 29));
		al.add(new Employee(105, "John", 21));

		//Sắp xếp list employee
		Collections.sort(al);
		for (Employee st : al) {
			System.out.println(st.id + " " + st.name + " " + st.age);
		}
	}
}
//Output
105 John 21
101 Peter 23
106 Marry 29
```
**Java Comparator interface**
Java Comparator interface được sử dụng để chỉ ra thứ tự của các đối tượng Người dùng tự định nghĩa(User-defined). Nó định nghĩa 2 phương thức compare(Object obj1,Object obj2) và equals(Object element). Nó cung cấp nhiều trình tự sắp xếp ví dụ như bạn có thể sắp các phần tử của đối tượng Nhân viên theo 'mã số', 'tên', tuổi',...

``public int compare(Object obj1,Object obj2)``: so sánh 2 object với nhau
``public void sort(List list, Comparator c)``: phương thức của Collections được sử dụng để sắp xếp các phần tử của list dựa trên Comparator.

**Ví dụ về Bài 2 Buổi 1**
```c
//Sap xep cac giang vien theo ho ten voi Comparator interface
public static void nameSort()
    {
        Collections.sort(OGITList,new Comparator<OrganicInstructor>() {
            //@Override
            public int compare(OrganicInstructor x1, OrganicInstructor x2)
            {
                if(x1.name.compareTo(x2.name)<0) return -1;
                else if(x1.name.compareTo(x2.name)==0) return 0;
                else return 1;
            }
        });
        Collections.sort(VSITList,new Comparator<VisitorInstructor>() {
            //@Override
            public int compare(VisitorInstructor x1, VisitorInstructor x2)
            {
                if(x1.name.compareTo(x2.name)<0) return -1;
                else if(x1.name.compareTo(x2.name)==0) return 0;
                else return 1;
            }
        });
        System.out.println("Da sap xep giang vien theo ho ten");
    }
    //Sap xep cac giang vien theo he so luong voi Comparator interface
    public  static void coefficientsSalarySort()
    {
        Collections.sort(OGITList,new Comparator<OrganicInstructor>() {
            //@Override
            public int compare(OrganicInstructor x1, OrganicInstructor x2)
            {
                if(x1.coefficientsSalary<x2.coefficientsSalary) return -1;
                else if(x1.coefficientsSalary==x2.coefficientsSalary) return 0;
                else return 1;
            }
        });
        Collections.sort(VSITList,new Comparator<VisitorInstructor>() {
            //@Override
            public int compare(VisitorInstructor x1, VisitorInstructor x2)
            {
                if(x1.coefficientsSalary<x2.coefficientsSalary) return -1;
                else if(x1.coefficientsSalary==x2.coefficientsSalary) return 0;
                else return 1;
            }
        });
        System.out.println("Da sap xep giang vien theo he so luong");
    }
```

**Comparable VS Comparator**
Comparable và Comparator đều là những interfaces được sử dụng để sắp xếp các phần tử trong collection. Nhưng chúng có vài đặc điểm khác nhau như sau
| Comparable                                          | Comparator                                        |
| --------------------------------------------------- | ------------------------------------------------- |
| Cung cấp duy nhất 1 trình tự sắp xếp                | Cung cấp nhiều trình tự sắp xếp                   |
| Ảnh hưởng đến class gốc (Phải implement Comparable) | Không ảnh hưởng đến class gốc                     |
| Cung cấp phương thức compareTo()                    | Cung cấp phương thức compare()                    |
| Nằm trong java.lang(Không cần phải import)          | Nằm trong java.util(Phải import)                  |
| Sắp xếp sử dụng Collections.sort(List)              | Sắp xếp sử dụng Collections.sort(List,Comparator) |









