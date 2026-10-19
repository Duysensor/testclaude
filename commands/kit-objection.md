---
description: Xây hệ thống xử lý từ chối của khách hàng
argument-hint: [loại từ chối hoặc nội dung cụ thể]
---

Tạo phản hồi thuyết phục cho mọi từ chối của khách hàng.

<args>$ARGUMENTS</args>

## Loại Từ Chối

- `price` — Từ chối về giá ("đắt quá", "không có tiền")
- `trust` — Từ chối về tin tưởng ("không biết anh/chị là ai")
- `timing` — Từ chối về thời điểm ("để sau", "chưa phải lúc")
- `need` — Từ chối về nhu cầu ("mình không cần cái này")
- `scam` — Từ chối về lừa đảo ("có phải lừa đảo không?") ← Số 1 VN market
- `authority` — Từ chối về thẩm quyền ("để hỏi vợ/chồng/sếp")
- `[nội dung cụ thể]` — Phân loại và phản hồi bất kỳ từ chối nào

## Quy Trình

1. Kích hoạt Conversion Agent
2. Dùng skill Objection Handler
3. Phân loại từ chối → Chọn kỹ thuật reframe → Soạn phản hồi
4. Output: Script phản hồi + gợi ý copy preemptive

## Ví Dụ

- `/kit-objection price khóa học online` — Reframe "đắt quá" cho khóa học số
- `/kit-objection trust thương hiệu mới` — Xử lý "không biết anh/chị" cho brand mới ra mắt
- `/kit-objection scam template landing page` — Hóa giải "lừa đảo không?" — từ chối số 1 VN
- `/kit-objection timing offer giới hạn` — Vượt qua "để mua sau" với offer có thời hạn

## Mẹo Tối Ưu

- Giải quyết từ chối TRƯỚC KHI chúng xuất hiện trong trang — đừng chờ đến DMs
- "Có phải lừa đảo không?" là từ chối số 1 thị trường VN — luôn chuẩn bị sẵn
- Kết hợp với `/kit-sales-page` để nhúng phản hồi từ chối thẳng vào copy
- Từ chối về giá: đừng so sánh với đối thủ — hãy so sánh với chi phí của việc KHÔNG giải quyết vấn đề

## Framework Xử Lý Từ Chối

```
1. Thừa nhận → Xác nhận lo ngại của khách hàng
2. Làm rõ    → Tìm ra từ chối thực sự ẩn bên dưới
3. Reframe   → Đổi góc nhìn, không phản bác
4. Bằng chứng → Proof points, testimonials, data
5. Redirect  → Dẫn về hành động tiếp theo
```
