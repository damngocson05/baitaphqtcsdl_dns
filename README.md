# BÁO CÁO BÀI TẬP SỐ 1: HỆ QUẢN TRỊ CSDL SQL SERVER 2025

**Thông tin sinh viên:**
- **Họ và tên:** Đàm Ngọc Sơn
- **Mã sinh viên:** K235480106061
- **Lớp:** K59.KMT.K01
- **Trường:** Đại học Kỹ thuật Công nghiệp Thái Nguyên (TNUT)

---

## 🛠️ 1. Cài đặt và Cấu hình
- **Phiên bản:** SQL Server 2025 Developer.
- **Cổng kết nối:** Đã cấu hình TCP/IP chạy trên cổng tĩnh `36061` (4 số cuối MSV).
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/257a327f-679e-4370-9fcc-c2175d26536e" />

- **Trạng thái cổng:** Kiểm tra bằng `netstat -ano | findstr 36061` cho kết quả `LISTENING`
- Kiểm tra Port trên CMD
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a06d5bca-6e4f-49af-a8c9-85603dd914c5" />

- **Xác thực:** Mixed Mode (Windows Auth & SQL Auth `sa/123`).
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ac9bae4a-9c2c-413c-9236-8433707448c3" />

---

## 🗄️ 2. Quản trị Cơ sở dữ liệu
- **Database:** `QL_sinhvien` được lưu trữ tại ổ đĩa E (Khác ổ C).
- **Bảng dữ liệu:** Đã thiết kế bảng `SinhVien` với khóa chính `masv`.
- **Import:** Nạp thành công dữ liệu từ file `svtnut.csv`.
<img width="869" height="785" alt="06a8d409-cbd6-4b4a-bc89-7437e7fe57a8" src="https://github.com/user-attachments/assets/e3e59504-fe0a-4fdb-8d55-b7a517322f4f" />

> ![Danh sách file .mdf và .ldf tại thư mục lưu trữ](<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/397253ec-e364-47c9-b343-d4deefe89abb" />
)

---

## 📊 3. Thao tác dữ liệu nâng cao 
Thực hiện các yêu cầu nghiệp vụ bằng SQL Script:
1. **Kiểm tra số dòng:** Đạt `12004` dòng (xấp xỉ 12020).
2. **Insert:** Thêm thông tin cá nhân sinh viên thực hiện bài.
3. **Update:** Cập nhật `noisinh = 'Sao Hoả'` cho các dòng dữ liệu trống.
4. **Select Into:** Tạo bảng `SaoHoa` từ danh sách sinh viên quê 'Sao Hoả'.
5. **Delete:** Xóa sinh viên cùng họ trong bảng `SaoHoa`.

---

## 📂 4. Sao lưu và Phục hồi 
- **Backup:** Sử dụng tính năng **Generate Scripts (Schema + Data)** để xuất toàn bộ CSDL ra file `dulieu.sql`.
- **Restore:** Đã thực hiện xóa Database, kiểm tra xóa file vật lý và chạy lại file `dulieu.sql` để khôi phục trạng thái ban đầu thành công.

---
**Tệp đính kèm:** [Tải file dulieu.sql tại đây](./dulieu.sql)
