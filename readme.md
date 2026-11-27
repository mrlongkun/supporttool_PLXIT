# ⛽ SupportTool - Hỗ Trợ Kỹ Thuật 

Ứng dụng Windows Desktop chuyên dụng dành cho Cán bộ Tin học, Kỹ thuật viên hỗ trợ vận hành và xử lý sự cố hệ thống tại các Cửa hàng Xăng dầu (CHXD) Petrolimex.

---

## 📥 Tải Về Phiên Bản Mới Nhất

| Phiên bản | Tải trực tiếp (Direct Download) | Kênh phát hành (Release Notes) |
| :--- | :--- | :--- |
| **Bản mới nhất (Latest)** | [⬇ **Tải SupportTool.exe**](https://github.com/mrlongkun/supporttool_PLXIT/releases/latest/download/SupportTool.exe) | [🔗 GitHub Releases](https://github.com/mrlongkun/supporttool_PLXIT/releases/latest) |


> 💡 **Lưu ý:** Tool chạy độc lập dạng Portable (chỉ cần file `.exe` duy nhất, không cần cài đặt, tương thích tốt từ Windows 7, Windows 10 đến Windows 11 trên nền tảng .NET Framework 4.0).

---

## 🌟 Tổng Quan Các Chức Năng Chính

Phần mềm được thiết kế theo giao diện phân tab rõ ràng, tối ưu hiển thị chống tràn/co rút giao diện trên mọi độ phân giải màn hình (DPI scaling):

### 1. 🖥️ Tab Vận Hành (AGAS / EGAS / KTMS / POS)
* **Kiểm tra thông mạng & Ping:**
  * Ping kiểm tra kết nối tới máy AGAS Server (`192.168.1.100`) và KTMS / EGAS Client (`192.168.1.101`).
  * Ping kiểm tra cổng thanh toán máy POS.
* **Kiểm tra & Xử lý Cơ sở Dữ liệu SQL Server:**
  * Kiểm tra kết nối SQL AGAS và SQL EGAS.
  * Hỗ trợ tự động sửa lỗi SQL (`Fix SQL`) và đồng bộ dữ liệu.
* **Quản trị Dịch vụ KTMS (Dịch vụ tự động hóa cột bơm):**
  * Theo dõi trạng thái Service KTMS trực quan (Đang chạy / Dừng).
  * Điều khiển nhanh: **Start**, **Stop**, **Restart** hoặc **Kill Process KTMS** khi bị treo.
  * Mở nhanh trình quản lý Windows Services (`services.msc`).
* **Tra cứu Nghiệp vụ & Dữ liệu:**
  * **Tra cứu PLX ID:** Lấy thông tin mã khách hàng qua mã số thuế hoặc thẻ định danh.
  * **Tra cứu Paylog:** Xem lịch sử và chi tiết các giao dịch thanh toán không tiền mặt theo số Refno.
  * **Kiểm tra Rule Firewall:** Đóng/mở và kiểm tra cấu hình tường lửa Windows cho luồng Inbound / Outbound.

---

### 2. ⚙️ Tab Chức Năng Nâng Cao (Quản Trị Hệ Thống CHXD)
* **Phân hệ Máy Khách EGAS (192.168.1.101):**
  * Kiểm tra và cấu hình Tên máy (`Computer Name`) & Địa chỉ IP tĩnh.
  * Cấu hình định dạng vùng (`Region / Locale`) và định dạng ngày ngắn chuẩn (`Short Date: dd/MM/yyyy`).
  * Quản trị dịch vụ máy chủ Web cục bộ **UltiDev ASP.NET 4.0 Web App** (Start / Stop / Restart).
  * Giám sát dịch vụ CSDL **SQL Server (SQLEXPRESS)** và **SQL Server Browser**.
  * Kiểm tra và bật/tắt Tường lửa Windows (**Windows Firewall**).
* **Phân hệ Máy Chủ AGAS (192.168.1.100):**
  * Giám sát trạng thái hoạt động của toàn bộ hệ sinh thái phần mềm AGAS:
    - `AGAS` (Ứng dụng chính)
    - `Agas_DB_Clean` (Dọn dẹp và tối ưu CSDL)
    - `AGASUpdated` (Tiến trình cập nhật tự động)
    - `autosendmail` (Dịch vụ gửi báo cáo tự động)
    - `agasapicloud` (Dịch vụ đồng bộ hóa Cloud tập đoàn)

---

### 3. ℹ️ Tab Giới Thiệu & Cập Nhật Tự Động (Auto-Update)
* **Thông tin ứng dụng:** Hiển thị số hiệu phiên bản hiện hành, thông tin bản quyền và link đến trang web hỗ trợ kỹ thuật CHXD.
* **Cơ chế Cập nhật Tự động (One-Click Auto Update):**
  * **Kiểm tra theo yêu cầu (On-Demand):** Phần mềm **tuyệt đối không chạy ngầm hay tự ý gửi gói tin mạng** khi chưa được phép.
  * **Kiểm tra phiên bản mới:** Khi bấm **"🔍 Kiểm tra bản mới"**, tool sẽ truy vấn trực tiếp GitHub Releases để lấy số phiên bản mới nhất và nội dung ghi chú cập nhật (**Release Notes**).
  * **Tự động hoán đổi phiên bản (Hot-swap):** Khi có bản mới, bấm **"⬇ Cập nhật ngay"**, phần mềm sẽ tự tải file về, thay thế file cũ và khởi động lại phiên bản mới chỉ trong vòng 2 giây mà không cần người dùng phải tải hay copy thủ công.

---

## 🛠️ Yêu Cầu Hệ Thống & Cài Đặt

* **Hệ điều hành:** Windows 7 SP1, Windows 8.1, Windows 10, Windows 11 (32-bit hoặc 64-bit).
* **Môi trường yêu cầu:** Microsoft .NET Framework 4.0 trở lên (đã có sẵn trên hầu hết các máy tính tại CHXD).
* **Cách sử dụng:** Tải file `SupportTool.exe` về máy, copy vào thư mục làm việc (hoặc để ngoài Desktop) và click đúp chuột để chạy trực tiếp với quyền Administrator.

---

## 👨‍💻 Thông Tin Phát Triển & Bản Quyền

* **Tác giả nền tảng:** Mr Duy
* **Nâng cấp & Phát triển:** Nguyễn Quốc Long (`longnq`) - Phòng Tin học Petrolimex
* **Kho lưu trữ & Kênh cập nhật:** [https://github.com/mrlongkun/supporttool_PLXIT](https://github.com/mrlongkun/supporttool_PLXIT)
* **Website Hỗ trợ kỹ thuật CHXD:** [https://hotrochxdplxdn.netlify.app](https://hotrochxdplxdn.netlify.app)
