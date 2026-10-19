---
description: Cài Telegram bot nhận thông báo đơn hàng realtime
argument-hint: [bước]
---

Cài hệ thống thông báo Telegram tự động cho mọi đơn hàng.

<args>$ARGUMENTS</args>

## Các Bước

- `start` — Bắt đầu từ đầu (tạo bot → nhận thông báo đầu tiên)
- `bot` — Tạo Telegram bot qua @BotFather
- `webhook` — Kết nối SePay webhook với Telegram bot
- `test` — Gửi thông báo test
- `templates` — Lấy các mẫu tin nhắn thông báo sẵn dùng
- `zalo` — Hướng dẫn tích hợp bổ sung qua Zalo OA

## Quy Trình

1. Kích hoạt Deliver Agent
2. Dùng skill Notification Setup Guide
3. Hướng dẫn cài Telegram bot + pipeline webhook
4. Output: Pipeline thông báo hoạt động hoàn chỉnh

## Ví Dụ

- `/kit-notify start` — Hướng dẫn đầy đủ từ tạo bot đến nhận cảnh báo đầu tiên
- `/kit-notify templates` — Lấy mẫu tin nhắn cho thanh toán, giao hàng, lỗi
- `/kit-notify webhook` — Kết nối sự kiện thanh toán SePay với Telegram bot
- `/kit-notify bot` — Chỉ hướng dẫn tạo bot và lấy token + chat ID
- `/kit-notify zalo` — Thêm kênh thông báo Zalo OA (75M+ người dùng VN)

## Mẹo Vận Hành

- Tạo Telegram bot qua @BotFather trước — cần bot token cho mọi bước tiếp theo
- Test webhook với ngrok cục bộ trước khi deploy lên production
- Tạo group riêng cho thông báo đơn hàng để tránh bị chìm trong chat cá nhân
- Phân loại thông báo: thanh toán (quan trọng) vs. giao hàng vs. lỗi (tùy chọn mute)

## Mẫu Tin Nhắn Thông Báo Mẫu

```
🛍️ ĐƠN HÀNG MỚI

👤 Khách: Nguyễn Văn A
📦 Sản phẩm: AI Landing Engine Kit
💰 Số tiền: 1,997,000 VNĐ
🏦 Ngân hàng: Vietcombank
✅ Trạng thái: Đã xác nhận
📬 Giao hàng: Email → tự động
🕐 15/01/2025 — 14:23:45
```
