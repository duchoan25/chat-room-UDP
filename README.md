<h2 align="center">
    <a href="https://dainam.edu.vn/vi/khoa-cong-nghe-thong-tin">
    🎓 Faculty of Information Technology (DaiNam University)
    </a>
</h2>
<h2 align="center">
    CHAT ROOM DÙNG UDP MULTICAST
</h2>
<div align="center">
    <p align="center">
        <img alt="AIoTLab Logo" width="170" src="https://github.com/user-attachments/assets/711a2cd8-7eb4-4dae-9d90-12c0a0a208a2" />
        <img alt="AIoTLab Logo" width="180" src="https://github.com/user-attachments/assets/dc2ef2b8-9a70-4cfa-9b4b-f6c2f25f1660" />
        <img alt="DaiNam University Logo" width="200" src="https://github.com/user-attachments/assets/77fe0fd1-2e55-4032-be3c-b1a705a1b574" />
    </p>

[![AIoTLab](https://img.shields.io/badge/AIoTLab-green?style=for-the-badge)](https://www.facebook.com/DNUAIoTLab)
[![Faculty of Information Technology](https://img.shields.io/badge/Faculty%20of%20Information%20Technology-blue?style=for-the-badge)](https://dainam.edu.vn/vi/khoa-cong-nghe-thong-tin)
[![DaiNam University](https://img.shields.io/badge/DaiNam%20University-orange?style=for-the-badge)](https://dainam.edu.vn)

</div>

---
## 📖 1. Giới thiệu hệ thống
Xây dựng một ứng dụng chat nhóm (chat room) trong đó nhiều người dùng có thể gửi và nhận tin nhắn cùng lúc.

Sử dụng UDP Multicast thay vì TCP, giúp truyền thông tin đến nhiều client trong cùng một nhóm mà không cần gửi riêng từng kết nối.
## 🔧 2. Công nghệ sử dụng
Java: Sử dụng Java làm ngôn ngữ chính nhờ tính đa nền tảng, hỗ trợ tốt các thư viện mạng và giao diện người dùng. Phiên bản JDK (ví dụ: OpenJDK 17) được sử dụng để đảm bảo tương thích với các môi trường phát triển hiện đại.

#### Ngôn ngữ lập trình:
Java (phổ biến trong demo học thuật và dễ xử lý socket).
(Ngoài Java, có thể dùng Python, C#, C++… nhưng Java được chọn nhiều do hỗ trợ tốt socket multicast).

#### Giao diện người dùng:
Xây dựng giao diện đồ họa (GUI) cho client sử dụng các thành phần của gói javax.swing.*:

        Java Swing: Được sử dụng để xây dựng giao diện đồ họa (GUI) với các thành phần như JFrame, JTextArea, JTextField, và JButton. Swing cung cấp khả năng tùy chỉnh cao và dễ tích hợp với các ứng dụng Java.

Swing cung cấp giao diện thân thiện, dễ tùy chỉnh mà không cần thư viện bên ngoài.

#### Công nghệ mạng:
        UDP Multicast: Sử dụng giao thức UDP Multicast để truyền tin nhắn đến nhiều người nhận trong cùng một nhóm (ví dụ: địa chỉ multicast 224.0.0.69, cổng 3000). Phương pháp này giảm tải băng thông so với gửi riêng lẻ đến từng client.
        
        Socket: Được client sử dụng để kết nối đến server thông qua địa chỉ IP và port.
        
        Threading: Sử dụng luồng (thread) trong Java để xử lý nhận tin nhắn đồng thời với giao diện, đảm bảo ứng dụng không bị treo khi chờ dữ liệu mạng.

#### Giao thức mạng:

UDP (User Datagram Protocol)

Truyền dữ liệu không kết nối, nhanh nhưng không đảm bảo tin cậy.

IP Multicast

Dải địa chỉ đặc biệt 224.0.0.0 – 239.255.255.255.

Cho phép gửi 1 gói tin đến nhiều client cùng tham gia group.
## 🚀 3. Hình ảnh các chức năng

<p align="center">
  <img src="https://github.com/user-attachments/assets/9637394e-f41a-415c-816b-39661598edd2" alt="Screenshot 2025-09-19 092536" width="800"/>
</p>

<p align="center">
  <em>Hình 1:  Chức năng đăng nhập </em>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/84afc742-80ba-4764-bdc1-83afde51d1c9" alt="Screenshot 2025-09-19 094427" width="800"/>
</p>
<p align="center">
  <em> Hình 2: Chức năng đăng kí </em>
</p>

<p align="center">
  <img src="https://github.com/user-attachments/assets/5d2a875f-d9d1-47c3-a1a4-13a8ee557dff" alt="Screenshot 2025-09-18 183912" width="800"/>
</p>
<p align="center">
  <em> Hình 3: Hình ảnh chat của các phòngphòng  - </em>
</p>

<p align="center">
  <img src="picture/Screenshot 2025-09-16 140708.png" alt="" width="800"/>
</p>
<p align="center">
  <em> Hình 5: Lịch sử chat  - </em>
</p>

## 📝 4. Các bước cài đặt
**Bước 1**: Chuẩn bị môi trường

Cài đặt Java Development Kit (JDK):

Tải JDK phiên bản 8 hoặc cao hơn (khuyến nghị OpenJDK 17) từ adoptium.net hoặc oracle.com.

Cài đặt JDK theo hướng dẫn của nhà cung cấp.

Sau cài đặt, kiểm tra bằng cách mở terminal và chạy:

        java -version
        
Nếu thấy phiên bản (ví dụ: "openjdk 17.0.1"), JDK đã sẵn sàng.

**Bước 2**: Tạo 2 file Server.java và Client.java

        Đảm bảo 2 file ở chung 1 package

**Bước 3**: Mở file ServerServer.java

        run java và sau đó Server sẽ khởi động và hiển thị giao diện, chờ kết nối từ client. 

        Mở một terminal mới (hoặc nhiều terminal để chạy nhiều client).


**Mọi Thắc Mắc Vui Lòng Liên Hệ Theo Thông Tin Bên Dưới Dưới**

**SDT**: 0971100154
**EMAIL**: nguyenduchoan2050@gmail.com
    
© 2025 AIoTLab, Faculty of Information Technology, DaiNam University. All rights reserved.

---
