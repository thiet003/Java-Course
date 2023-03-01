## 1. Tổng quan về Java Swing

Java Swing là một phần của Java Foundation Classes (JFC) được sử dụng để tạo các ứng dụng window-based. Nó được xây dựng trên API AWT (Abstract Windowing Toolkit) và được viết hoàn toàn bằng Java.

Không giống như AWT, Java Swing cung cấp các thành phần không phụ thuộc vào nền tảng và nhẹ hơn.

Gói javax.swing cung cấp các lớp cho java swing API như JButton, JTextField, JTextArea, JRadioButton, JCheckbox, JMenu, JColorChooser, v.v.

**Phân cấp các lớp Java Swing**

![example](https://viettuts.vn/images/java-swing/phan-cap-cac-lop-java-swing.jpg)

## 2. JFrame trong Java SWing

JFrame là một container(Nơi chứa và sắp xếp các component khác của Java Swing, có thể là các container khác) trong ứng dụng Java Swing, nó được dùng để chứa và sắp xếp các phần con như Button, Label, TextField, etc.

***Lớp JFrame này có các constructor sau:***
1. JFrame(): Xây dựng một Frame mới, ban đầu là không nhìn thấy (invisible).

2. JFrame(GraphicsConfiguration gc): Tạo một Frame trong GraphicsConfiguration đã cho của một thiết bị màn hình và một title trống.

3. JFrame(String title): Tạo một Frame mới, ban đầu là không nhìn thấy (invisible) với title đã cho.

4. JFrame(String title, GraphicsConfiguration gc): Tạo một Frame với title đã cho và GraphicsConfiguration đã cho của một thiết bị màn hình.

Mặc định khi một JFrame được khởi tạo xong nó sẽ ở trạng thái ẩn, tất là người dùng sẽ không thấy được. Nếu muốn hiển thị JFrame này đến người dùng chúng ta cần gọi đến setVisible(boolean visible) với giá trị truyền vào:

* True – JFrame sẽ hiện thị ra giao diện.
* False – JFrame sẽ bị ẩn đi.

**Chiều cao, rộng và vị trí của JFrame trên màn hình Desktop**

Mặc định khi JFrame được khởi tạo thì vị trí xuất hiện của nó trên mành hình Desktop nằm ở phía trên bên trái cùng của màn hình. Kích thước tuỳ thuộc vào các component chứa trong nó.

Để thay đổi kích thước và vị trí mặc định của JFrame, chúng ta có thể sử dụng:

* **setSize(width, height)** – Chỉ định chiều rộng vào chiều cao của JFrame
* **setLocation(int x, int y)** – Chỉ định toạ độ của JFrame trên màn hình theo 2 trục X, Y
* **setBounds(int x, int y, int width, int height)** – Cách sử dụng nhanh, gộp 2 hàm ở trên lại 

***Ví dụ về sử dụng JFrame trong JavaSwing***

```c

import javax.swing.*;

public class Demo {
    public static void main(String[] args) {
        JFrame f = new JFrame("Demo");//Khởi tạo 1 JFrame với tiêu đề Demo
        f.setBounds(100,100,500,500);//xét vị trí cho frame f với x=100,y=100, width=500,height=500
        f.setVisible(true);// hiện JFrame lên màn hình
    }
}
```

## 3. JTextField trong Java Swing 

JTextField là một component có lẽ cũng được sử dụng rất nhiều trong các ứng dụng Java Swing cùng với Button, Label, CheckBox, etc.

JTextField là một component cho phép nhập và chỉnh sữa đoạn văn bản trên cùng một dòng vì thế nó thường phù hợp cho việc nhập, chỉnh sửa các thông tin dạng ngắn gọn, mang đại ý như là email, password, tên công ty, tên sinh viên, etc.

### Tạo JTextField

Để khởi tạo một JTextField trong Java Swing rất đơn giản với cú pháp sau:

```c
JTextField jTextField = new JTextField();
```

Để khởi tạo một JTextField với đoạn văn bản có sẵn thì có thể làm như sau:

```c
JTextField jTextField = new JTextField("Default Text");
```

Trong JTextField có một thuộc tính gọi là columns được dùng để tính toán độ rộng của JTextField, mặc định nó là 0 nên khi không có dữ liệu thì kích thước của nó sẽ rất nhỏ. Để chỉ định columns cho JTextField chúng ta có thể khởi tạo như sau:

```c
JTextField textField = new JTextField(20);
```

HOMEJAVACách Tạo, Và Xử Lý Sự Kiện Của JTextField Trong Java Swing
Tags:Java SwingCách tạo, và xử lý sự kiện của JTextField trong Java Swing Deft November 23, 2020
Mục lục [ẩn]

1 Tạo JTextField
2 Lấy String trong JTextField
3 Tạo Tooltip cho JTextField
4 Focus vào một JTextField
5 Xử lý sự kiện trong JTextField
6 Select các ký tự trong JTextFiled
7 Tuỳ biến JTextField
JTextField là một component có lẽ cũng được sử dụng rất nhiều trong các ứng dụng Java Swing cùng với Button, Label, CheckBox, etc.

JTextField là một component cho phép nhập và chỉnh sữa đoạn văn bản trên cùng một dòng vì thế nó thường phù hợp cho việc nhập, chỉnh sửa các thông tin dạng ngắn gọn, mang đại ý như là email, password, tên công ty, tên sinh viên, etc. Còn những thông tin dài hơn thì chúng ta có thể sử dụng JTextArea cho phép nhập, chỉnh sửa dữ liệu trên nhiều dòng.

Tạo JTextField
Để khởi tạo một JTextField trong Java Swing rất đơn giản với cú pháp sau:

JTextField jTextField = new JTextField();
Để khởi tạo một JTextField với đoạn văn bản có sẵn thì có thể làm như sau:

JTextField jTextField = new JTextField("Default Text");
Trong JTextField có một thuộc tính gọi là columns được dùng để tính toán độ rộng của JTextField, mặc định nó là 0 nên khi không có dữ liệu thì kích thước của nó sẽ rất nhỏ. Để chỉ định columns cho JTextField chúng ta có thể khởi tạo như sau:

JTextField textField = new JTextField(20);
Note:

Nếu JTextField được khởi tạo mà không được cung cấp đoạn văn bản ban đầu thì giá trị này sẽ là null. Các bạn nhớ lưu ý khi thao tác nếu không có thể bị NullPointerException.
Nếu columns không được cung cấp lúc khởi tạo thì giá trị mặc định nó là 0, chiều rộng của JTextField sẽ được tính dựa vào văn bản. Nếu cả 2 văn bản và columns không được cung cấp thì chiều rộng của nó sẽ nhỏ tối đa.
Ví dụ tạo 2 JTextFiled trong JFrame

import javax.swing.*;
public class JTextFieldExample {
    public static void main(String[] agrs) {
        JFrame mainFrame = new JFrame("JtextField Exampke");
        mainFrame.setSize(400, 150);
        JPanel panel = new JPanel();
        // khoi tao JTextField
        JTextField jTextField = new JTextField(10);
        JTextField jTextField1 = new JTextField(20);
        panel.add(jTextField);
        panel.add(jTextField1);
        mainFrame.add(panel);
        mainFrame.setVisible(true);
    }
}


Lấy String trong JTextField
Để lấy giá trị của String trong JTextField chúng ta có thể sử dụng getText() method.

```c
String content = textField.getText()
```

### Tạo Tooltip cho JTextField

Đôi khi đoạn văn bản của chúng ta quá nhiều và không thể hiển thị đầy đủ trên JTextField, hay bạn muốn hiển thị một thông điệp gì đó khi người dùng rê chuột vào một JTextField thì các bạn có thể sử dụng setToolTipText() method
```c
public class JTextFieldExample {
    public static void main(String[] agrs) {
        JFrame mainFrame = new JFrame("JtextField Exampke");
        mainFrame.setSize(400, 150);
        JPanel panel = new JPanel();
        JTextField jTextField = new JTextField(10);
        jTextField.setToolTipText("Tooltip here!");
        panel.add(jTextField);
        mainFrame.add(panel);
        mainFrame.setLocationRelativeTo(null);
        mainFrame.setVisible(true);
    }
}
```

![example](https://shareprogramming.net/wp-content/uploads/2020/11/Screen-Shot-2020-11-23-at-6.36.53-PM.png)


Có thể chỉ định font chữ, kích thước, màu nền

```c
textField.setFont(new java.awt.Font("Arial", Font.ITALIC | Font.BOLD, 12));
textField.setForeground(Color.BLUE);
textField.setBackground(Color.YELLOW);
```

***Ví dụ về JTextField tring JavaSwing***

```c
import javax.swing.*;
import javax.swing.table.TableColumn;
import javax.swing.text.TabableView;
import javax.swing.text.TableView;

public class Demo {
    public static void main(String[] args) {
        JFrame f = new JFrame("Demo");

        f.setBounds(100,100,500,500);
        JTextField text = new JTextField(20);
        text.setBounds(50,10,50,20);
        text.setToolTipText("Nhập ở đây");
        f.add(text);
        f.setLayout(null);
        f.setVisible(true);
    }
}
```

## 4. JButton trong JavaSwing

Button được biến đến như là một control được sử dụng rất nhiều trong Java Swing cùng với Label, TextField, etc.

***Cách tạo Button trong Java Swing***

Để khởi tạo một Button trong Java Swing chúng ta có thể làm như sau:

```c
JButton btn = new JButton("Click Button");
```
Một số phương thức được sử dụng phổ biến của của lớp AbstractButton

1. public void setText(String s): được sử dụng để thiết lập text đã cho trên button.

2. public String getText(): được sử dụng để trả về text của button.
3. public void setBounds(int x, int y, int w, int h): được sử dụng để xét vị trí kích cỡ của button.

**Xử lý sự kiện trong Button**

Để xử lý sự kiện khi người dùng nhấp vào Button chúng ta có thể làm như sau:

```c
button.addActionListener(new ActionListener() {
    @Override
    public void actionPerformed(ActionEvent evt) {
        // do everything here...
    }
}); 
```

Tuỳ biến giao diện Button
Một số thao thác thường dùng với Button như thay đổi màu nền với setBackground().

```c
button.setBackground(Color.YELLOW);
```

Hay xác định Font, cỡ chữ

```c
button.setFont(new java.awt.Font("Arial", Font.BOLD, 14));
```

## 5. Jpanel trong JavaSWing

JPanel là một container trong Swing dùng để chứa và sắp các các component khác bên trong nó. Nhiệm vụ chính của JPanel là tổ chức các thành phần, nhiều bố cục khác nhau có thể được thiết lập trong JPanel giúp tổ chức các thành phần tốt hơn, tuy nhiên nó không có thanh tiêu đề như JFrame.

***Khởi tạo JPanel ***

Chúng ta có một số hàm khởi tạo để tạo JPanel như sau:

* JPanel() : Khởi tạo JPanel với  flow layout.
* JPanel(LayoutManager l) : Khởi tạo một JPanel với Layout được chỉ định.
* JPanel(boolean isDoubleBuffered) : tạo một JPanel mới với một chiến lược đệm cụ thể
* JPanel(LayoutManager l, boolean isDoubleBuffered) : Khởi tạo một JPanel với Layout và chiếm lược đệm cụ thể.

***Các hàm thường xuyên sử dụng*** 

1. add(Component c) : Thêm một component vào JPanel
2. setLayout(LayoutManager l) :  Điều chỉnh lại layout của JPanel
3. updateUI() : cập nhật thuộc tính giao diện người dùng với một giá trị từ giao diện hiện tại
4. setUI(PanelUI ui) : thiết lập giao diện của một đối tượng hiển thị thành phần này.
5. getUI() : trả về giao diện đối tượng hiển thị thành phần này.
paramString() : trả về đại diện chuỗi của JPanel này.
6. getUIClassID() : trả về tên của lớp Giao diện hiển thị thành phần này.
7. getAccessibleContext() : ấy AccessibleContext được liên kết với JPanel này.

**Ví dụ JPanel**

```c
import java.awt.event.*; 
import java.awt.*; 
import javax.swing.*; 
class solution extends JFrame { 
  
    // JFrame 
    static JFrame f; 
  
    // JButton 
    static JButton b, b1, b2; 
  
    // label to display text 
    static JLabel l; 
  
    // main class 
    public static void main(String[] args) 
    { 
        // create a new frame to store text field and button 
        f = new JFrame("panel"); 
  
        // create a label to display text 
        l = new JLabel("panel label"); 
  
        // create a new buttons 
        b = new JButton("button1"); 
        b1 = new JButton("button2"); 
        b2 = new JButton("button3"); 
  
        // create a panel to add buttons 
        JPanel p = new JPanel(); 
  
        // add buttons and textfield to panel 
        p.add(b); 
        p.add(b1); 
        p.add(b2); 
        p.add(l); 
  
        // setbackground of panel 
        p.setBackground(Color.red); 
  
        // add panel to frame 
        f.add(p); 
  
        // set the size of frame 
        f.setSize(300, 300); 
  
        f.show(); 
    } 
} 
```
![example](https://shareprogramming.net//wp-content/uploads/2020/11/6000-300x283-1.png)

## 6. JMenu trong JavaSwing

Menu là một trong những thành phần cơ bản của một ứng dụng Java Swing, đây là nơi chứa tất cả các phím chức năng của ứng dụng. Để tạo một menu trong Java Swing chúng ta phải sử dụng các class sau:

1. JMenuBar – Tạo một menu bar.
2. JMenu – Tạo menu.
3. JMenuItem – Các phần tử con trong JMenu.
4. JMenuItemListener – Tạo các trình xử lý sự kiện.

**Constructor**

Để khởi tạo JMenuBar và JMenu chúng ta có các constructor cơ bản sau:

* JMenuBar() : Tạo một MenuBar.
* JMenu() : Tạo một Menu rỗng.
* JMenu(String name) : Tạo một menu với tên được chỉ định.
* JMenu(String name, boolean b) : Tạo menu với tên được chỉ định, và boolean chỉ định menu có thể kéo ra khỏi menu bar hay không.

**Một số hàm thường xuyên sử dụng:**

1. add(JMenu c) : Thêm một menu vào MenuBar.
2. add(Component c) : Thêm một component vào JMenu.
3. add(Component c, int index) :Thêm một component vào JMenu tại vị trí index.
4.add(JMenuItem menuItem) : Thêm một MenuItem vào cuối menu.
5. add(String s) : Thêm một menu mới với tên được chỉ định và gắn vào cuối menu.
6. getItem(int index) :Trả về MenuItem tại vị trí Index.

***Ví dụ tạo Menu đơn giản***

```c
import java.awt.Container;
import java.awt.FlowLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

import javax.swing.*;

class SimpleMenus extends JApplet {
    private JTextField t = new JTextField(15);

    private ActionListener al = new ActionListener() {
        public void actionPerformed(ActionEvent e) {
            t.setText(((JMenuItem) e.getSource()).getText());
        }
    };

    private JMenu[] menus = {
            new JMenu("Winken"),
            new JMenu("Blinken"),
            new JMenu("Nod")};

    private JMenuItem[] items = {
            new JMenuItem("Fee"),
            new JMenuItem("Fi"),
            new JMenuItem("Fo"),
            new JMenuItem("Zip"),
            new JMenuItem("Zap"),
            new JMenuItem("Zot"),
            new JMenuItem("Olly"),
            new JMenuItem("Oxen"),
            new JMenuItem("Free")};

    public void init() {
        for (int i = 0; i < items.length; i++) {
            items[i].addActionListener(al);
            menus[i % 3].add(items[i]);
        }
        JMenuBar mb = new JMenuBar();
        for (int i = 0; i < menus.length; i++) {
             mb.add(menus[i]);
        }

        setJMenuBar(mb);
        Container cp = getContentPane();
        cp.setLayout(new FlowLayout());
        cp.add(t);
    }

    public static void main(String[] args) {
        run(new SimpleMenus(), 200, 200);
    }

    public static void run(JApplet applet, int width, int height) {
        JFrame frame = new JFrame();
        frame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);
        frame.getContentPane().add(applet);
        frame.setSize(width, height);
        applet.init();
        applet.start();
        frame.setLocationRelativeTo(null);
        frame.setVisible(true);

    }
}
```

## 7. JLabel trong JavaSwing

Lớp JLabel trong Java Swing có thể hiển thị hoặc text, hoặc hình ảnh hoặc cả hai. Các nội dung của Label được gán bởi thiết lập căn chỉnh ngang và dọc trong khu vực hiển thị của nó. Theo mặc định, các label được căn chỉnh theo chiều dọc trong khu vực hiển thị. Theo mặc định, text-only label là căn chỉnh theo cạnh, image-only label là căn chỉnh theo chiều ngang.

**Tạo Label trong Java Swing**

Chúng ta có thể tạo một Label trong Swing thông qua các constructor sau:

```c
public JLabel ()
public JLabel (java.lang.String text)
public JLabel (java.lang.String text, int horizontalAlignment)
public JLabel (Icon image)
public JLabel (Icon image, int horizontalAlignment)
public JLabel (Java.lang.String text, Icon icon, int horizontalAlignment)
```

Dưới đây là đoạn code tạo Label với một String và icon:

```c
JLabel nameLabel  = new JLabel("Name:");
JLabel warningImage  = new JLabel(new Icon("C:/images/ok.gif"));
```

Nếu Label không được gán một đoạn văn bảng ngay từ đầu thì các bạn có thể gán sau đó với setText() method, hàm này cũng có thể dùng để cập nhật văn bản hiển thị của Label.

```c
import java.awt.FlowLayout;
import javax.swing.JFrame;
import javax.swing.JLabel;

public class Main {
  public static void main(String args[]) {
    JFrame f = new JFrame("Label Demo");
    f.setLayout(new FlowLayout());
    f.setSize(300, 200);
    f.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
    
    JLabel label= new JLabel("https://shareprogramming.net//");
    f.add(label);
    f.setVisible(true);
  }
}
```

**Căn chỉnh văn bản**

Chúng ta có thể quản lý vị trí xuất hiện của văn bản trong Label. Ví dụ căn chỉnh label hiển thị giữa theo chiều dọc và chiều ngang.

```c
label.setHorizontalAlignment(JLabel.CENTER);
label.setVerticalAlignment(JLabel.CENTER);
```

**Tạo Border cho Label**

Chúng ta có thể tạo Border cho Label cách đơn giản như sau:

```c
JLabel label= new JLabel("A default label");
Border border = BorderFactory.createLineBorder(Color.BLACK);
label.setBorder(border);
```

## 8. JComboBox trong JavaSwing

JComboBox là một thành phần của Java Swing kế thừa từ JComponent class, nó cho phép hiển thị một popup menu gồm một danh sách các phần tử là các tuỳ chọn, người dùng có thể chọn một trong số những tuỳ chọn này. 

**Khởi tạo JComboBox**

Để khởi tạo một JComboBox chúng ta có thể sử dụng một số constructor sau:

* **JComboBox()** – Khởi tạo một JComboBox rỗng.
* **JComboBox(ComboBoxModel M)** – Khởi tạo JComboBox với các phần tử được cung cấp bởi ComboBoxModel.
* **JComboBox(E [ ] arr)** – Khởi tạo JComboBox với các phần tử từ mảng arr được chỉ định.
* **JComboBox(Vector items)** – Khởi tạo JComboBox với các phần tử từ Vector items được chỉ định.

***Một số method thường sử dụng trong JComboBox***

JComboBox cung cấp rất nhiều method để chúng ta sử dụng, trong phần này chúng ta sẽ cùng điểm qua một số method thường sử dụng nhất:

* **addItem(E item)** – Thêm một phần tử vào JComboBox.
* **addItemListener( ItemListener l)** – Thêm ItemListener vào JComboBox.
* **getItemAt(int i)** – Trả về phần tử tạo vị trí i trong JCombobox.
* **getItemCount()** – Trả về số lượng phần tử trong JComboBox.
* **getSelectedItem()** – Trả về phần tử đang được người dùng lựa chọn.
* **removeItemAt(int i)** – Xoá phần tại vị trí i được chỉ định.
* **removeAllItems()** – Xoá tất cả các phần tử trong JComboBox.
* **setPopupVisible(boolean v)** – Hiển thị popup các phần tử trong JComboBox.
* **setMaximumRowCount(int count)** – Đặt số hàng tối đa mà JComboBox hiển thị.
* **isPopupVisible()** – Kiểm tra xem popup có đang hiển thị hay không.

**Ví dụ đơn giản về JComboBox**

```c
import javax.swing.*;
import java.awt.*;
import java.awt.event.ItemEvent;
import java.awt.event.ItemListener;

class JComboBoxExample {

    public static void main(String[] args) {
        JFrame f = new JFrame("frame");
        f.setLayout(new FlowLayout());
        String s1[] = {"Ha Noi", "Dang Nang", "Ho Chi Minh", "Hue", "Tien Giang"};

        JLabel l = new JLabel("Chon thanh pho ");
        JLabel l1 = new JLabel("Ha noi duoc chon");
        l.setForeground(Color.red);
        l1.setForeground(Color.blue);

        JComboBox c1 = new JComboBox(s1);
        c1.addItemListener(new ItemListener() {
            @Override
            public void itemStateChanged(ItemEvent e) {
                if (e.getSource() == c1) {
                    l1.setText(c1.getSelectedItem() + " duoc chon");
                }
            }
        });
        JPanel p = new JPanel();

        p.add(l);

        p.add(c1);

        p.add(l1);

        f.add(p);
        f.setSize(450, 300);

        f.setVisible(true);
    }

}
```

![example](https://shareprogramming.net/wp-content/uploads/2020/11/Screen-Shot-2020-11-29-at-12.29.05-PM.png)
