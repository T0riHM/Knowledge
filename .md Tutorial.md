## Hướng dẫn sử dụng Markdown 
### Mục lục
[1. Thẻ tiêu đề](#thetieude)

[2. Kiểu chữ](#kieuchu)

[3. Kiểu danh sách](#kieudanhsach)

[4. Trích dẫn, bo chữ](#trichdan,bochu)

[5. Escape markdown](#escapemarkdown)

[6. Tạo bảng](#taobang)

[7. Chèn link](#chenlink)

[8. Chèn ảnh, emoji](#chenanh,emoji)
*********************************
## Mở đầu
Markdown là ngôn ngữ đánh dấu văn bản được tạo bởi John Gruber,
cú pháp khá đơn giản và dễ hiểu, dễ nhớ.
Bạn cần tạo một file .md. Có thể sử dụng notepate, notepad++, vi,...
. Bài viết dưới đây sẽ hướng dẫn để bạn có thể hiểu và sử dụng được ngay những cú pháp đó.

## Nội dung
<a name="thetieude"></a>
### 1. Thẻ tiêu đề
Markdown sử dụng các ký tự `#` để đánh dấu các tiêu đề. Mức độ các tiêu đề sẽ giảm dần từ 1 đến 6 tương ứng vứi từ 1 đến 6 ký tự `#` liên tiếp 

Ví dụ dòng lệnh 
```
# Thẻ cấp 1
## Thẻ cấp 2 
### thẻ cấp 3
```

Kết quả là:
# Thẻ cấp 1
## Thẻ cấp 2 
### Thẻ cấp 3
<a name="kieuchu"></a>
### 2. Kiểu chữ
Nội dung không nằm trong thẻ nào, Markdown mặc định sẽ nằm trong thẻ `p` của html
- Sử dụng ký tự `_` hoặc `*` để in nghiêng

Ví dụ: 
```
_Chữ in nghiêng_
*Chữ in nghiêng*
```

Kết quả là:

_Chữ in nghiêng_

*Chữ in nghiêng*
- Sử dụng ký tự `__` hoặc `**` để in đậm

Ví dụ:

`**In đậm**`

Kết quả là:

**In đậm**

- Sử dụng 3 ký tự `***` để vừa ***in dậm vừa in nghiêng***
```
***in đậm, in nghiêng***
```
***in đậm, in nghiêng***

- Ngoài ra chữ có thể gạch ngang bằng 2 dấu `~~`
```
~~gạch ngang~~
```
Kết quả là: 
~~gạch ngang~~

<a name="kieudanhsach"></a>
### 3. Kiểu danh sách
- Để đánh dấu 1 danh sách không có thứ tự ta sử dụng các ký tự `-`, `*`, `+` trước mỗi dòng.

Ví dụ: 
```
	- Danh sách 1
	- Danh sách 2
	- Danh sách 3
```
	
Kết quả là:

	- Danh sách 1
	
	- Danh sách 2
	
	- Danh sách 3
- Đánh dấu 1 danh sách có thứ tự ta sử dụng các số

Ví dụ: 
```
1. Danh sách 1
2. Danh sách 2
3. Danh sách 3
```
Kết quả là:
1. Danh sách 1
2. Danh sách 2
3. Danh sách 3
<a name="trichdan,bochu"></a>
### 4. Trích dẫn, bo chữ
Cách viết một trích dẫn bạn sử dụng ký tự `>`
Ví dụ: 
```
>Làm trai đứng ở trong trời đất
Phải có danh gì với núi sông.
```
>Làm trai đứng ở trong trời đất
 
>Phải có danh gì với núi sông.


Để bo 1 đoạn text sử dụng 
Ví dụ: 
```
`Bo đoạn text`
```
Kết quả là:
`Bo đoạn text`

<a name="escapemarkdown"></a>
### 5. Escape markdown 
Đôi khi viết bài bạn gặp phải các ký tự trùng với cú pháp của markdown.
Để phân biết bạn chỉ cần thêm dấu `\` trước các ký hiệu đó.
Ví dụ :
```
\*text*
```
Kết quả sẽ hiện ra là \*text* chứ không phải *in đậm*
<a name="taobang"></a>
### 6. Tạo bảng
Các cột trong bảng được ngăn cách với nhau bằng dấu dạch đứng `|` 
và header được tách với content bằng dấu gạch ngang `-`

```
|Thời khóa biểu|Thứ 2| Thứ 3| Thứ 4|
|--------------|:-----:|:------|------:|
|Kíp 1| ab| abc| abc|
|Kíp 2| x| x| z|
```

Kết quả là:

|Thời khóa biểu|Thứ 2| Thứ 3| Thứ 4|
|--------------|:-----:|:------|------:|
|Kíp 1| ab| abc| abc|
|Kíp 2| x| x| z|

<a name ="chenlink"></a>
### 7. Chèn link
Để chèn link chỉ cần add link đó vào file .md
```
https://github.com
```
https://github.com

Để rút ngắn link 
```
[Github](https://github.com)
```
[Github](https://github.com)

Ngoài ra bạn có thể thêm tiêu đề link bằng cách thêm "title" vào cuối phần `()`
```
[Github](https://github.com "Github")
```
[Github](https://github.com "Github")

<a name="chenanh,emoji">/</a>
### 8. Chèn ảnh, Emoji
Để chèn img sử dụng cú pháp sau:
```
![alt](link_anh)
```

Kết quả:
![Hoahong](https://shophoacantho.com/uploads/goc-thu-gian/2015_01/y-nghia-hoa-hong.jpg)

### Emoji 
```
:smile:
```

:smile:

### Video 

{@youtube: https://www.youtube.com/watch?v=sclBjiPuStU&list=RDsclBjiPuStU&start_radio=1}

