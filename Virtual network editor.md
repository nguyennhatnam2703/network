<<<<<<< HEAD
﻿
=======

# **Tìm hiểu về Virtual Network Editor trong VMware Workstation**

# Mục lục

- [1.Giới thiệu VMware Workstation ](#1)

- [2.Switch ảo](#2)

- [3.Card mang trên máy ảo.](#3)

- [4.DHCP server ảo](#4)

- [5.LAN Segment](#5)

- [6.Các cơ chế hoạt động khi cấu hình với switch ảo.](#6)

- [6.1:Bridge](#6.1)

- [6.2:NAT](#6.2)

- [6.3:Host only](#6.3)

 <a name="1"><a>
 ## 1.Giới thiệu VMware Workstation
 
 - VMware Workstation là phần mềm ảo hóa phiên bản dùng cho người dùng PC, để có thể sử dụng phần mềm này  hiệu quả, một yếu tố rất quan     trọng là chúng ta cần phải hiểu về các kết nối mạng, cách thiết lập và cài đặt hệ thống mạng ảo trong phần mềm. 
 - Các thành phần hình thành nên mạng ảo trong VMware gồm switch ảo, card mạng ảo, DHCP server ảo và thiết bị NAT
 
  <a name="2"><a>
 ## 2.Switch ảo
 
 - Switch ảo có vài trò kết nối các thành phần mạng ảo với nhau.
 - Chúng có tên là VMnet0,VMnet2,VMnet3,....
 - Một số switch ảo được gắn vào mạng một cách mặc định. Mặc định khi ta cài Wmware thì có sẵn 3 Switch ảo như sau: VMnet0 chế độ Bridged (cầu nối), VMnet8 chế độ NAT và VMnet1 chế độ Host-only.
 - VMware Workstation (phiên bản 12) cho phép tạo 20 switch ảo trên Windows và 255 cái trên Linux.
 - Trên mỗi Switch ảo trên Windows thì các kết nối của các máy tính ảo (host) vào mỗi Switch ảo là không giới hạn, còn trên Linux thì 32      máy ảo.
 
 ![](https://www.engisv.info/wp-content/uploads/2013/08/dhcp.png)

 <a name="3"><a>
 ## 3.Card mang trên máy ảo.
 
 -Khi bạn tạo một máy ảo mới, card mạng được tạo ra cho máy ảo, những card mạng này hiển thị trên hệ điều hành máy ảo với tên thiết bị như là AMD PCNET PCI hay Intel Pro/1000 MT Server Adapter. 
 
 ![](../image/i2.png)
 
  <a name="4"><a>
 ## 4.DHCP server ảo
 
 -DHCP (Dynamic Host Configuration) server ảo đảm nhiệm việc cung cấp địa chỉ IP cho các máy ảo trong việc kết nối máy ảo vào các Switch   ảo không có tính năng Bridged (VMnet0). 
 - DHCP  server ảo cấp phát địa chỉ IP cho các máy ảo có kết nối với VMnet Host-only và NAT.
 
 ![](https://public.bn.files.1drv.com/y4peG36U7NACYoQN4xNa8kzMrs8IddLfNfvz2UdSTJHHBVKTU6BKRxxPVSnC7Cnt7UDzHkpZl9UvMhrWB8MaIHD6TBOg8RN2pLx4VHjEWiBB5Ded_l0xtyg8fS79vVg2zNvM0ANMy-VYTPy3ZiWx1c_52xtzenIt-8Jo2eg2vG0wIkfsj028wsldL02rRoEvXBT/dhcp.png?psid=1&rdrts=245380895)

 <a name="5"><a>
 ## 5.LAN Segment
 - Các card mạng của máy ảo có thể gắn kết với nhau thành từng LAN Segment.
 -Không giống như VMnet, LAN Segment chỉ kết nối các máy ảo được gán trong một LAN Segment lại với nhau mà không có những tính năng như   DHCP và LAN Segment không thể kết nối ra máy thật như các Virtual Switch VMnet.
 
 ![](../image/lag/png)
 
  <a name="6"><a>
 ## 6.Các cơ chế hoạt động khi cấu hình với switch ảo.
 
  <a name="6.1"><a>
 ## 6.1:Bridge
 - ở chế độ này, card mạng trên máy ảo được gắn vào VMnet0, VMnet0 này liên kết trực tiếp với card mạng vật lý trên máy thật, máy ảo lúc này sẽ kết nối internet thông qua  card mạng vật lý và có chung lớp mạng với card mạng vật lý.
 
 ![](https://public.bn.files.1drv.com/y4pmQpFGGVCkpAgVP5xikkW15KWQpyONPf7l0O_itJWG4UbMKa18Nw9xRNfTnMn2XcSremXKZrfeXBtheLOFqEF31S94Dsq5EqGm_2kPGu5b76_-znzI3zx4xOTbmDK13ZNX9Lt32UUCGy7rAGnPN4ps5Hm-lbnrjXpdxnIS-Oxh2a2Ytu646yWmOApe3qHMUgI/briged.png?psid=1&rdrts=245380896)
 
  <a name="6.2"><a>
 ## 6.2:NAT
 
 - ở chế độ này, card mạng của máy ảo kết nối với VMnet8, VNnet8 cho phép máy ảo đi ra mạng vật lý bên ngoài internet thông qua cơ chế NAT
 - Lúc này lớp mạng bên trong máy ảo khác hoàn toàn với lớp mạng của card vật lý bên ngoài, hai mạng hoàn toàn tách biệt. IP của card mạng máy ảo sẽ được cấp bởi DHCP của VMnet8, trong trường hợp bạn muốn thiết lập IP tĩnh cho card mạng máy ảo bạn phải đảm bảo chung lớp mạng với VNnet8 thì máy ảo mới có thể đi internet.
 
  ![](https://public.bn.files.1drv.com/y4pYQJTxUDoHmUtDcRmE7WeQn95T_bhmWOwLBqM0BnTl8pqXumWY-xdWYptS0oyH7hi3V7AnuXUkKgAOicKdckGJjpc788DqRG5o8AlbyT2uPPXCF2asVSaknUQZLuj0xbEH1v31DI10r8ILkwWzKSvro5w_KKktEZVKg-bBNx9OJbF6sZjx3wS2n6IeU5AL31L/NAT.png?psid=1&rdrts=245380896)
  
  ## 6.3:Host only
  
  - máy ảo được kết nối với VMnet có tính năng Host-only, trong trường hợp này là VMnet1 . VNnet Host-only kết nối với  một card mạng ảo tương ứng ngoài máy thật. 
  
  - Ở chế độ này,  các máy ảo không có kết nối vào mạng vật lý bên ngoài hay internet thông qua máy thật , có nghĩa là mạng VMnet Host-only và mạng vật lý hoàn toàn tách biệt.
  - IP của máy ảo được cấp bởi DHCP của VMnet tương ứng. Trong nhiều trường hợp đặc biệt cần cấu hình riêng, ta có thể tắt DHCP trên VMnet và cấu hình IP bằng tay cho máy ảo.
  
  ![](https://public.bn.files.1drv.com/y4pARrdVqArJcswexFFTZnagid4g92WJjM5y3pMFc75l6xiz9A90y68P_WE7txbcy1p759lMgCiEGqEy-Cwvg9b3YBjuFqQQ2p9ZbUc_3_05g_VoiDnlZNPzaqsgkkkIqRPMblDsO5q7z6pniJ3La9DJTvZNqBlb7AtSNnatBRLnO4_5citGM9vLn9im5-30aHd/host-only.png?psid=1&rdrts=245380896)
 
 
 
 
 
 
 
 


## Tài liệu tham khảo

[1] https://virtualizationreview.com/articles/2011/06/30/virtual-network-editor-vmware-workstation.aspx

[2] https://www.engisv.info/?p=134







>>>>>>> 1836dd760a03db4c45d8f5b1b1bb665fc71c7873
