# simple-voice-to-text-core

[English](README.md) | Tiếng Việt

Thư viện lõi chuyển giọng nói thành văn bản, chạy offline, viết bằng TypeScript. Ưu tiên tiếng Việt.

> Trạng thái: đang khởi tạo, chưa có code chạy được.

## Mục tiêu

- **Input:** file ghi âm (ưu tiên làm trước) và ghi âm trực tiếp từ mic.
- **Output:** văn bản (đoạn văn) từ đoạn ghi âm đó.
- Chạy bằng model offline, đoán được lời nói kể cả khi giọng không rõ.
- Chạy được trên cả máy yếu (CPU) lẫn máy có GPU.
- Cài đặt và thiết lập dễ dàng, sau này dùng được trên nhiều nền tảng.

## Phạm vi của repo này

Repo chỉ chứa **phần lõi xử lý**, chưa phải một app hoàn chỉnh. Lõi không tự in ra màn hình hay đọc tham số dòng lệnh; mọi thứ vào/ra đều qua hàm và giá trị trả về. Một CLI nhỏ đi kèm để chạy thử và làm ví dụ cách dùng lõi.

Các app (desktop, mobile, web) sẽ làm sau, ở repo riêng, và dùng lại lõi này.

## Quyết định đã chốt

| Mục | Lựa chọn |
| --- | --- |
| Ngôn ngữ | TypeScript (JS/TS, ưu tiên TS) |
| Giao diện đầu tiên | CLI (terminal) |
| Nhận diện giọng nói | Model chạy offline |
| Ngôn ngữ đầu tiên | Tiếng Việt |
| Nền tảng thử nghiệm đầu | Windows 11 |

## Lộ trình

- [ ] **Bước 0:** chạy thử model bằng tay trên đoạn ghi âm 30-60 giây, so sánh chất lượng và tốc độ (CPU và GPU), chọn model và thư viện.
- [ ] **Bước 1:** CLI nhận đường dẫn file, chuyển sang định dạng model cần, gọi model, in text ra terminal.
- [ ] **Bước 2:** hỗ trợ file dài (chia đoạn), hiển thị tiến trình, lưu ra file `.txt`, xử lý lỗi.
- [ ] **Bước 3:** ghi âm trực tiếp từ mic.
- [ ] **Bước 4:** thử khử ồn và đo hiệu quả trước/sau (chỉ giữ lại nếu thật sự cải thiện).
- [ ] **Sau này:** desktop app, mobile app, web app (nếu cần) với giao diện đơn giản, thực dụng.

## Nguyên tắc thiết kế

- Chia phần xử lý thành các module tách biệt: đọc/chuyển đổi audio, transcriber, xuất kết quả.
- Dễ đổi model mà không phải sửa phần còn lại.
- Ưu tiên thư viện có binary build sẵn để người dùng không phải tự biên dịch.
- Model tải tự động ở lần chạy đầu, có hiển thị tiến trình.

## Ghi chú

- File ghi âm và file model **không** được commit (xem `.gitignore`).
- Dự án làm để học và để dùng cho nhu cầu cá nhân: tự viết phần lõi, dùng AI để giải thích, review và hỗ trợ phần phụ.

## Giấy phép

Chưa chọn.
