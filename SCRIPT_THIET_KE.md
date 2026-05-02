# Thiết kế phần mềm Math Translator Pipeline

## Mục tiêu

Phần mềm tự động hóa quy trình dịch tài liệu Toán học theo hướng:
Upload PDF → tách từng trang → tạo prompt → dịch từng trang → dựng lại PDF → ghép file → xóa file tạm.

## Luồng xử lý

1. Người dùng upload PDF.
2. Hệ thống tạo một session tạm.
3. Hệ thống tách PDF thành từng file nhỏ, mỗi file gồm một trang.
4. Hệ thống render từng trang thành ảnh PNG để preview.
5. Hệ thống trích xuất các block văn bản và tọa độ.
6. Hệ thống tạo prompt cố định cho từng trang.
7. Người dùng mở cửa sổ ChatGPT và đăng nhập thủ công.
8. Người dùng copy prompt vào ChatGPT.
9. ChatGPT trả về JSON bản dịch.
10. Người dùng dán JSON vào phần mềm.
11. Phần mềm phủ bản dịch vào đúng vùng text.
12. Phần mềm dựng lại từng trang PDF.
13. Phần mềm ghép các trang thành một PDF lớn.
14. Phần mềm xóa các file phụ.

## Ranh giới an toàn

Phần mềm không tự động điều khiển ChatGPT web, không lấy cookie, không đọc session, không tự gửi tin nhắn và không tự trích xuất output từ cửa sổ ChatGPT.

Nếu muốn tự động hóa 100%, nên thêm provider chính thức như OpenAI API, Gemini API hoặc local model.
