\
# Math Translator Pipeline - Safe ChatGPT Login Edition

Bản này triển khai pipeline đúng hướng sản phẩm:

1. Người dùng upload PDF.
2. App tạo session tạm.
3. App tách PDF thành từng file PDF nhỏ: 1 trang / 1 file.
4. App render mỗi trang thành ảnh PNG preview.
5. App trích xuất các block text theo tọa độ.
6. App tạo prompt cố định cho từng trang.
7. Người dùng mở cửa sổ ChatGPT, đăng nhập thủ công.
8. Người dùng copy prompt từng trang vào ChatGPT.
9. Người dùng dán bản dịch JSON trở lại app.
10. App dựng lại từng trang PDF dịch.
11. App ghép toàn bộ PDF dịch thành file lớn.
12. App xóa file tạm.

## Vì sao không tự động điều khiển cửa sổ ChatGPT?

App không tự động bấm, gửi file, đọc phản hồi, lấy cookie hoặc điều khiển phiên đăng nhập ChatGPT.
Đây là ranh giới an toàn để không thu thập thông tin đăng nhập hoặc tự động trích xuất output từ ChatGPT web.

Muốn tự động 100% thì nên thêm provider chính thức:
- OpenAI API
- Gemini API
- Local model/offline model

## Cài đặt

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python main.py
```

## Lưu ý

- Bản này ưu tiên PDF.
- DOCX/TXT có thể thêm sau.
- Chất lượng dựng PDF phụ thuộc độ phức tạp layout.
- Công thức dạng ảnh được giữ nguyên vì app dựng trên ảnh nền của trang gốc.
- Text dịch được phủ lên vùng text gốc.
