# quan-ly-ho-so-hoc-sinh-bang-OCR
<img width="1616" height="558" alt="image" src="https://github.com/user-attachments/assets/33491f93-303b-4b2d-9849-d577509e568b" />
 Hệ thống Quản lý Hồ sơ Học sinh, Sinh viên bằng OCR 

1. Giới thiệu
Ứng dụng này là một **web service sử dụng Flask** kết hợp với **Gemini AI** để:
- Nhận diện thông tin học sinh/sinh viên từ ảnh (OCR).
- Trích xuất bảng điểm (môn học, điểm).
- Quản lý danh sách sinh viên (thêm, sửa, xóa).
- Xuất dữ liệu ra **Excel**.
- Cung cấp **API** để tích hợp với giao diện web (trong thư mục `templates/`).

2. Công nghệ sử dụng
- **Python 3.9+**
- **Flask** (REST API backend)
- **Flask-CORS** (cho phép frontend gọi API)
- **Pandas** (xuất Excel)
- **Pillow (PIL)** (xử lý ảnh)
- **Google Gemini AI API** (`google-generativeai`)

3. Tạo môi trường ảo
  python -m venv venv
source venv/bin/activate   # Linux/macOS
venv\Scripts\activate      # Windows
* Cài đặt thư viện
pip install -r requirements.txt
* Cấu hình API key Gemini
GEMINI_API_KEY = "YOUR_API_KEY"
* Chạy server: python app.py
* Giao diện
<img width="1336" height="650" alt="image" src="https://github.com/user-attachments/assets/ef487b93-26aa-4d8a-8a7b-5d5f7e113306" />
Các chức năng chính
 1. Quản lý sinh viên
- Thêm mới học sinh/sinh viên: thủ công hoặc thông qua upload ảnh bảng điểm.
- Cập nhật thông tin sinh viên (MSSV, Họ tên, Ngành).
- Xóa sinh viên.
- Xem danh sách sinh viên hiện tại.

2. OCR & Trích xuất thông tin
- **/ocr**: Upload ảnh bảng điểm → Hệ thống tự động trích xuất:
  - Họ Tên
  - MSSV
  - Ngành học
  - Điểm các môn
- **/grades**: Upload ảnh → Trích xuất riêng bảng điểm từng môn.

 3. Quản lý điểm
- Tự động gắn điểm từ OCR vào hồ sơ sinh viên.
- Cho phép thêm điểm thủ công khi tạo mới sinh viên.

### 4. Xuất báo cáo
- **/export**: Xuất toàn bộ danh sách sinh viên + điểm sang file **Excel** (`danh_sach_hoc_sinh.xlsx`).



