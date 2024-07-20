# Mở đầu

Hướng dẫn thực hành căn bản về bảo mật thông tin cá nhân/danh tính trên không gian mạng, chống lại việc dò tìm thông tin, [social engineering](https://cystack.net/blog/social-engineering), bị [OSINT](https://whitehat.vn/threads/lieu-ban-da-biet-tat-tan-tat-ve-osint.15832/),… hoặc có thể dùng để làm giáo án/hướng dẫn những nhân viên văn phòng về nâng cao nhận thức an toàn thông tin ở mức cơ bản.

Thông tin này được tìm hiểu, tổng hợp qua mạng ở nhiều nguồn, copy và chỉnh sửa cho hợp lý với điều kiện ở Việt Nam. Sẽ có update thêm trong tương lai về các việc không nên/nên và các ví dụ thực tế về các trường hợp nếu có hoặc có thể.

Bản đầu tiên được viết vào 20/7/2024.

# Mục lục

[I. Việc chia sẻ thông tin trên mạng](#viecchiasethongtintrenmang)

[1. Đối với cá nhân](#doivoicanhan)

[2. Đối với nhân viên công ty](#doivoinhanviencongty)

[II. Quy tắc chia sẻ và sử dụng thông tin trên mạng](#quytacchiasevasudungthongtintrenmang)

[III. Tham khảo](#thamkhao)

# Nội dung

<a name="viecchiasethongtintrenmang"></a>
## I. Việc chia sẻ thông tin trên mạng

<a name="doivoicanhan"></a>
### 1. Đối với cá nhân không/hạn chế chia sẻ

1.  Biệt danh, Họ, Tên Đệm và Tên thật được sử dụng trong cuộc sống hàng ngày/Họ, Tên Đệm và Tên pháp lý
2.  Ngày, tháng, năm sinh
3.  Thông tin về gia đình, bao gồm số thành viên trong gia đình, Biệt danh, Họ, Tên Đệm và Tên được sử dụng trong cuộc sống hàng ngày/Họ, Tên Đệm và Tên pháp lý
4.  Mối quan hệ trong gia đình và xã hội
5.  Địa chỉ nhà, nơi làm việc và địa chỉ trường học
6.  Số nhận dạng cá nhân bao gồm số bảo hiểm y tế, số căn cước công dân, số định dạng cá nhân, hộ chiếu, bằng lái xe, sổ hộ khẩu
7.  Ảnh chụp màn hình đầy đủ của điện thoại, máy tính cá nhân
8.  Cấu hình, mẫu mã, model của các thiết bị hay sử dụng như đồng hồ, điện thoại, máy tính cá nhân,…
9.  Ảnh chụp màn hình của bất cứ ứng dụng nào có thể chứa thông tin cá nhân
10. Địa chỉ IP(public IP) được nhà mạng cung cấp
11. Thông tin có thể sử dụng để trả lời các câu hỏi bảo mật phổ biến, như tên thành phố được sinh ra, tên thú cưng đầu tiên, tên của giáo viên đầu tiên,…

<a name="doivoinhanviencongty"></a>
### 2. Đối với nhân viên công ty tuyệt đối không chia sẻ

1.  Các thông tin xác thực tài khoản, mật khẩu liên quan đến công ty/công việc và làm, đặt theo các quy tắc được đề ra (tùy mỗi công ty)
2.  Ảnh chụp màn hình đầy đủ của điện thoại, máy tính công ty, hoặc các hình ảnh có liên quan tới/ở công ty (ví dụ: có thể lỡ chụp toàn màn hình máy tính, trong đó lỡ dính 1 đoạn chat của công ty có đường link web thử nghiệm và có public ra internet, mà web này chưa được triển khai các biện pháp an toàn)
3.  Cấu hình, mẫu mã, model của các thiết bị sử dụng như đồng hồ, điện thoại, máy tính,…
4.  Các vấn đề/thông tin của công ty vời người quen, người thân, chỗ công cộng
5.  Ý thức được hành động của bản thân đối với các chính sách của công ty

<a name="quytacchiasevasudungthongtintrenmang"></a>
## II. Quy tắc chia sẻ và sử dụng thông tin trên mạng

1.  Sử dụng ít nhất 3 địa chỉ email khác nhau dành cho các mục đích khác nhau. Ví dụ:
      -   Một địa chỉ email được sử dụng để xác minh các dịch vụ không thiết yếu như giải trí, học tập
      -   Một địa chỉ email được sử dụng để đăng kí các dịch vụ thiết yếu như ngân hàng, dịch vụ công
      -   Một địa chỉ email cho riêng công việc
      -   Nếu cần những email tạm thời để xác thực trong vài phút rồi bỏ. Gợi ý sử dụng [temp-mail](https://temp-mail.org/en/)
2.  Không **NÊN\*** sử dụng cùng một mật khẩu cho nhiều dịch vụ và nên đặt theo khuyến nghị như sau:
      -   Mật khẩu thường sẽ bao gồm chữ hoa, chữ thường, số, ký tự đặc biệt,…
      -   Thay đổi theo chu kỳ 3 tháng, 6 tháng, 1 năm,…
      -   Không được hao hao giống với tài khoản hoặc mật khẩu cũ
      -   Mỗi 1 tài khoản nên là 1 mật khẩu độc nhất
3.  Sử dụng chức năng xác thực hai lớp nếu có
4.  Sử dụng các ứng dụng VPN để ẩn địa chỉ IP
5.  Không **NÊN\*** sử dụng cùng một biệt danh/tên đăng nhập cho nhiều dịch vụ khác nhau
      -   Nếu có dùng chung một biệt danh/tên đăng nhập nên thay đổi ít nhất ở 1 vài chi tiết, như chữ o có thể thay bằng số 0, e thành 3,…
      -   Hoặc có thể sử dụng những con số, chữ đặc biệt đối với bản thân thêm vào cuối biệt danh/tên đăng nhập
6.  Hạn chế đăng nhập các tài khoản như Google, Facebook,.. vào các thiết bị chưa rõ nguồn gốc hoặc hạn chế ít nhất có thể, khi đăng nhập xong NHỚ log out ra

\*Chỉ là không **NÊN**, không có nghĩa là không được làm thế, và cũng có gợi ý nếu dùng

<a name="thamkhao"></a>
## III. Tham khảo

1. https://github.com/ndbiaw/opsec-guide

2. https://medium.com/@mr.alexanderghost/ultimate-opsec-b9174fe6e4bf
