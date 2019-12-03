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

# Hoạt động của SNMP

- Các SNMP agent sẽ giữ một sơ sở dữ liệu, được gọi là Management Information Base (MIB), trong đó chứa các thông tin khác nhau về hoạt động của thiết bị mà 
  agent đang giám sát. Phần mềm quản trị SNMP Manager sẽ thu thập thông tin này qua giao thức SNMP.
  
# Ưu điểm của SNMP

- SNMP sẽ giúp đơn giản hóa các quá trình quản lý các thành phần trong mạng ,nhờ đó các phần mềm SNMP có thể được phát triển nhanh và tốn ít chi phí.
- SNMP được thiết kế để có thể mở rộng các chức năng quản lý, giám sát
- SNMP được thiết kế để có thể hoạt động độc lập với các kiến trúc và cơ chế của các thiết bị hỗ trợ SNMP.
  + Các thiết bị khác nhau có hoạt động khác nhau nhưng đáp ứng SNMP là giống nhau. 
  + Ví dụ bạn có thể dùng 1 phần mềm để theo dõi dung lượng ổ cứng còn trống của các máy chủ chạy HĐH Windows và Linux
  
# Tham khảo:
- [1]   http://planet.com.vn/hotro/kienthuc/dichvumang/snmp/mlnews.2010-06-25.9003750781/view
- [2] http://www.netone.com.vn/Trangch%E1%BB%A7/H%E1%BB%97tr%E1%BB%A3k%E1%BB%B9thu%E1%BA%ADt/Ki%E1%BA%BFnth%E1%BB%A9cc%C4%83nb%E1%BA%A3n/tabid/366/arid/1119/Default.aspx
- [3] https://vi.wikipedia.org/wiki/SNMP