# Báo cáo: So sánh kiến trúc CISC và RISC
---

## 1. Giới thiệu chung

Trong lĩnh vực kiến trúc máy tính, hai hướng tiếp cận nổi bật là **CISC (Complex Instruction Set Computer)** và **RISC (Reduced Instruction Set Computer)**. Đây là hai triết lý thiết kế bộ xử lý (CPU architecture) khác nhau, ảnh hưởng sâu sắc đến hiệu năng, độ phức tạp phần cứng và khả năng tối ưu hóa trong các hệ thống máy tính và hệ thống nhúng.

CISC ra đời trong bối cảnh bộ nhớ còn đắt đỏ, tốc độ truyền dữ liệu thấp, nên hướng đến việc **giảm số lượng dòng lệnh trong chương trình** bằng cách cung cấp **các lệnh phức tạp hơn**. Ngược lại, RISC xuất hiện sau đó với triết lý “**đơn giản hóa phần cứng, tăng tốc độ xử lý**”, tận dụng khả năng pipeline và tối ưu hóa trình biên dịch (compiler).

Trong thời đại hiện nay, hiểu rõ sự khác biệt giữa hai kiến trúc này là rất cần thiết cho kỹ sư nhúng — những người thường phải cân bằng giữa **hiệu năng, tiêu thụ điện năng và chi phí phần cứng**.

---

## 2. Kiến trúc CISC (Complex Instruction Set Computer)

### 2.1. Khái niệm
CISC là kiến trúc có **tập lệnh phức tạp**, trong đó mỗi lệnh có thể thực hiện nhiều thao tác cấp cao như truy xuất bộ nhớ, tính toán, và lưu kết quả chỉ trong **một lệnh duy nhất**. Một ví dụ điển hình của kiến trúc CISC là **Intel x86**.

### 2.2. Ưu điểm
- Giảm **số lượng lệnh trong chương trình**, giúp tiết kiệm bộ nhớ mã lệnh.  
- Hỗ trợ **nhiều chế độ địa chỉ** (addressing modes), linh hoạt cho lập trình viên hợp ngữ.  
- Tương thích ngược tốt (backward compatibility) — đặc biệt trong dòng vi xử lý Intel.

### 2.3. Nhược điểm
- **Phần cứng phức tạp** do phải giải mã (decode) nhiều loại lệnh khác nhau.  
- **Khó thực hiện pipeline**, do thời gian thực hiện mỗi lệnh không đồng nhất.  
- Tiêu thụ năng lượng cao và tốc độ xung nhịp (clock speed) thường bị giới hạn.

---

## 3. Kiến trúc RISC (Reduced Instruction Set Computer)

### 3.1. Khái niệm
RISC hướng tới việc **giảm số lượng và độ phức tạp của tập lệnh**. Mỗi lệnh được thiết kế để **thực thi trong một chu kỳ xung nhịp (one clock cycle)**, giúp đơn giản hóa phần cứng và tối ưu hóa cho pipeline. Một đại diện tiêu biểu là **ARM (Advanced RISC Machine)**.

### 3.2. Ưu điểm
- **Tốc độ xử lý cao** nhờ pipeline hiệu quả.  
- **Phần cứng đơn giản**, dễ thiết kế và tiêu thụ điện năng thấp.  
- Dễ mở rộng và phù hợp với các hệ thống nhúng có yêu cầu tiết kiệm năng lượng.

### 3.3. Nhược điểm
- Chương trình cần **nhiều lệnh hơn** để hoàn thành cùng một tác vụ so với CISC.  
- Một số thao tác phức tạp phải chia nhỏ thành nhiều lệnh đơn giản.  
- Phụ thuộc nhiều vào **hiệu quả của trình biên dịch**.

---

## 4. So sánh kiến trúc CISC và RISC

| **Tiêu chí** | **CISC** | **RISC** |
|---------------|-----------|-----------|
| **Cấu trúc tập lệnh** | Tập lệnh phức tạp, nhiều chế độ địa chỉ. | Tập lệnh đơn giản, độ dài cố định. |
| **Tốc độ xử lý** | Thực thi mỗi lệnh mất nhiều chu kỳ xung. | Mỗi lệnh hoàn thành trong 1 chu kỳ, hỗ trợ pipeline. |
| **Kích thước chương trình** | Nhỏ hơn, do mỗi lệnh làm được nhiều việc. | Lớn hơn, cần nhiều lệnh hơn cho cùng tác vụ. |
| **Độ phức tạp phần cứng** | Cao, mạch điều khiển phức tạp. | Đơn giản, dễ tối ưu hiệu năng và năng lượng. |
| **Ứng dụng điển hình** | Intel x86, AMD, Pentium. | ARM, MIPS, RISC-V. |

Từ bảng trên có thể thấy, **RISC ưu tiên tốc độ và hiệu quả năng lượng**, trong khi **CISC ưu tiên khả năng tương thích và linh hoạt**.

---

## 5. Ứng dụng thực tế

- **Kiến trúc CISC**: Được sử dụng phổ biến trong **máy tính cá nhân (PC)**, **máy chủ (server)** và các hệ thống yêu cầu hiệu năng tính toán cao. Ví dụ: vi xử lý **Intel Core i7, AMD Ryzen**.
- **Kiến trúc RISC**: Thống trị lĩnh vực **thiết bị di động, IoT và hệ thống nhúng**. Ví dụ: **ARM Cortex-M, Cortex-A**, **Apple M1/M2**, và các bộ xử lý **RISC-V** mã nguồn mở.

Đặc biệt, **ARM** hiện chiếm hơn 90% thị phần bộ xử lý trong thiết bị di động nhờ khả năng tiêu thụ điện năng thấp, hiệu suất cao và chi phí sản xuất hợp lý.

---

## 6. Kết luận và quan điểm cá nhân

Sự khác biệt giữa CISC và RISC phản ánh hai triết lý thiết kế:  
- **CISC**: Tối ưu cho lập trình viên và tương thích phần mềm.  
- **RISC**: Tối ưu cho phần cứng và hiệu năng xử lý.

Trong bối cảnh phát triển **hệ thống nhúng hiện nay**, **RISC tỏ ra phù hợp hơn** nhờ các ưu điểm:
1. **Tiêu thụ năng lượng thấp**, giúp kéo dài thời gian hoạt động cho các thiết bị chạy pin.  
2. **Hiệu suất xử lý ổn định** nhờ pipeline sâu và tập lệnh cố định.  
3. **Dễ mở rộng** sang kiến trúc tùy biến như **RISC-V**, phù hợp với xu hướng mã nguồn mở trong ngành nhúng.  

Tuy nhiên, CISC vẫn giữ vai trò quan trọng trong các hệ thống máy tính hiệu năng cao. Xu hướng hiện nay là **lai giữa hai kiến trúc** — ví dụ, vi xử lý Intel x86 nội bộ sử dụng các vi-lệnh (micro-ops) mang tính RISC.

Tóm lại, với đặc thù của **kỹ sư nhúng**, kiến trúc **RISC (đặc biệt là ARM và RISC-V)** là lựa chọn tối ưu cho việc thiết kế các hệ thống nhúng hiện đại, cân bằng giữa **hiệu năng, chi phí và năng lượng**.

