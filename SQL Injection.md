# **Lý Thuyết**

**Theo lý thuyết, SQL Injection** là một kỹ thuật lợi dụng những lỗ hổng về câu truy vấn của các ứng dụng. Lỗ hổng tồn tại khi đầu vào của người dùng không được kiểm tra đúng cách, được thực hiện bằng cách chèn thêm một đoạn [SQL](https://topdev.vn/blog/sql-la-gi/) để làm sai lệnh đi câu truy vấn ban đầu, từ đó có thể khai thác dữ liệu từ database. **SQL injection** có thể cho phép attackers thực hiện các thao tác như một người quản trị web, trên cơ sở dữ liệu của ứng dụng.

Về mặt thực tiễn: Nói đơn giản là do thiết kế của giao diện nhập dữ liệu bất kỳ và sử dụng các đầu vào này để xây dựng các truy vấn SQL, không giới hạn việc người dùng nhập những gì. Từ đó attacker lợi dụng những lỗi đó để chèn vào đó các đoạn truy vấn SQL rồi gửi lên server để sữa đổi dữ liệu từ database, hoặc lấy thông tin từ database.

Sau đây là 1 bài lab đơn giản bao gồm về những vấn đề như:

SQL injection

SQL statements: SELECT and UPDATE statements

Measures to prevent and protect against attack

# LAB

## SQL injection

Trong phần này ta sẽ làm việc với giao diện người dùng đăng nhập, ta sẽ sử dụng nhưng câu lệnh cơ bản để có thể đăng nhập vào nhưng không cần biết mật khẩu hay tài khoản của người dùng.

### Input Box Non-String

Đầu tiên, ta sẽ có 1 giao diện người dùng đơn giản như sau, với vai trò là 1 attacker, ta sẽ thử nhập bất cứ thứ gì để tìm manh mối.

![](media/9e3ffd5d4d8b271d945980a0e759fcb1.png)

Khi nhập thử vài thứ đơn giản và log in, ta được thông tin trả về là sai thông tin đăng nhập, nhưng đây là môi trường luyện tập/học hỏi nên ta được trả về kèm query của SQL như sau: **SELECT uid, name, profileID, salary, passportNr, email, nickName, password FROM usertable WHERE profileID=haha AND password = 'a665a45920422f9d417e4867efdc4fb8a04a1f3fff1fa07e998e86f7f7a27ae3'**

Khi nhìn vào query, ta thấy được những thứ ta nhập vào sẽ được đặt vào để tìm kiếm, ProfileID sẽ được giữ nguyên, còn Password sẽ bị băm ở 1 dạng nào đó. Từ đây, ta có thể phân tích rằng ta sẽ khai thác được ở chỗ ProfileID do nó giữ nguyên những gì ta nhập vào, còn Password thì không do nó đã bị chuyển đổi khi đưa vào query tìm kiếm của SQL.

![Ảnh có chứa văn bản, ảnh chụp màn hình, phần mềm, Biểu tượng máy tính Mô tả được tạo tự động](media/4a1d9eb1f5a1e67937b98ff2a0738f57.png)

Ta bắt đầu sử dụng cú pháp truy vấn SQL đã biết/học để khai thác: **1 or 1=1 --**

Password nhập hay không nhập sẽ tùy vào giao diện bắt buộc hay không, do giao diện này bắt buộc ta nhập vào password và nó sẽ biển đổi ở khúc sau, mà cái ta cần khúc đầu query là đúng và nó sẽ trả về kết quả, nên ở đây ta dùng **“--”** để kết thúc câu truy vấn (có nghĩ là từ sau “--” ở câu truy vấn bên dưới sẽ không được dùng đến để truy vấn mặc dù có hiển thị). Nên khúc password này nhập bất cứ thứ gì cũng được. Và ta sẽ được trả về thông tin cần biết.

**SELECT uid, name, profileID, salary, passportNr, email, nickName, password FROM usertable WHERE profileID= 1 or 1=1 -- AND password = 'a665a45920422f9d417e4867efdc4fb8a04a1f3fff1fa07e998e86f7f7a27ae3'**

![](media/c24beb57671c17b63385b1dcda6a6590.png)

![](media/6ffb0479c07677659bf360d7216ebb9c.png)

### Input Box String

Cũng như ban đầu, ta có 1 giao diện người dùng đơn giản, cùng với những bước thử đơn giản để biết được cần làm những gì.

![](media/80946f320342eaf6fc69d204bbb607d7.png)

Khi thử xong ta được trả về với câu truy vấn như sau: **SELECT uid, name, profileID, salary, passportNr, email, nickName, password FROM usertable WHERE profileID = 'haha' AND password = 'a82bbcafa60653297ec19c20da291c70a861098afd5fb2b2325a947272379f57'**

Điều khác biệt so với cái ở trên là ở đây ta thấy chữ ta nhập vào được bỏ trong dấu ‘, có nghĩa là định dạng nhập vào sẽ là string, còn password vẫn là như cũ sẽ được băm ra

![](media/792175f17df27d1ddb12159e4555684f.png)

Ta cũng bắt đầu sử dụng cú pháp truy vấn SQL đã biết/học để khai thác: **1 or 1=1 --**, nhưng lần này khác hơn định dạng đầu vào sẽ giữ nguyên là chuỗi string đó, và ta sẽ cần thay đổi câu truy vấn 1 tý để dừng và bắt đầu chuỗi string ở những điểm ta muốn, nên cú pháp là: **1' or '1'='1' --**

Khúc sau, password vẫn như trên, nên ta nhập gì cũng được.

2 dấu **' màu xanh** là mặc định của SQL, ta điều chỉnh sau số 1 của ta là 1 dấu **'** để kết thúc dấu **'** mặc định của SQL, còn dấu **'** còn lại sau -- coi như không có tác dụng

**SELECT uid, name, profileID, salary, passportNr, email, nickName, password FROM usertable WHERE profileID = '1' or '1'='1' --' AND password = 'cfae26288bd82e1a97669b7720470cf394e87b0e53bdd7e584055805cc63001f'**

![](media/6104dede8eecc3e5fb2486bb556c8c97.png)

![](media/db0b2477d9f3b181e6f84947f7ab7f89.png)

### URL

Cũng như 2 phần trước, là 1 giao diện người dùng, ta thực hiện các bước như trước, và được trả về kết quả y như cái thứ 2 chúng ta đã là

![Ảnh có chứa văn bản, ảnh chụp màn hình, phần mềm, Phần mềm đa phương tiện Mô tả được tạo tự động](media/29e4880d41b783ec2ef805bc2a587b4d.png)

![Ảnh có chứa văn bản, ảnh chụp màn hình, phần mềm, Biểu tượng máy tính Mô tả được tạo tự động](media/a5178cf4cfdf6d35610a79ea89eaba8f.png)

Khi thực hiện với cú pháp truy vấn y chang như cái 2: **1' or '1'='1' --**, ta được trả về là trang đã cấm nhập các cú pháp đặc biệt, nhưng khi nhìn lên url, ta thấy được các thứ ta nhập đều được ghi trên đó

![Ảnh có chứa văn bản, ảnh chụp màn hình, phần mềm, Phần mềm đa phương tiện Mô tả được tạo tự động](media/f36c84798e1b0aaf0cf857b4079cfc72.png)

Ta thử sửa đổi url trên thành như sau và enter:

**http://10.10.74.78:5000/sesqli3/login?profileID=1' or '1'='1' --&password=123**

Ta đã đăng nhập thành công và lấy được thông tin

![Ảnh có chứa văn bản, ảnh chụp màn hình, phần mềm, Phần mềm đa phương tiện Mô tả được tạo tự động](media/f6329b952d004e1ead08b5dd03f6e3e4.png)

![Ảnh có chứa văn bản, phần mềm, Phần mềm đa phương tiện, Biểu tượng máy tính Mô tả được tạo tự động](media/b0375457bb0c32139c1165613995924a.png)

## SQL statements

Phần này sẽ chuyên sâu hơn về việc lấy, thay đổi dữ liệu người dùng và gần như chỉ áp dụng được khi đã thực hiện được bước SQL injection trên.

Lần này đề bài cho ta tài khoản và mật khẩu sẵn, mục tiêu là vào hệ thống với các thủ thuật cần thiết như(thay đổi, cập nhật cần) để tìm ra flag

-   **profileID: 10**
-   **password: toor**

## Measures to prevent and protect against attack

**Sử dụng Web Application Firewalls (WAF):** có các rule chống syntax đã quy định trước, Load Balance, chống top 10 owsap,…

**Kiểm tra và ràng buộc đầu vào (Input Validation and Sanitization)**: gần giống như WAF, nhưng WAF làm được nhiều chức năng hơn, hoặc nếu chỉ cần chống SQL với kiểm tra ràng buộc này thì không cần đầu tư thêm chi phí vào WAF.

**Sử dụng Prepared Statements:**

Sẽ gồm 2 bước là *Prepare* và *Compile and Execute*

![Ảnh có chứa Đồ họa, Phông chữ, thiết kế đồ họa, phim hoạt hình Mô tả được tạo tự động](media/6fac9179575dc3ac17427fe6aaa8a66a.png)

*Prepare*: đầu tiên, ứng dụng tạo ra 1 statement template và gửi nó cho DB. Các giá trị không được chỉ ra và được gọi là parameters (dấu ? bên dưới) **SELECT \* FROM accounts WHERE id = ?;**

*Compile and Execute:* (parse, optimizes và translates) statement template , store kết quả mà không thực thi. Quá trình này do DB thực hiện. Ứng dụng gửi giá trị của parametes của statement template và DB thực thi nó. Có thể thực thi statement nhiều lần với nhiều giá trị khác nhau.
