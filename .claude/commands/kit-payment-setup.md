---
description: Hướng dẫn cài đặt SePay VietQR từng bước — từ tạo tài khoản đến webhook
argument-hint: [start|api|qr|webhook|test|compare]
---

Anh/chị đang yêu cầu hướng dẫn cài đặt thanh toán SePay VietQR.

<args>$ARGUMENTS</args>

## Thực Thi

Đọc và áp dụng theo thứ tự:
1. Load `agents/02-deliver-agent.md` — System prompt Deliver Agent
2. Load `skills/payment-setup-guide/SKILL.md` — Payment setup skill
3. Load `skills/payment-setup-guide/references/payment-gateway-integration-guide.md`
4. Load `skills/payment-setup-guide/references/checkout-flow-design-patterns.md`

## Actions

- **start** → Hướng dẫn đầy đủ từ đầu: tạo tài khoản → xác minh → API → QR đầu tiên
- **api** → Cấu hình API token, xác thực, lưu trữ an toàn
- **qr** → Tạo VietQR payment link với đúng parameters
- **webhook** → Cài endpoint nhận webhook + code xác minh HMAC
- **test** → Test transaction đầy đủ trong sandbox environment
- **compare** → So sánh SePay vs. Manual transfer vs. Stripe cho use case của anh/chị

## Yêu Cầu Output

- Hướng dẫn từng bước rõ ràng (có thể follow ngay)
- Code examples đầy đủ (Node.js) với chú thích tiếng Việt
- Checklist kiểm tra sau mỗi bước
- Lỗi thường gặp và cách fix

## Lưu Ý Bảo Mật

```
⚠️ KHÔNG bao giờ hardcode API keys trong source code
⚠️ LUÔN xác minh HMAC signature trên mọi webhook
⚠️ Dùng sandbox trước, production sau khi test xong
⚠️ Implement deduplication để tránh giao hàng 2 lần
```
