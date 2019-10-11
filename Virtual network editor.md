## **Tìm hiểu về Virtual Network Editor trong VMware Workstation**

VMware Workstation là phần mềm ảo hóa phiên bản dùng cho người dùng PC, để có thể sử dụng phần mềm này  hiệu quả, một yếu tố rất quan trọng là chúng ta cần phải hiểu về các kết nối mạng, cách thiết lập và cài đặt hệ thống mạng ảo trong phần mềm. ﻿
 ## 1.Giới thiệu VMware Workstation
 
 - VMware Workstation là phần mềm ảo hóa phiên bản dùng cho người dùng PC, để có thể sử dụng phần mềm này  hiệu quả, một yếu tố rất quan     trọng là chúng ta cần phải hiểu về các kết nối mạng, cách thiết lập và cài đặt hệ thống mạng ảo trong phần mềm. 
 - Các thành phần hình thành nên mạng ảo trong VMware gồm switch ảo, card mạng ảo, DHCP server ảo và thiết bị NAT
 
 ## 2.Switch ảo
 
 - Switch ảo có vài trò kết nối các thành phần mạng ảo với nhau.
 - Chúng có tên là VMnet0,VMnet2,VMnet3,....
 - Một số switch ảo được gắn vào mạng một cách mặc định. Mặc định khi ta cài Wmware thì có sẵn 3 Switch ảo như sau: VMnet0 chế độ Bridged (cầu nối), VMnet8 chế độ NAT và VMnet1 chế độ Host-only.
 - VMware Workstation (phiên bản 12) cho phép tạo 20 switch ảo trên Windows và 255 cái trên Linux.
 - Trên mỗi Switch ảo trên Windows thì các kết nối của các máy tính ảo (host) vào mỗi Switch ảo là không giới hạn, còn trên Linux thì 32      máy ảo.
 
 ## 3.Card mang trên máy ảo.
 
 -Khi bạn tạo một máy ảo mới, card mạng được tạo ra cho máy ảo, những card mạng này hiển thị trên hệ điều hành máy ảo với tên thiết bị như là AMD PCNET PCI hay Intel Pro/1000 MT Server Adapter. 
 
 ![](../image/i2.png)
 
 ## 4.DHCP server ảo
 
 -DHCP (Dynamic Host Configuration) server ảo đảm nhiệm việc cung cấp địa chỉ IP cho các máy ảo trong việc kết nối máy ảo vào các Switch   ảo không có tính năng Bridged (VMnet0). 
 - DHCP  server ảo cấp phát địa chỉ IP cho các máy ảo có kết nối với VMnet Host-only và NAT.
 
 ![](https://public.bn.files.1drv.com/y4peG36U7NACYoQN4xNa8kzMrs8IddLfNfvz2UdSTJHHBVKTU6BKRxxPVSnC7Cnt7UDzHkpZl9UvMhrWB8MaIHD6TBOg8RN2pLx4VHjEWiBB5Ded_l0xtyg8fS79vVg2zNvM0ANMy-VYTPy3ZiWx1c_52xtzenIt-8Jo2eg2vG0wIkfsj028wsldL02rRoEvXBT/dhcp.png?psid=1&rdrts=245380895)
 
 
 
 ![](https://www.engisv.info/wp-content/uploads/2013/08/dhcp.png)
 
 
 


## Tài liệu tham khảo

[1](https://virtualizationreview.com/articles/2011/06/30/virtual-network-editor-vmware-workstation.aspx)

[2](https://www.engisv.info/?p=134)







