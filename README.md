# ETC.-Management-System
## Giới thiệu
*Tên Đồ Án:* **XÂY DỰNG CƠ SỞ DỮ LIỆU QUẢN LÝ HỆ THỐNG THU PHÍ TỰ ĐỘNG ETC**  
*Ngôn ngữ:* **PL/SQL**  
*Phần mềm sử dụng:* **Oracle SQL Developer**
## Phân tích thiết kế cơ sở dữ liệu
### *Mô hình dữ liệu mức quan niệm:*
#### Mối quan hệ
##### Mối quan hệ giữa PHUONGTIENTHUPHI - XE  
![image](https://user-images.githubusercontent.com/126310227/221748973-36eac612-8d02-4971-81ac-8cd0100eeeb3.png)  
##### Mối quan hệ giữa KHACHHANG - HOADON  
![image](https://user-images.githubusercontent.com/126310227/221749036-90c183f5-963e-4194-92ac-910208acecf8.png)  
##### Mối quan hệ giữa NHANVIEN - THEETAG  
![image](https://user-images.githubusercontent.com/126310227/221749067-735e4451-6211-471f-9fc0-277d5024fe33.png)  
##### Mối quan hệ giữa NHANVIEN – TRAMTHUPHIBOT – TINHTHANH  
![image](https://user-images.githubusercontent.com/126310227/221749118-75914fd9-8034-4a55-8145-25e67f7b3c7f.png)
#### Mô hình thực thể kết hợp
![image](https://user-images.githubusercontent.com/126310227/221749206-c7d5f782-687c-40d2-9d69-aee1166bf4a5.png)
### Mô hình dữ liệu quan hệ
-	KHACHHANG(**_MAKH_**, HOKH, TENKH, NGAYSINHKH, GIOITINHKH, DIACHIKH, EMAILKH, SDTKH, CCCDKH)  
-	NHANVIEN((**_MANV_**, HONV, TENNV, GIOITINHNV, DIACHINV, EMAILNV, SDTNV, NGAYSINHNV, NGAYVAOLAM, LUONG, CCCDNV, _MACV, MATRAM_)  
-	TINHTHANH((**_MATINH_**, TENTINH)  
-	TRAMTHUPHIBOT(**_MATRAM_**, TENTRAM, DIACHI, _MATINH_, TUYENDUONG)  
-	CHUCVU(**_MACV_**, TENCV)  
-	PHUONGTIENTHUPHI(**_MALOAIXE_**, GHICHU)  
-	XE(**_MAXE_**, BIENSOXE, _MAKH, MALOAIXE_)  
-	TAIKHOAN(**_MATK_**, MATKHAU, QUYEN, _MANV_)  
-	LOAIVE(**_MALOAIVE_**, TENLOAIVE)  
-	THEETAG(**_MAVACHTHE_**, _MAKH, MALOAIVE, MAXE_, SODUTK)  
-	VIPHAM(**_MAVIPHAM_**, TENVIPHAM, MUCPHAT)  
-	LICHSUVIPHAM(**_MALSVP_**, _MAKH, MAVIPHAM_, NGAYVIPHAM)  
-	HOADON(**_MAHD_**, _MAVACHTHE, MAVIPHAM, MANV_, NGAYLAP)  
-	CHITIETHOADON(**_MAHD_**, _MATRAM, MAXE_, NOIDUNG)  

### *Sơ đồ Diagram:*  
![image](https://user-images.githubusercontent.com/126310227/221750790-5e2dc443-98a6-4e67-bf00-b1a063eb880c.png)

## Ứng dụng
### *Phần ứng dụng của đồ án sẽ bao gồm như sau:*  
| Tên ứng dụng| Số câu thực hiện |
|------|-------|
| Update và Delete | 10 |
| PL/SQL| 30 |
| View | 6 | 
| Function | 6 | 
| Store Procedure | 6 | 
| Trigger | 4 | 

### *Dưới đây sẽ là một số kết quả trong phần này*
#### Mẫu 1:
Viết cấu lệnh PL/SQL hiển thị số dư tài khoản của khách hàng với mã khách hàng là tham số truyền vào để biết được khách hàng đó còn đủ số dư để qua trạm không?
Nếu không thì gửi thông báo nhắc nhở số dư tài khoản không đủ.  
**Kết quả**  
![image](https://user-images.githubusercontent.com/126310227/221751239-0ebdb431-455b-4637-b51b-87f503ce6f55.png)  

#### Mẫu 2:  
Viết khối lệnh PL/SQL cho phép tổng số hóa đơn đã được bởi nhân viên cụ thể nào đó. Với mã nhân viên là tham số truyền vào 
Thông tin bao gồm: Mã nhân viên, tên trạm , số hóa đơn đã lập.  
**Kết quả**  
![image](https://user-images.githubusercontent.com/126310227/221751383-97cc566e-4b62-4a8c-9f88-0811518a4dd5.png)  

#### Mẫu 3:  
Viết khối lệnh PL/SQL lập danh sách báo cáo những khách hàng đã từng vi phạm, sắp xếp theo mã khách hàng TĂNG DẦN.   
**Kết quả**  
![image](https://user-images.githubusercontent.com/126310227/221751651-07ba5087-6b52-4c09-8e75-6c5b3c64675f.png)  

#### Mẫu 4:  
Viết thủ tục có tên proc_recharge cho phép nạp tiền vào thẻ Etag có các tham số mã vạch của thẻ Etag, số tiền cần nạp vào.  
Xử lý ngoại lệ: Kiểm tra mã vạch thẻ có tồn tại trong bảng THEETAG hay không?   
Nếu không có in ra thông báo lỗi. Viết khối lệnh PL/SQL thực thi thủ tục.  
 
**-	Kết quả trường hợp bị lỗi**  
![image](https://user-images.githubusercontent.com/126310227/221751849-db0ef8c7-149e-48ce-ba9d-2807965462c2.png)  
**-	Kết quả trường hợp đúng**  
*Lệnh chạy thành công*  
_Số tiền trước khi nạp:_  
![image](https://user-images.githubusercontent.com/126310227/221751951-b175e810-74e1-45df-a06b-9bbbe78906ce.png)  
_Số tiền sau khi nạp 100.000đ:_ 
![image](https://user-images.githubusercontent.com/126310227/221751980-1a9de7f8-75b4-4c13-b79b-d989295e880d.png)

#### Mẫu 5:
Tạo ràng buộc toàn vẹn kiểm tra mỗi khi thêm (Insert) hoặc cập nhật (Update) một dòng dữ liệu trong bảng Hóa Đơn.  
Đưa ra thông báo lỗi nếu nhập ngày lập hóa đơn > ngày hiện hành.  
**Kết quả trường hợp Insert thành công**  
![image](https://user-images.githubusercontent.com/126310227/221752686-cd117a20-4398-4675-aebd-2f52a3048f61.png)   
**Kết quả trường hợp Insert bị vi phạm**  
![image](https://user-images.githubusercontent.com/126310227/221752710-65245d3b-ab62-4a56-909c-f3b62b71f265.png)  
**Kết quả trường hợp Update thành công**  
![image](https://user-images.githubusercontent.com/126310227/221752757-cde37b5b-0c0a-4bb4-b542-1d6dbe288207.png)  
**Kết quả trường hợp Update vi phạm**  
![image](https://user-images.githubusercontent.com/126310227/221752780-626baaf0-437e-453f-8e5d-12558f43105f.png)  


## Kết luận
### Ưu điểm
-	Tạo mô hình thực thể cho thấy các dữ liệu có liên kết với nhau bởi các khóa chính làm cho thông tin được tìm nhanh chóng và đầy đủ.  
-	Tìm hiểu và theo dõi, phân tích thông qua hoạt động của mô hình trạm thu phí không dừng ETC từ đó sẽ xây dựng thành một phần mềm, và dễ dàng điều chỉnh chính sách phù hợp.  
-	Tìm hiểu được cơ sở lý thuyết về hệ thống quản lý hệ thống thu phí ETC.  
-	Cài đặt hệ quản trị cơ sở dữ liệu Oracle để quản lý về thu phí không dừng tại các trạm BOT trong cả nước.  
-	Xây dựng được CSDL quản lý hoạt động của trạm thu phí.  
-	Tạo được chức năng cập nhật thêm xóa sửa các nghiệp vụ cần thiết, các câu truy vấn dữ liệu thường dùng, khung nhìn view tiện lợi cho việc xem dữ liệu loại bỏ được một số thông tin không cần thiết. và những câu lệnh thủ tục và hàm quan trọng, cuối cùng là những câu trigger ràng buộc toàn tạo sự liên kết, kết dính cho các bảng thêm phần chính xác rõ ràng.   
### Nhược điểm
-	Kỹ năng thực hiện các mô hình thiết kế thông qua việc sử dụng các công cụ thiết kế trên máy tính chưa tốt, các mô hình có độ chuẩn xác chưa cao.  
-	Quản lí quá trình thực hiện đồ án còn thiếu hợp lý, cân đối cả về mặt nội dung lẫn thời gian.  
-	Một số chức năng của hệ thống chưa hoàn thiện.  
-	Hệ quản trị cơ sở chưa triệt để.  
-	Bảo mật dữ liệu chưa được tốt.  

  
