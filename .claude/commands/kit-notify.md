---
description: Cài Telegram bot nhận thông báo đơn hàng realtime — từ tạo bot đến test
argument-hint: [start|bot|webhook|test|templates|zalo]
---

Anh/chị đang yêu cầu cài hệ thống thông báo Telegram tự động.

<args>$ARGUMENTS</args>

## Thực Thi

Đọc và áp dụng theo thứ tự:
1. Load `agents/02-deliver-agent.md` — System prompt Deliver Agent
2. Load `skills/notification-setup-guide/SKILL.md` — Notification skill
3. Load `skills/notification-setup-guide/references/telegram-bot-notification-setup.md`
4. Load `skills/notification-setup-guide/references/webhook-to-notification-pipeline.md`
5. Load `skills/notification-setup-guide/references/notification-message-templates.md`

## Actions

- **start** → Hướng dẫn đầy đủ: tạo bot → lấy token → cài webhook → test
- **bot** → Chỉ tạo bot @BotFather và lấy token + chat ID
- **webhook** → Kết nối SePay payment events → Telegram notification pipeline
- **test** → Gửi test notification để xác minh pipeline hoạt động
- **templates** → Lấy tất cả mẫu tin nhắn (đơn hàng, giao hàng, lỗi, summary)
- **zalo** → Thêm kênh Zalo OA (tùy chọn, 75M+ người dùng VN)

## Yêu Cầu Output

- Hướng dẫn từng bước với screenshots text description
- Code webhook handler hoàn chỉnh (Node.js) với chú thích tiếng Việt
- Tất cả message templates sẵn dùng
- Hướng dẫn test và troubleshooting

## Mẫu Tin Nhắn Output Chuẩn

```
🛍️ ĐƠN HÀNG MỚI #{ORDER_ID}
👤 Khách: {TÊN_KHÁCH}
📦 Sản phẩm: {TÊN_SẢN_PHẨM}
💰 Số tiền: {SỐ_TIỀN} VNĐ
🏦 Ngân hàng: {NGÂN_HÀNG}
✅ Trạng thái: Đã xác nhận
📬 Giao hàng: {PHƯƠNG_THỨC}
🕐 {NGÀY_GIỜ}
— AI Landing Engine Kit | 10xSystem
```
