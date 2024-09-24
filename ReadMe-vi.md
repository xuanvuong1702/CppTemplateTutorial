## Hướng dẫn nâng cao về Template C++ <!-- omit in toc -->
===============

Mục lục được tạo bởi tiện ích mở rộng VSCode [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one).
- [1. Lời mở đầu](#1-lời-mở-đầu)
  - [1.1. Giới thiệu về C++: Phức tạp hơn bạn nghĩ, nhưng đơn giản hơn bạn tưởng](#11-giới-thiệu-về-c-phức-tạp-hơn-bạn-nghĩ-nhưng-đơn-giản-hơn-bạn-tưởng)
  - [1.2. Đối tượng độc giả](#12-đối-tượng-độc-giả)
  - [1.3. Bản quyền](#13-bản-quyền)
  - [1.4. Môi trường biên dịch được đề xuất](#14-môi-trường-biên-dịch-được-đề-xuất)
  - [1.5. Quy ước trình bày](#15-quy-ước-trình-bày)
    - [1.5.1. Mã ví dụ](#151-mã-ví-dụ)
    - [1.5.2. Trích dẫn](#152-trích-dẫn)
  - [1.6. Ý kiến, đề xuất, phản hồi, bổ sung, kế hoạch viết](#16-ý-kiến-đề-xuất-phản-hồi-bổ-sung-kế-hoạch-viết)
- [2. Cú pháp cơ bản của Template](#2-cú-pháp-cơ-bản-của-template)
  - [2.1. Template là gì](#21-template-là-gì)
  - [2.2. Cú pháp cơ bản của Class Template](#22-cú-pháp-cơ-bản-của-class-template)
    - [2.2.1. “Lớp Template” hay “Class Template”](#221-lớp-template-hay-class-template)
    - [2.2.2. Khai báo và định nghĩa Class Template và biến thành viên](#222-khai-báo-và-định-nghĩa-class-template-và-biến-thành-viên)
    - [2.2.3. Sử dụng Template](#223-sử-dụng-template)
    - [2.2.4. Định nghĩa hàm thành viên của Class Template](#224-định-nghĩa-hàm-thành-viên-của-class-template)
  - [2.3. Giới thiệu về Function Template](#23-giới-thiệu-về-function-template)
    - [2.3.1. Khai báo và định nghĩa Function Template](#231-khai-báo-và-định-nghĩa-function-template)
    - [2.3.2. Sử dụng Function Template](#232-sử-dụng-function-template)
  - [2.4. Kiểu số nguyên cũng có thể là tham số Template](#24-kiểu-số-nguyên-cũng-có-thể-là-tham-số-template)
  - [2.5. Hình thức và chức năng của Template là thống nhất](#25-hình-thức-và-chức-năng-của-template-là-thống-nhất)
- [3. Cơ bản về lập trình meta template](#3-cơ-bản-về-lập-trình-meta-template)
  - [3.1. Lập trình, lập trình meta, lập trình meta template](#31-lập-trình-lập-trình-meta-lập-trình-meta-template)
  - [3.2. If-Then-Else trong thế giới Template: Chuyên môn hóa và chuyên môn hóa một phần của Class Template](#32-if-then-else-trong-thế-giới-template-chuyên-môn-hóa-và-chuyên-môn-hóa-một-phần-của-class-template)
    - [3.2.1. Thực thi mã dựa trên kiểu](#321-thực-thi-mã-dựa-trên-kiểu)
    - [3.2.2. Chuyên môn hóa](#322-chuyên-môn-hóa)
    - [3.2.3. Chuyên môn hóa: Một số vấn đề khác](#323-chuyên-môn-hóa-một-số-vấn-đề-khác)
  - [3.3. Suy luận khi sử dụng](#33-suy-luận-khi-sử-dụng)
    - [3.3.1. Lỗi cú pháp bị bỏ qua](#331-lỗi-cú-pháp-bị-bỏ-qua)
    - [3.3.2. Tra cứu tên: I am who I am](#332-tra-cứu-tên-i-am-who-i-am)
    - [3.3.3. Từ khóa typename “dư thừa”](#333-từ-khóa-typename-dư-thừa)
  - [3.4. Tóm tắt chương](#34-tóm-tắt-chương)
- [4. Hiểu sâu hơn về chuyên môn hóa và chuyên môn hóa một phần](#4-hiểu-sâu-hơn-về-chuyên-môn-hóa-và-chuyên-môn-hóa-một-phần)
  - [4.1. Hiểu đúng về chuyên môn hóa một phần](#41-hiểu-đúng-về-chuyên-môn-hóa-một-phần)
    - [4.1.1. So sánh chuyên môn hóa một phần và quá tải hàm](#411-so-sánh-chuyên-môn-hóa-một-phần-và-quá-tải-hàm)
    - [4.1.2. Tham số Template có độ dài không xác định](#412-tham-số-template-có-độ-dài-không-xác-định)
    - [4.1.3. Tham số mặc định của Template](#413-tham-số-mặc-định-của-template)
  - [4.2. Thuốc hối hận: SFINAE](#42-thuốc-hối-hận-sfinae)
  - [4.3. Concept: Mô tả trực tiếp các ràng buộc đối với tham số Template](#43-concept-mô-tả-trực-tiếp-các-ràng-buộc-đối-với-tham-số-template)
    - [4.3.1. Concept giải quyết vấn đề gì](#431-concept-giải-quyết-vấn-đề-gì)
    - [4.3.2. Giới thiệu về Concept](#432-giới-thiệu-về-concept)
- [5. Chương chưa hoàn thành](#5-chương-chưa-hoàn-thành)

# 1. Lời mở đầu

## 1.1. Giới thiệu về C++: Phức tạp hơn bạn nghĩ, nhưng đơn giản hơn bạn tưởng

C++ dường như đã trở thành một ngôn ngữ lập trình gây tranh cãi từ ngày nó được thế giới biết đến. Xung quanh nó là vô số lời khen ngợi và chê bai. Khi tôi tiết lộ ý định viết bài này trên Weibo, tôi cũng nhận được nhiều bình luận trái chiều. Là một ngôn ngữ lập trình, việc sở hữu nhiều người dùng vừa yêu vừa ghét, vừa sử dụng vừa sợ hãi nó, cũng là một điều kỳ lạ trong rừng ngôn ngữ.

Lý do tại sao C++ trở thành một ngôn ngữ đa tầng, đa dạng về cấu trúc và cú pháp phức tạp là do nhiều nguyên nhân. Trong cuốn sách "The Design and Evolution of C++", Bjarne đã giải thích chi tiết lý do tại sao C++ trở thành như ngày nay (C++98/03). Đây cũng là cuốn sách mà tôi và Trần Tử Hãn luôn giới thiệu cho những người mới bắt đầu. Qua đó, bạn có thể hiểu được phần nào lý do tại sao nhiều yếu tố cú pháp của C++ trở nên phức tạp như hiện nay là do bất khả kháng.

Là một trong những tính năng đặc sắc nhất của C++, Template, với cú pháp và ngữ nghĩa gần như thần bí, đương nhiên trở thành nỗi ám ảnh của người mới bắt đầu. Thậm chí, nhiều người đã làm việc nhiều năm vẫn còn e ngại với phần Template của C++. Trong hầu hết các tiêu chuẩn mã hóa, Template, giống như đa kế thừa, trở thành vùng cấm của lập trình viên thông thường (không phải người viết thư viện). Thậm chí, Boost, với việc sử dụng Template khá nhiều, cũng trở thành “mục tiêu công kích”.

Nhưng trên thực tế, Template C++ không phức tạp như bạn nghĩ. Chúng ta chỉ cần thay đổi góc nhìn: Trong C++03, bản thân Template có thể được coi là một "ngôn ngữ" độc lập. Nó có "giá trị", "hàm", "biểu thức" và "câu lệnh". Ngoài cú pháp hơi khó hiểu, nó không có con trỏ cũng như mảng, càng không có kế thừa và đa hình phức tạp như trong C++. Có thể nói, nó đơn giản hơn nhiều so với ngôn ngữ C. Nếu chúng ta học Template như một ngôn ngữ, thì chỉ cần bỏ ra một chút thời gian so với việc học lập trình hướng đối tượng là có thể nắm bắt được. Theo cách suy nghĩ này, hầu hết các kỹ thuật xuất hiện trong các sách về Template đều có thể được hiểu một cách dễ dàng.

Hãy cùng điểm lại lịch sử của Template. Năm 1987, khái niệm lập trình tổng quát (Generic Programming) đã được đưa vào C++, dẫn đến sự ra đời của cú pháp Template sau này. Có thể nói, cú pháp Template ngay từ đầu đã được tạo ra để cung cấp cơ chế lập trình tổng quát trong C++. Năm 1992, Alexander Stepanov bắt đầu nghiên cứu sử dụng cú pháp Template để tạo thư viện chương trình, sau này phát triển thành STL và được đưa vào tiêu chuẩn vào năm 1993.

Vào thời điểm đó, nhiều người cho rằng STL đã là đỉnh cao của Template C++. Tuy nhiên, trên tạp chí "C++ Report" năm 1995, John Barton và Lee Nackman đã đưa ra một ví dụ về Template cho phép nhân ma trận. Có thể nói, lập trình meta đã bắt đầu được nhiều người quan tâm vào thời điểm đó. Kể từ khi bài báo này được xuất bản, nhiều chuyên gia đã bắt đầu quan tâm đến Template. Alexandrescu, với cuốn sách "Modern C++ Design" và thư viện Template Loki, là người có đóng góp lớn nhất cho các kỹ thuật lập trình meta. Cuốn sách được xuất bản năm 2001 này đã gián tiếp dẫn đến sự xuất hiện của các thư viện lập trình meta template. Các thành phần tổng quát như Typelist và các phương pháp thiết kế như Policy được sử dụng trong sách đã mang đến một luồng gió mới. Tuy nhiên, do toàn bộ cuốn sách sử dụng phương pháp gần như “Geek” để xây dựng mọi thứ, nên việc đọc nó có phần khó khăn.

Cuốn sách "C++ Templates" được xuất bản năm 2002 có thể nói là một tác phẩm tổng hợp về Template. Nó giải thích chi tiết cú pháp của Template, cung cấp thông tin chi tiết về ngôn ngữ liên quan đến Template và đưa ra nhiều ví dụ tiêu biểu. Tuy nhiên, đối với người mới bắt đầu học Template, cuốn sách này quá chi tiết, khiến họ dễ dàng nản lòng và bỏ cuộc.

Mục đích của bài viết này là giới thiệu một "ngôn ngữ Template" đơn giản, rõ ràng thông qua góc nhìn "ngôn ngữ lập trình". Tôi sẽ cố gắng kết nối các yếu tố của Template, sử dụng các ví dụ đơn giản để giúp người đọc học "ngôn ngữ" này, cho phép người đọc viết và đọc mã Template một cách dễ dàng, biến kỹ thuật "lập trình meta template" trở thành một kỹ năng hữu ích mà người đọc nắm vững và có thể áp dụng trong nhiều trường hợp khác nhau.

## 1.2. Đối tượng độc giả

Vì bài viết này không dành cho người mới bắt đầu học C++, các ví dụ cũng sẽ liên quan đến một số kiến thức khác, nên nếu người đọc đáp ứng các điều kiện sau, việc đọc sẽ dễ dàng hơn:

* Nắm vững cú pháp cơ bản của C++;
* Đã sử dụng STL;
* Nắm vững một số thuật toán thông dụng, cũng như các phương pháp lập trình như đệ quy.

Ngoài ra, mặc dù chương đầu tiên sẽ giới thiệu một số cú pháp cơ bản của Template C++, nhưng nó vẫn còn khá sơ lược. Do đó, tôi cũng hy vọng người đọc đã hiểu và nắm vững các cú pháp cơ bản nhất của Template C++; nếu bạn có thể viết các Function Template và Class Template cơ bản thì càng tốt.

Như đã đề cập ở phần trước, bài viết này không phải là bản sao đơn giản của "C++ Templates" và cũng ít trùng lặp với "Modern C++ Design". Về cấu trúc kiến thức, tôi khuyên bạn nên đọc bài viết này trước, sau đó đọc "C++ Templates" để hiểu thêm về cú pháp và chi tiết triển khai; "Modern C++ Design" ngoài lập trình meta còn có rất nhiều ví dụ về lập trình tổng quát, về cơ bản phần lập trình tổng quát ít giao thoa với nội dung tôi trình bày, bạn có thể đọc các chương tương ứng của "MCD" sau khi đọc xong chương 1-3 để hiểu các quy tắc cơ bản của Template; phần lập trình meta (như Typelist) nên được đọc sau khi đọc xong bài viết này, có lẽ sẽ dễ hiểu hơn.

## 1.3. Bản quyền

Bài viết này được viết và đồng bộ hóa với Github, vì vậy trong quá trình viết khó tránh khỏi việc bỏ sót trích dẫn. Phần lớn nội dung của bài viết này là do tôi viết, nhưng cũng có thể có một số phần được lấy từ nguồn khác. Tôi sẽ cố gắng hết sức để đánh dấu tất cả các nội dung được trích dẫn bằng dấu ngoặc kép, hoặc chỉ ra trong ngữ cảnh và ghi chú bên lề. Nếu có bất kỳ thiếu sót nào, vui lòng cho tôi biết.

Tôi giữ bản quyền tất cả các phần tôi đã viết trong bài viết này. Nếu bạn cần đăng lại hoặc trích dẫn, vui lòng ghi rõ nguồn và thông báo cho tôi.

## 1.4. Môi trường biên dịch được đề xuất

Có nhiều trình biên dịch C++ và việc hỗ trợ Template có thể có sự khác biệt nhỏ. Nếu không có yêu cầu đặc biệt, trong quá trình viết bài này, tôi đã sử dụng các trình biên dịch sau để kiểm tra mã và ví dụ được cung cấp trong bài viết:

* Clang 14.0.3; 15.0 (amd64)
* Visual Studio 2022 19.2+ (amd64)

Ngoài ra, đối với một số ví dụ phức tạp, tôi đã cung cấp bản xem trước trình biên dịch trực tuyến trong bài viết để bạn đọc và kiểm tra dễ dàng. Trình biên dịch trực tuyến tham khảo: [`gcc.godbolt.org`](https://gcc.godbolt.org/).

Một số tính năng được sử dụng trong các ví dụ và tiêu chuẩn C++ tương ứng của chúng:

| Tính năng | Tiêu chuẩn |
|---|---|
| std::decay_t<T> | C++ 14 |

## 1.5. Quy ước trình bày

### 1.5.1. Mã ví dụ

```C++
void SampleCode() {
    // Đây là một đoạn mã ví dụ
}
```

### 1.5.2. Trích dẫn

Trích dẫn từ tiêu chuẩn C++:

> 1.1.2/1 Đây là một đoạn trích dẫn hoặc dịch từ tiêu chuẩn.

Trích dẫn từ các sách khác:

> 《Tên sách》
> Đây là một đoạn trích dẫn hoặc dịch từ các sách khác.

## 1.6. Ý kiến, đề xuất, phản hồi, bổ sung, kế hoạch viết

* Cần bổ sung:
  * Động lực sử dụng Template.
  * Thêm phần "Cách sử dụng bài viết này". Phần này sẽ giải thích quy ước trình bày của toàn bộ bài viết (phông chữ in đậm, lời nhắc, cách tổ chức ví dụ), tất cả các mô tả, ví dụ, trích dẫn sẽ được sắp xếp lại theo quy ước trình bày khi được xem xét lại.
  * Ngoại trừ các ví dụ được sử dụng để mô tả cú pháp, các ví dụ khác sẽ cố gắng mang ý nghĩa thực tế để làm rõ ý định.
  * Giải thích đầy đủ các quy tắc suy luận kiểu của Template trong chương phù hợp. Parameter-Argument, auto variable, decltype, decltype(auto)
  * Giải thích ADL trong phần quá tải hàm Template và khởi tạo.
  * Phần Template biến đổi nên được giải thích theo tiêu chuẩn (Argument Packing/Unpacking).
* Đề xuất:
  * So sánh sự khác biệt giữa Template và hàm.
  * Phân tích về C++14 Return type deduction for normal functions (màu xanh lam).

# 2. Cú pháp cơ bản của Template

## 2.1. Template là gì

## 2.2. Cú pháp cơ bản của Class Template

### 2.2.1. “Lớp Template” hay “Class Template”

### 2.2.2. Khai báo và định nghĩa Class Template và biến thành viên

Hãy cùng xem lại khai báo và định nghĩa cơ bản nhất của Class Template:

Khai báo Class Template:
```C++
template <typename T> class ClassA;
```

Định nghĩa Class Template:
```C++
template <typename T> class ClassA
{
    T member;
};
```

`template` là từ khóa C++, có nghĩa là chúng ta sẽ định nghĩa một Template. Giống như hàm, Template cũng có một loạt các tham số. Các tham số này được bao gồm trong `< >` sau `template`. Trong ví dụ trên, `typename T` là tham số Template. Hãy nhớ lại khai báo tham số hàm tương tự:

``` C++
void foo(int a);
```

`T` có thể được coi là tương tự như tham số hàm `a`, "tham số Template" `T` ở đây cũng giống như tham số hàm, bạn có thể đặt bất kỳ tên nào bạn muốn; `typename` tương tự như kiểu tham số hàm `int` trong ví dụ, nó biểu thị rằng `T` trong tham số Template sẽ khớp với một kiểu. Ngoài `typename`, chúng ta sẽ thảo luận sau, kiểu số nguyên cũng có thể là tham số của Template.

Sau khi định nghĩa tham số Template, bạn có thể định nghĩa lớp bạn cần. Tuy nhiên, khi định nghĩa lớp, ngoài các kiểu có thể sử dụng trong lớp thông thường, bạn cũng có thể sử dụng kiểu `T` được sử dụng trong tham số Template. Có thể nói, `T` này là tinh túy của Template, vì bạn có thể thay thế `T` bằng kiểu bạn cần bằng cách chỉ định tham số Template thực tế.

Ví dụ: nếu chúng ta sử dụng `ClassA<int>` để khởi tạo Class Template `ClassA`, thì `ClassA<int>` có thể tương đương với định nghĩa sau:

``` C++
// Lưu ý: Đây không phải là cú pháp C++ hợp lệ, chỉ để minh họa chức năng của Template.
typedef class {
    int member;
} ClassA<int>;
```

Có thể thấy, bằng cách thay thế kiểu bằng tham số Template, chúng ta có thể nhận được nhiều kiểu mới có cùng hình thức, giúp giảm thiểu lượng mã. Cách sử dụng này được gọi là "lập trình tổng quát" (Generic Programming), ứng dụng phổ biến nhất của nó là các Class Template chứa trong STL.

### 2.2.3. Sử dụng Template

Đối với C++, một trong những vai trò quan trọng nhất của kiểu là sử dụng nó để tạo ra một biến. Ví dụ: chúng ta định nghĩa một Class Template `vector` là mảng động (danh sách), nó có các thao tác `push_back` và `clear` cho bất kỳ kiểu phần tử nào, chúng ta có thể định nghĩa lớp này như sau:

```C++
template <typename T>
class vector
{
public:
    void push_back(T const&);
    void clear();				
	
private:
    T* elements;
};
```

Giả sử chương trình của chúng ta cần một danh sách kiểu số nguyên và một danh sách kiểu số thực, thì chúng ta có thể nhận được hai biến thông qua mã sau:

```C++
vector<int> intArray;
vector<float> floatArray;
```

Lúc này, chúng ta có thể thực hiện các thao tác sau để có được kết quả mong muốn:

```C++
intArray.push_back(5);
floatArray.push_back(3.0f);
```

Quá trình định nghĩa biến có thể được chia thành hai bước: Bước đầu tiên, `vector<int>` liên kết `int` với Class Template `vector` để có được một "lớp thông thường `vector<int>`"; bước thứ hai định nghĩa một biến thông qua "vector<int>".

Không giống như "lớp thông thường", Class Template không thể được sử dụng trực tiếp để định nghĩa biến - xét cho cùng, tên của nó là "Template" chứ không phải "lớp". Ví dụ:

```C++
vector unknownVector; // Ví dụ sai
```

Đây là sai. Chúng ta gọi quá trình biến đổi Class Template thành "lớp thông thường" thông qua liên kết kiểu là khởi tạo Template (Template Instantiate). Cú pháp khởi tạo là:

```
Tên Template < [Tham số Template thực tế 1, Tham số Template thực tế 2, ...] >
```

Hãy xem một số ví dụ:
```C++
vector<int>
ClassA<double>

template <typename T0, typename T1> class ClassB
{
    // Thân lớp ...
};

ClassB<int, float>
```

Tất nhiên, trong quá trình khởi tạo, kiểu được liên kết với tham số Template (tức là tham số Template thực tế) cần phải khớp chính xác với tham số Template hình thức.
Giống như hàm, nếu không cung cấp đủ và khớp các tham số, Template sẽ không được khởi tạo chính xác.

### 2.2.4. Định nghĩa hàm thành viên của Class Template

Do C++11 đã chính thức loại bỏ tính năng "xuất Template", nên khi biến của Class Template gọi hàm thành viên, nó cần phải thấy định nghĩa hàm thành viên đầy đủ. Do đó, các hàm thành viên trong Class Template hiện nay thường được triển khai theo cách nội tuyến.
Ví dụ:

``` C++
template <typename T>
class vector
{
public:
    void clear()
    {
        // Thân hàm
    }
	
private:
    T* elements;
};
```

Tất nhiên, chúng ta cũng có thể đặt phần định nghĩa của `vector<T>::clear` bên ngoài kiểu, chỉ là cú pháp lúc này sẽ hơi khó hiểu:

```C++
template <typename T>
class vector
{
public:
    void clear();  // Lưu ý, chỉ có khai báo ở đây.
private:
    T* elements;
};

template <typename T>
void vector<T>::clear()  // Triển khai hàm được đặt ở đây.
{
    // Thân hàm
}
```

Phần triển khai hàm trông hơi khó hiểu. Lần đầu tiên tôi học về nó, tôi đã nghĩ:

``` C++
void vector::clear()
{
    // Thân hàm
}
```

Không phải là được rồi sao? Nhưng suy nghĩ đơn giản sẽ biết rằng, `clear` không thể tìm thấy ký hiệu kiểu tổng quát `T`.

Do đó, khi triển khai hàm thành viên, cần phải cung cấp tham số Template. Ngoài ra, tại sao tên kiểu không phải là `vector` mà là `vector<T>`?
Nếu bạn đã hiểu cú pháp chuyên môn hóa một phần và chuyên môn hóa của Template, bạn nên nhận ra rằng `vector<T>` ở đây tương tự như chuyên môn hóa/chuyên môn hóa một phần về mặt cú pháp. Trên thực tế, định nghĩa hàm ở đây thực sự là chuyên môn hóa một phần của hàm thành viên. Khái niệm chuyên môn hóa và chuyên môn hóa một phần sẽ được giới thiệu chi tiết trong phần thứ hai của bài viết này.

Tóm lại, triển khai hàm thành viên chính xác như sau:

``` C++
template <typename T> // Tham số Template
void vector<T> /* Trông giống như chuyên môn hóa một phần */ ::clear() // Triển khai hàm được đặt ở đây.
{
    // Thân hàm
}
```

## 2.3. Giới thiệu về Function Template

### 2.3.1. Khai báo và định nghĩa Function Template

Cú pháp của Function Template về cơ bản giống với Class Template, cũng bắt đầu bằng từ khóa `template` và danh sách tham số Template. Kiểu trong danh sách tham số Template có thể xuất hiện trong tham số, giá trị trả về và thân hàm. Ví dụ, một số ví dụ sau:

```C++
template <typename T> void foo(T const& v);

template <typename T> T foo();

template <typename T, typename U> U foo(T const&);

template <typename T> void foo()
{
    T var;
    // ...
}
```

Cho dù là Function Template hay Class Template, chúng đều trông "biến đổi vô tận" trong mã thực tế. Những "biến đổi" này chủ yếu là do kiểu được coi là tham số, dẫn đến việc mã có thể thay đổi nhiều hơn.

Tóm lại, Template chỉ có hai điểm:

1. Trong hàm hoặc lớp, có một số kiểu chúng ta muốn thay đổi, chúng ta sử dụng một định danh để thay thế nó, đó là "tham số Template";

2. Ở những nơi cần các kiểu này, hãy viết định danh tương ứng ("tham số Template").

Tất nhiên, "biến đổi" ở đây thực chất là cố định sau khi mã được biên dịch, có thể gọi là tính biến đổi thời gian biên dịch.

Tôi muốn nói thêm ở đây, chủ yếu là để cho bạn biết rằng Template thực sự là một thứ rất đơn giản.

Ví dụ sau đây có thể giúp bạn giải quyết hai vấn đề sau:

1. Loại nhu cầu nào có thể được giải quyết bằng Template?

2. Làm thế nào để biến "tổng quát" trong tâm trí thành mã thực sự "tổng quát"?

```
Ví dụ: hàm có kiểu tổng quát 'add'.
```

Trong số những người bạn tôi gặp, ngay cả khi tôi giải thích Template cho họ theo cách này, ngay cả khi họ đã hiểu Template, họ vẫn sợ hãi nó. Xét cho cùng, về mặt hình thức, cả lớp Template và hàm Template đều phức tạp hơn so với phiên bản không phải Template, và nội dung cần hiểu khi đọc mã cũng tăng lên.

Làm thế nào để vượt qua vấn đề này và cuối cùng coi Template như mã phẳng?

Chỉ có một câu trả lời: **Luyện tập thành thạo**.

Khi học Template, bạn cần suy nghĩ và luyện tập lặp đi lặp lại như sau:

1. Đặt câu hỏi: Nhu cầu của tôi có thể được giải quyết bằng Template không?

2. Giải quyết như thế nào?

3. Viết giải pháp bằng mã.

4. Nếu thất bại, hãy tìm ra nguyên nhân. Có phải do thiếu kiến thức (ví dụ: không biết cách chuyển đổi `T&` thành `T`), hay là không khả thi (ví dụ: cố gắng chuyên môn hóa Class Template bằng hằng số thực, nhưng thực tế điều này là không khả thi)?

Bằng cách lặp lại các bài tập trên, bạn sẽ có thể nắm vững cả cú pháp và ý nghĩa của Template. Nếu bạn gặp khó khăn trong việc đặt câu hỏi, thì ví dụ kinh điển sau đây có thể là điểm khởi đầu cho bạn:

1. Viết một cấu trúc dữ liệu tổng quát: ví dụ: danh sách tuyến tính, mảng, danh sách liên kết, cây nhị phân;

2. Viết một hàm tổng quát có thể hoạt động trên các cấu trúc dữ liệu khác nhau, các kiểu phần tử khác nhau, ví dụ: tính tổng;

Tất nhiên, giống như "mẫu thiết kế", Template trong ứng dụng thực tế cũng sẽ có một số nhu cầu và giải pháp cố định. Các trường hợp phổ biến bao gồm: tổng quát (cách sử dụng cơ bản nhất), lấy thông tin tương ứng thông qua kiểu (trích xuất kiểu), tính toán trong thời gian biên dịch, suy luận và chuyển đổi giữa các kiểu (chuyển đổi từ kiểu này sang kiểu khác, ví dụ: boost::function). Những điều này sẽ được giới thiệu dần dần trong các chương sau của bài viết này.

### 2.3.2. Sử dụng Function Template

Hãy xem một Function Template đơn giản, cộng hai số:

``` C++
template <typename T> T Add(T a, T b)
{
    return a + b;
}
```

Định dạng gọi Function Template là:

``` C++
Tên Function Template < Danh sách tham số Template > ( Tham số )
```

Ví dụ: nếu chúng ta muốn cộng hai số nguyên `int`, thì theo phương pháp khởi tạo Class Template, chúng ta có thể viết như sau:

``` C++
int a = 5;
int b = 3;
int result = Add<int>(a, b);
```

Lúc này, chúng ta tương đương với việc sở hữu một hàm mới:

``` C++
int Add<int>(int a, int b) { return a + b; }
```

Lúc này, ở một góc xa xôi khác của chương trình, bạn cũng cần tính tổng. Nhưng lúc này, kiểu tham số của bạn là `float`, vì vậy bạn viết:

``` C++
Add<float>(a, b);
```

Mọi thứ có vẻ hoàn hảo. Nhưng nếu bạn là một lập trình viên lười biếng, bạn chắc chắn sẽ nghĩ, khi tôi gọi `Add<int>(a, b)`, cả `a` và `b` đều khớp với `T` đó. Trình biên dịch nên biết rằng `T` đó thực sự là `int`? Tại sao tôi phải viết thêm `Add<int>`?
Ừm, tôi muốn nói rằng, tác giả của trình biên dịch cũng nghĩ như vậy. Vì vậy, trên thực tế, khi bạn viết đoạn mã sau trong trình biên dịch:

``` C++
int a = 5;
int b = 3;
int result = Add(a, b);
```

Trình biên dịch sẽ hiểu ý bạn và biến `Add` thành `Add<int>`. Tuy nhiên, trình biên dịch không thể đối mặt với câu trả lời mơ hồ. Ví dụ: nếu bạn viết như thế này thì sao?

``` C++
int  a = 5;
char b = 3;
int  result = Add(a, b);
```

Tham số đầu tiên `a` cho trình biên dịch biết `T` này là `int`. Trình biên dịch gật đầu nói, được rồi. Nhưng tham số thứ hai `b` không hài lòng, nó nói với trình biên dịch, `T` của bạn thực ra là `char`.
Hai tham số riêng biệt chỉ ra kiểu của `T`, trình biên dịch không biết phải làm gì. Trong Visual Studio 2012, sẽ có lời nhắc sau:

```
error C2782: 'T _1_2_2::Add(T,T)' : template parameter 'T' is ambiguous
```

Ok, "ambiguous", lời nhắc này quá rõ ràng.

Tuy nhiên, miễn là bạn không ép buộc trình biên dịch bị tâm thần phân liệt, trình biên dịch thực sự rất thông minh, nó có thể đoán được ý định thực sự của bạn từ nhiều manh mối, như ví dụ sau:

``` C++
template <typename T> class A {};

template <typename T> T foo( A<T> v );

A<int> v;
foo(v);	// Nó có thể đoán chính xác rằng T là int.
```

Ồ, trình biên dịch đã bỏ qua lớp `A` và đoán được `T` khớp với `int`. Làm thế nào trình biên dịch thực hiện "phép thuật" này, chúng ta sẽ giải thích sau, trong phần 2.2.

Bây giờ là thời gian luyện tập của bạn. Bạn thử viết nhiều ví dụ, nhưng bạn vẫn còn băn khoăn về một trong số chúng:

``` C++
float data[1024];

template <typename T> T GetValue(int i)
{
    return static_cast<T>(data[i]);
}

float a = GetValue(0);	// Lỗi!
int b = GetValue(1);	// Cũng lỗi!
```

Tại sao lại lỗi? Bạn suy nghĩ kỹ, hóa ra trình biên dịch không thể suy luận kiểu dựa trên giá trị trả về. Khi hàm được gọi, ai nhận giá trị trả về vẫn chưa biết. Sau khi sửa đổi như sau, mọi thứ sẽ hoạt động bình thường:

``` C++
float a = GetValue<float>(0);
int b = GetValue<int>(1);
```

Ừm, thật dễ dàng phải không? Ừm, bạn lại tự tin làm một bài tập nữa:

Bạn muốn viết một Function Template có tên là `c_style_cast`, như tên gọi của nó, nó thực hiện chuyển đổi kiểu C. Sau đó, vì sự tiện lợi, bạn hy vọng nó có thể được viết giống như các chuyển đổi tích hợp như `static_cast`. Vì vậy, bạn đã viết một trường hợp sử dụng.

``` C++
DstT dest = c_style_cast<DstT>(src);
```

Dựa trên định dạng gọi, bạn biết rằng có hai tham số Template, `DstT` và `SrcT`. Chỉ có một tham số, `src`, vì vậy tham số hình thức của hàm tất nhiên được viết như thế này: `(SrcT src)`. Việc triển khai cũng rất đơn giản, `(DstT)v`.

Chúng ta hãy kết hợp thông tin chúng ta có để viết Function Template của riêng mình:

``` C++
template <typename SrcT, typename DstT> DstT c_style_cast(SrcT v)
{
    return (DstT)(v);
}

int v = 0;
float i = c_style_cast<float>(v);
```

Ừm, thật dễ dàng! Chúng ta hãy nhấn F6... Ồ! Điều này có nghĩa là gì!

``` C++
error C2783: 'DstT _1_2_2::c_style_cast(SrcT)' : could not deduce template argument for 'DstT'
```

Sau đó, bạn cẩn thận so sánh và phát hiện ra... có hai tham số Template, trong khi chỉ có một `SrcT` có thể thu được từ các tham số. Kết hợp với thông báo lỗi, có vẻ như vấn đề nằm ở `DstT`. Lúc này, bạn thử sửa lỗi bằng cách viết đầy đủ các tham số Template:

``` C++
float i = c_style_cast<int, float>(v);
```

Ừm, nó đã biên dịch thành công. Có phải C++ không hỗ trợ việc suy luận một phần tham số Template từ các tham số?

Tất nhiên là có thể. Chỉ là trong trường hợp suy luận một phần, chỉ định một phần, trình biên dịch có giới hạn về thứ tự của các tham số Template: **Viết trước các tham số Template cần chỉ định, sau đó đặt các tham số Template có thể suy luận được ở phía sau**.

Trong ví dụ này, `SrcT` có thể được suy luận, `DstT` cần được chỉ định. Viết Function Template như sau là được:

``` C++
template <typename DstT, typename SrcT> DstT c_style_cast(SrcT v)	// Tham số Template DstT cần được chỉ định thủ công, đặt ở phía trước.
{
    return