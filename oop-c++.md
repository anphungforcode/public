***Keywords:*** hướng đối tượng c++,

## Reference
1. Nguyễn Văn Hiếu, [*Lập Trình Hướng Đối Tượng Là Gì?*](https://nguyenvanhieu.vn/lap-trinh-huong-doi-tuong-cpp/), nguyenvanhieu.vn (2023)
2. Diệu Hương, [*Lập trình hướng đối tượng c++ cho người mới bắt đầu*](https://mindx.edu.vn/blog/lap-trinh-huong-doi-tuong-c), mindx.edu.vn (2023)


## Table of Contents
- [Object-oriented programming (OOP) in C++](#object-oriented-programming-oop-in-c)
  - [1. Đối tượng (Object)](#1-đối-tượng-object)
    - [Phân biệt thuộc tính và phương thức\*\*](#phân-biệt-thuộc-tính-và-phương-thức)
  - [2. Lớp (Class)](#2-lớp-class)
  - [3. Các đặc điểm của lập trình hướng đối tượng](#3-các-đặc-điểm-của-lập-trình-hướng-đối-tượng)
    - [3.1. Tính trừu tượng (Abstraction)](#31-tính-trừu-tượng-abstraction)
    - [3.2. Tính đóng gói (Encapsulation)](#32-tính-đóng-gói-encapsulation)
    - [3.3. Tính đa hình (Polymorphism)](#33-tính-đa-hình-polymorphism)
    - [Phân biệt Compile time Polymorphism và Runtime Polymorphism](#phân-biệt-compile-time-polymorphism-và-runtime-polymorphism)
      - [Ép kiểu trong Compile time Polymorphism khi cùng số lượng tham số nhưng không đúng kiểu dữ liệu](#ép-kiểu-trong-compile-time-polymorphism-khi-cùng-số-lượng-tham-số-nhưng-không-đúng-kiểu-dữ-liệu)
    - [3.4. Tính kế thừa (Inheritance)](#34-tính-kế-thừa-inheritance)
  - [FAQ](#faq)
      - [Lập trình hướng đối tượng là gì?](#lập-trình-hướng-đối-tượng-là-gì)
      - [Đối tượng là gì?](#đối-tượng-là-gì)
      - [Class là gì?](#class-là-gì)
      - [Nguyên tắc của lập trình hướng đối tượng](#nguyên-tắc-của-lập-trình-hướng-đối-tượng)
      - [Interface là gì?](#interface-là-gì)
      - [So sánh lập trình hướng đối tượng và lập trình hướng thủ tục](#so-sánh-lập-trình-hướng-đối-tượng-và-lập-trình-hướng-thủ-tục)


# Object-oriented programming (OOP) in C++
![Alt text](/images/oops.png)

## 1. Đối tượng (Object)
Một đối tượng gồm 2 thành phần:
- Thuộc tính (Attribute)
- phương thức (Method)
  - this
  - self

### Phân biệt thuộc tính và phương thức**
Thuộc tính là những đặc điểm, thông tin của đối tượng.

Phương thức là những hành động mà đối tượng đó có thể thực hiện

**Ví dụ:** 
Object: People
-> Thuộc tính: Tên, tuổi, màu da, ...
-> Phương thức: Đi, nói, ăn, ...



## 2. Lớp (Class)

Một lớp cũng có 2 thành phần:
- Thuộc tính
- Phương thức

> Lớp cũng có thể được dùng để định nghĩa một kiểu dữ liệu mới

Lập trình hướng đối tượng có 4 tính chất:
1. Tính trừu tượng (Abstraction)
2. Tính đóng gói (Encapsulation)
3. Tính đa hình (Polymorphism)
4. Tính kế thừa (Inheritance)


## 3. Các đặc điểm của lập trình hướng đối tượng
![Alt text](/images/oop.png)
<!-- *Các đặc điểm của lập trình hướng đối tượng* -->

### 3.1. Tính trừu tượng (Abstraction)
Nhằm mục đích làm giảm sự phức tạp bằng cách ẩn đi các chi tiết không liên quan trực tiếp tới người dùng ( là lập trình viên). Cho phép người dùng vẫn thực hiện được các công việc cần thiết dựa trên một thực thể trừu tượng (hộp đen) được cung cấp mà không cần hiểu bên trong.

**Ví dụ:**
...
### 3.2. Tính đóng gói (Encapsulation)

![Alt text](/images/encapsulation.png)
<!-- *Tính đóng gói* -->
Tính đóng gói là sự kết hợp một bộ các dữ liệu liên quan đến nhau cùng với một bộ các hàm/ phương thức hoạt động dựa trên bộ dữ liệu đó, rồi đóng gói tất cả vào trong lớp (class).

**Ví dụ về tính đóng gói:**
```cpp
class connguoi {
private:
    string ten;
    int tuoi;
public:
    void input()
    {
        cout << "Nhap Ten: ";
        fflush(stdin);
        getline(cin, this->ten);
        cout << "Nhap Tuoi: ";
        cin >> tuoi;
    }

    void output()
    {
        cout << "Ten: " << this->ten << endl;
        cout << "Tuoi: " << this->tuoi << endl;
    }
};
```

### 3.3. Tính đa hình (Polymorphism)
Tính đa hình có 2 dạng
- Compile time Polymorphism (**overloading**)
- Runtime Polymorphism (**overriding**) - **Implementation**

### Phân biệt Compile time Polymorphism và Runtime Polymorphism
Compile time Polymorphism là khi trong class có các hàm cùng tên, nhưng khác số lượng tham số hoặc kiểu dữ liệu của tham số. 
> Khi gọi hàm thì trong quá trình biên dịch, compiler sẽ quyết định hàm nào dựa trên số lượng tham số và kiểu dữ liệu của tham số truyền vào hàm.

Runtime Polymorphism là khi tạo ra nhiều biến thể, không phải được định nghĩa bởi lớp đó, mà bởi các lớp con của nó.
> ...

**Ví dụ về overloading:**
```cpp
#include <bits/stdc++.h>
using namespace std;

class Data
{
public:
    void print(int i)
    {
        cout << "Print int: " << i << endl;
    }

    void print(float i)
    {
        cout << "Print float: " << i << endl;
    }

    void print(string i)
    {
        cout << "Print string: " << i << endl;
    }

}

int main()
{
    Data obj;
    obj.print(1);
    obj.print(2.5);
    obj.print("Lap Trinh Khong Kho");

    return 0;
}
```

**Ví dụ về overriding:**
...


#### Ép kiểu trong Compile time Polymorphism khi cùng số lượng tham số nhưng không đúng kiểu dữ liệu
...

### 3.4. Tính kế thừa (Inheritance)
Đối tượng 

**Ví dụ:**
```cpp
Class People {
  - ten
  - tuoi
}

Class Student kế thừa People {
  // Student vẫn có các thuộc tính ten, tuoi kế thừa từ People
  - student_code
  - GPA
}
```



## FAQ
#### Lập trình hướng đối tượng là gì?
...
#### Đối tượng là gì?
Đối tượng là một thực thể (instance) của class, là một thực thể có đặc điểm và hành vi.

#### Class là gì?
Class là khuôn mẫu để tạo ra đối tượng.

#### Nguyên tắc của lập trình hướng đối tượng
...


![Alt text](/images/oops_2.png)

https://viblo.asia/p/solid-5-nguyen-tac-cua-thiet-ke-huong-doi-tuong-WAyK8LWEKxX

design pattern


#### Interface là gì?
#### So sánh lập trình hướng đối tượng và lập trình hướng thủ tục

OOP | POP
--|--
phát triển và bảo trì dễ dàng hơn | không dễ quản lý nếu dự án lớn và code ngày càng nhiều
ẩn dữ liệu đi | dữ liệu toàn cục có thể truy cập từ bất cứ đâu
cung cấp khả năng mô tả sự kiện trong thế giới thực hiệu quả |











