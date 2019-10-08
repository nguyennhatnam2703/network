## **Mô hình OSI**

![image](https://www.totolink.vn/public/uploads/img_article/mohinhosilagichucnangcuacactanggiaothuctrongmohinhosi.png)
## **I:Chức năng các tầng:**

### *1.Application*
![image](https://www.totolink.vn/public/uploads/img_article/mohinhosilagichucnangcuacactanggiaothuctrongmohinhosipresentationlayer.png)
### 1.1:Chức năng

Tầng Application có chức năng cung cấp giao diện để người dùng và 
 chương trình ứng dụng tương tác với nhau.Các giao thức cung cấp
các phương diện cho người dùng để truy cập vào mạng. 

### 1.2:Một số dịch vụ và giao thức trong tầng Application

+ DNS

+ SMTP

+ HTTP

+ FTP

+ Telnet

+ SSH
 
### *2.Presentation*

![image](https://www.totolink.vn/public/uploads/img_article/mohinhosilagichucnangcuacactanggiaothuctrongmohinhosipresentationlayer.png)

###2.1:Chức năng 

+Dịch các mã ký tự từ ASCII sang EBCDIC.

+chuyển đổi dữ liệu.

+mã hóa và giải mã dữ liệu để đảm bảo bảo mật.

+nén dữ liệu để giảm lượng dữ liệu truyền trên mạng

### *3.Session*

![image](https://www.totolink.vn/public/uploads/img_article/mohinhosilagichucnangcuacactanggiaothuctrongmohinhosisessionlayer.png)

### Chức năng

Tầng Session cho phép các người sử dụng trên các máy tính khác nhau có thể thiết lập,duy trì,đồng bộ phiên truyền thông  trong quá trình truyền thông giữa họ với nhau.

### *4.Transport*

![image](https://www.totolink.vn/public/uploads/img_article/mohinhosilagichucnangcuacactanggiaothuctrongmohinhositransportlayer.png)

#### 4.1:Chức năng chính

+theo dõi ứng dụng nguồn và đích

+phân đoạn dữ liệu,quản lí mỗi đoạn,hợp thành nguồn và đích.

+xác định đúng từng loại ứng dụng trong mỗi phiên truyền thông
	
#### 4.2:Các giao thức phổ biến

#### 4.2.1: Giao thức TCP

+TCP là truyền thông hướng kết nối,tạo phiên kết nối đến khi truyền

+truyền thông tin cậy đảm bảo dữ liệu bị mất sẽ được truyền lại

+sắp xếp dữ liệu khi truyền

+theo dõi từng phiên truyền thông

Một số ứng dụng:HTTP,SMTP,POP3,.....


#### 4.2.2:Giao thức UDP
+UDP là truyền thông phi kết nối,không thiết lập kết nối khi truyền.

+truyền thông không tin cậy

+không sắp xếp lại cấu trúc khi truyền

+không điều khiển luồng,không theo dõi phiên truyền thông

Một số ứng dụng:game online,livestream,...


### *5.Network*

![image](https://www.totolink.vn/public/uploads/img_article/mohinhosilagichucnangcuacactanggiaothuctrongmohinhosinetworklayer.png)

#### 5.1:Chức năng

+chuyển đổi dữ liệu

+định tuyến đường đi của gói tin

#### 5.2:Giao thức chính:

+internet protocol version 4(IPv4)

+internet protocol version 6(Ipv6)

###*6.Tầng Datalink*

![image](https://www.totolink.vn/public/uploads/img_article/mohinhosilagichucnangcuacactanggiaothuctrongmohinhosidatalinklayer.png)

#### 6.1:Chức năng:
+liên kết dữ liêu với tầng trên

+điều khiển Frame được đặt vào đường truyền và lấy ra đường truyền.

### 6.2:Giao thức.
+Logical link control(LLC):chịu trách nhiệm kiểm soát lỗi và kiểm soát luồng.

+Media access control(MAC):chịu trách nhiệm quản lí quyền truy cập và quyền truyền dữ liệu.

### *7.Tầng Physical*

![image](https://www.totolink.vn/public/uploads/img_article/mohinhosilagichucnangcuacactanggiaothuctrongmohinhosiphysicallayer.png)

#### Chức năng
+thiết lập và ngắt mạch một liên kết truyền thông

+biến đổi thể dạng của dữ liệu số trong thiết bị người dùng đồng bộ với tín hiệu được truyền qua đường truyền thông

## Tài liệu tham khảo

[totolink](https://www.totolink.vn/article/136-mo-hinh-osi-la-gi-chuc-nang-cua-cac-tang-giao-thuc-trong-mo-hinh-osi.html)

[blog](https://www.bmc.com/blogs/osi-model-7-layers/)







