---
description: Tự động hóa giao sản phẩm số sau khi thanh toán
argument-hint: [phương thức]
---

Cài hệ thống giao sản phẩm số tự động — không cần thao tác thủ công.

<args>$ARGUMENTS</args>

## Phương Thức Giao Hàng

- `email` — Email + link tải xuống (có hạn thời gian)
- `redirect` — Redirect sang trang được bảo vệ bằng token
- `telegram` — Telegram bot tự động gửi file/link
- `compare` — So sánh tất cả phương thức (tốc độ, chi phí, UX)
- `post-purchase` — Cài chuỗi tương tác sau mua (7 điểm chạm)

## Quy Trình

1. Kích hoạt Deliver Agent
2. Dùng skill Delivery Setup Guide
3. Cấu hình phương thức giao hàng đã chọn + chuỗi tương tác sau mua
4. Output: Pipeline giao hàng tự động hoạt động

## Ví Dụ

- `/kit-deliver email` — Cài giao hàng tự động qua email với link tải xuống
- `/kit-deliver telegram` — Cấu hình bot Telegram tự gửi file sau thanh toán
- `/kit-deliver compare` — So sánh 4 phương thức: tốc độ, chi phí, độ phức tạp, UX
- `/kit-deliver post-purchase` — Xây chuỗi 7 điểm chạm sau mua (chào mừng → onboard → upsell)

## Chọn Phương Thức Phù Hợp

| Phương Thức | Dùng Cho | Thời Gian Cài | Chi Phí |
|-------------|----------|---------------|---------|
| Email | PDF, template, khóa học | 30 phút | 0–200k/tháng |
| Redirect | Video course, membership | 15 phút | Miễn phí |
| Telegram | File nhanh, cộng đồng | 45 phút | Miễn phí |
| Hybrid | Sản phẩm cao cấp | 60 phút | 0–200k/tháng |

## Mẹo Vận Hành

- Dùng email cho tài liệu và khóa học; Telegram cho hàng hóa số cần truy cập tức thì
- Luôn gửi tin nhắn cảm ơn sau mua — giảm đáng kể tỷ lệ yêu cầu hoàn tiền
- Test toàn bộ luồng mua → giao hàng từ đầu đến cuối trước khi go live
- Implement retry 3 lần nếu giao hàng thất bại — không để khách đợi quá 5 phút
