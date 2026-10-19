---
description: Cài hệ thống giao sản phẩm số tự động sau thanh toán
argument-hint: [email|redirect|telegram|compare|post-purchase]
---

Anh/chị đang yêu cầu cài tự động giao sản phẩm số.

<args>$ARGUMENTS</args>

## Thực Thi

Đọc và áp dụng theo thứ tự:
1. Load `agents/02-deliver-agent.md` — System prompt Deliver Agent
2. Load `skills/delivery-setup-guide/SKILL.md` — Delivery skill
3. Load `skills/delivery-setup-guide/references/digital-product-delivery-methods.md`
4. Load `skills/delivery-setup-guide/references/automated-delivery-workflow.md`
5. (Nếu cần post-purchase) Load `skills/delivery-setup-guide/references/post-purchase-engagement-sequence.md`

## Actions

- **email** → Cài giao hàng qua email + link tải xuống có hạn thời gian
- **redirect** → Redirect sang trang được bảo vệ bằng unique token
- **telegram** → Bot Telegram tự gửi file/link sau xác nhận thanh toán
- **compare** → Bảng so sánh 4 phương thức: thời gian cài, chi phí, UX, độ tin cậy
- **post-purchase** → Chuỗi 7 điểm chạm sau mua (từ cảm ơn đến upsell ngày 14)

## Yêu Cầu Output

- Code hoàn chỉnh theo phương thức được chọn, có chú thích tiếng Việt
- Checklist cài đặt từng bước
- Hướng dẫn test end-to-end
- Error handling và retry logic

## Luồng Tự Động Chuẩn

```
Webhook SePay → Xác minh HMAC → Kiểm tra trùng lặp
→ Khớp sản phẩm → Log giao dịch → Thông báo Telegram
→ Giao sản phẩm (email/redirect/bot) → Xác nhận khách
→ Kích hoạt chuỗi sau mua
```

Delivery target: **Khách nhận sản phẩm trong 60 giây sau thanh toán.**
