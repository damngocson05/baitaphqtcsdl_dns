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

- **Xác thực:** Mixed Mode 
> Windows Authentication
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/444c24ff-adc6-498f-9698-5a64242b49e8" />

> SQL Server Authentication 
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/c7f18bc2-4d26-4fe2-aaa5-cdf5fe88e923" />

---

## 🗄️ 2. Quản trị Cơ sở dữ liệu
- **Database:** `QL_sinhvien` được lưu trữ tại ổ đĩa E (Khác ổ C).
- **Bảng dữ liệu:** Đã thiết kế bảng `SinhVien` với khóa chính `masv`
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/003bccb5-93e5-45da-b7bc-08e12e3c0991" />

- **Import:** Nạp thành công dữ liệu từ file `svtnut.csv`
<img width="869" height="785" alt="06a8d409-cbd6-4b4a-bc89-7437e7fe57a8" src="https://github.com/user-attachments/assets/e3e59504-fe0a-4fdb-8d55-b7a517322f4f" />

- Lệnh kiểm tra số dòng sau khi import
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/22ada1fd-1ab5-4886-9205-1a5fd89ecf5c" />


---

## 📊 3. Thao tác dữ liệu nâng cao 
Thực hiện các yêu cầu nghiệp vụ bằng SQL Script:
1. **Kiểm tra số dòng:** Đạt `12004` dòng (xấp xỉ 12020)
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/22ada1fd-1ab5-4886-9205-1a5fd89ecf5c" />

3. **Insert:** Thêm thông tin cá nhân sinh viên thực hiện bài
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ea168e52-8c34-43e8-8c31-9b4041acdfdf" />

5. **Update:** Cập nhật `noisinh = 'Sao Hoả'` cho các dòng dữ liệu trống.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/180114b7-d7b2-4b02-91b3-14fe49660b1a" />

7. **Select Into:** Tạo bảng `SaoHoa` từ danh sách sinh viên quê 'Sao Hoả'.
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/216433d4-a9f9-45a5-9328-a5f2ef9ad5ac" />

9. **Delete:** Xóa sinh viên cùng họ trong bảng `SaoHoa`.

> Danh sách sinh viên cùng họ Đàm
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e9027216-85e2-4b74-a7fe-2de989d49f09" />

> Tiến hành xóa sanh sách sinh viên cùng họ
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2fc9ca30-d493-413d-a2a6-626cc7dc9689" />

---

## 📂 4. Sao lưu và Phục hồi 
- **Backup:** Sử dụng tính năng **Generate Scripts (Schema + Data)** để xuất toàn bộ CSDL ra file `dulieu.sql`.

> Xuất thành công file dulieu.sql
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3c0303e1-5822-4c40-a172-351e5a455093" />

- **Restore:** Đã thực hiện xóa Database, kiểm tra xóa file vật lý và chạy lại file `dulieu.sql` để khôi phục trạng thái ban đầu.
> Tiến hành xóa database
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/6a850cfa-842d-4717-8219-c6d5f613c799" />

- **Restore:** Đã thực hiện xóa Database, kiểm tra xóa file vật lý và chạy lại file `dulieu.sql` để khôi phục trạng thái ban đầu thành công.

> Tiến hành khôi phục database
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/34a9d461-4f0f-45e9-a3a9-59d2a4d8ac81" />

- **Tuy nhiên:** Do lượng dữ liệu lớn nên trong lúc khôi phục có gặp chút vấn đề nên em đã chuyển qua khôi phục bằng CMD
- sqlcmd -S localhost,36061 -E -i "E:\baitap\Hệ quản trị cơ sở dữ liệu\QL_sinhvien\dulieu.sql"

> Kết quả dữ liệu trong db.SinhVien và db.SaoHoa đã được khôi phục
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5cd31ee6-29d8-4e60-a713-173316269193" />

## Upload file dulieu.sql lên github
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/a180e93f-73df-4968-b767-596e2f32c4ab" />

---
## Kết luận
Hy vọng bài tập này đáp ứng được các yêu cầu của môn học. Mọi đóng góp hoặc thắc mắc vui lòng liên hệ qua email: **K235480106061@Tnut.edu.vn**.

Người thực hiện
**Đàm Ngọc Sơn**

---
**Tệp đính kèm:** [Tải file dulieu.sql tại đây](./dulieu.sql)
