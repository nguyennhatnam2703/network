# Tìm hiểu về SNMP

# Khái niệm SNMP 

- SNMP( simple network management protocol) là giao thức là giao thức quản lý mạng đơn giản
- SNMP hoạt động ở lớp ứng dụng, chạy cổng 160, 161,162 trên UDP.
- SNMP là giao thức được sử dụng rất phổ biến để giám sát và điều khiển thiết bị mạng như switch, router, server ...
- Ngoài ra SNMP còn cho phép quản lý các thiết bị mạng từ xa.
- SNMP có khả năng theo dõi, lấy thông tin, đưa ra thông báo và tác động đến các hoạt động hệ thống mạng theo ý muốn của người quản trị
- một số khả năng của phần mềm SNMP:
  + theo dõi tốc độ đường truyền của router,biết được tổng số byte đã truyền/nhận.
  + lấy thông tin máy chủ đang có bao nhiêu ổng cứng, mỗi ổ cứng còn trống bao nhiêu
  + tự động nhận cảnh báo khi switch có một port bị down
  + điều khiển tắt các port trên switch
  
# Thành phần của SNMP
- Hai nhân tố chính trong SNMP: Manager và Agent.
  + Manager: Là một máy tính chạy chương trình quản lý mạng. Manager còn được gọi là một NMS (Network Management Station). Nhiệm vụ của một manager là truy vấn 
  các agent và xử lý thông tin nhận được từ agent.
  + Agent: Là một chương trình chạy trên thiết bị mạng cần được quản lý. Agent có thể là một chương trình riêng biệt (ví dụ như daemon trên Unix) hay được tích 
  hợp vào hệ điều hành, ví dụ như IOS (Internetwork Operation System) của Cisco. Nhiệm vụ của agent là thông tin cho manager.
  
# Các phiên bản của SNMP

- Hiện tại có 4 phiêm bản của SNMP: SNMPv1, SNMPv2c, SNMPv2u và SNMPv3. 
- Các phiên bản khác nhau một chút ở phần định dạng bản tin và phương thức hoạt động
- Hiện tại SNMPv1 là phổ biến nhất do có nhiều thiết bị tương thích nhất và có nhiều phần mềm hỗ trợ nhất.
- Các đặc điểm của các phiên bản:
- |Phiên bản SNMP| Mô tả |
  |--------------|-------|
  |1|Dùng SMIv1 dùng phương thức xác thực đơn giản với community nhưng chỉ dùng MIB-I|
  |2|Dùng SMIv2. Loại bỏ việc sử dụng communities thêm vào các thông điệp Getbulk và Inform nhưng đã bắt đầu với phiên bản MIB-II|
  |2c|Phiên bản giả cho phép SNMPv1 giao tiếp với SNMPv2. Tương đương với SNMPv2|
  |3|Phần lớn tương tự như SNMPv2 nhưng thêm vào các tính năng bảo mật. Hỗ trợ tương thích ngược. Dùng MIB-II|

# Hoạt động của SNMP
- ![]( /image/hdsnmp.jpg)
- Các SNMP agent sẽ giữ một sơ sở dữ liệu, được gọi là Management Information Base (MIB), trong đó chứa các thông tin khác nhau về hoạt động của thiết bị mà 
  agent đang giám sát. Phần mềm quản trị SNMP Manager sẽ thu thập thông tin này qua giao thức SNMP.
  
# Ưu điểm của SNMP

- SNMP sẽ giúp đơn giản hóa các quá trình quản lý các thành phần trong mạng ,nhờ đó các phần mềm SNMP có thể được phát triển nhanh và tốn ít chi phí.
- SNMP được thiết kế để có thể mở rộng các chức năng quản lý, giám sát
- SNMP được thiết kế để có thể hoạt động độc lập với các kiến trúc và cơ chế của các thiết bị hỗ trợ SNMP.
  + Các thiết bị khác nhau có hoạt động khác nhau nhưng đáp ứng SNMP là giống nhau. 
  + Ví dụ bạn có thể dùng 1 phần mềm để theo dõi dung lượng ổ cứng còn trống của các máy chủ chạy HĐH Windows và Linux

# Các thông điệp SNMP

- |Messgae|Phiên bản ban đầu|Thông điệp trả lời|Thông điệp được gửi bởi|Mục đích chính|
  |-------|-----------------|------------------|-----------------------|--------------|
  |Get|1|Response|Manager|Yêu cầu giá trị của một biến|
  |GetNext|1|Response|Manager|Yêu cầu cho giá trị MIB kế tiếp trong cây MIB|
  |GetBulk|2|Response|Manager|Yêu cầu gửi nhiều biến MIB với chỉ một request. Hữu ích cho việc thu thập các thông tin có cấu trúc phức     tạp như bảng định tuyến IP|
  |Response|1|None|Agent|Được dùng để trả lời cho thông tin trong các yêu cầu Get và Set|
  |Set|1|Respose|Manager|Được gửi bởi một phần mềm manager đến agent để thiết lập một giá trị cho một biến. Agent sẽ trả lời bằng thông   điệp response|
  |Trap|1|None|Agent|Cho phép các agents gửi các thông tin tự do đến một manager. Manager sẽ không trả lời với bất kỳ thông điệp SNMP     nào|
  |Inform|2|Response|Manager|Một thông điệp được dùng giữa SNMP manger để cho phép dữ liệu MIB được trao đổi|
  
 - Cả ba biến thể của thông điệp SNMP get message và thông điệp SNMP response thường được dùng khi ta chủ động dùng một SNMP manager:
   + Khi một người dùng của SNMP hỏi thông tin, phần mềm manager sẽ gửi một trong ba kiểu lệnh get đến agent.
   + Phía agent sẽ trả lời bằng thông điệp SNMP response.
 - Lệnh SNMP set cho phép các phần mềm quản lý thay đổi một vài thứ trên agent.  
 - SNMP trap là các thông điệp được gửi từ agent đến trạm quản trị. Ví dụ khi một cổng bị hỏng hóc, một agent của SNMP có thể gửi ra một   thông điệp trap đến SNMP manager.
 - các thông điệp inform cho phép hai SNMP giao tiếp với nhau để trao đổi các thông tin MIB về các agents và cả hai cùng đang quản lý.
  
   

# Tham khảo:
- [1]   http://planet.com.vn/hotro/kienthuc/dichvumang/snmp/mlnews.2010-06-25.9003750781/view
- [2] http://www.netone.com.vn/Trangch%E1%BB%A7/H%E1%BB%97tr%E1%BB%A3k%E1%BB%B9thu%E1%BA%ADt/Ki%E1%BA%BFnth%E1%BB%A9cc%C4%83nb%E1%BA%A3n/tabid/366/arid/1119/Default.aspx
- [3] https://vi.wikipedia.org/wiki/SNMP
- [4] https://tailieu.vn/doc/chuong-4-cac-phien-ban-snmp-650319.html
