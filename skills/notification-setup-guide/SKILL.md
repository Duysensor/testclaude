---
name: notification-setup-guide
description: Cài hệ thống thông báo realtime qua Telegram bot — nhận cảnh báo đơn hàng ngay khi khách thanh toán
version: 2.0.0
kit: AI Landing Engine Kit by 10xSystem
---

# Notification Setup Guide Skill

## Kích Hoạt Skill Này Khi

- Cài thông báo đơn hàng realtime cho solopreneur
- Cấu hình Telegram bot cho business alerts
- Triển khai notification pipeline dựa trên webhook
- Tạo automated payment và lead alerts
- Thiết kế message templates thông báo
- Troubleshoot lỗi notification không gửi được

---

## Tổng Quan

Skill này cung cấp hướng dẫn toàn diện để triển khai hệ thống thông báo tự động dùng Telegram. Thiết kế cho solopreneur bán sản phẩm số, bao gồm cài bot, tích hợp webhook và message templating.

**Kênh chính:** Telegram (bot-based notifications)
**Cách tiếp cận:** Code/webhook-based automation
**Đối tượng:** Solopreneur, SME, developer

---

## Workflow Cài Đặt Nhanh

```
Bước 1: Tạo Telegram Bot
         ├─ Nhắn @BotFather để tạo bot
         ├─ Nhận bot token
         └─ Cấu hình tên và description bot

Bước 2: Chuẩn Bị Kênh Nhận Thông Báo
         ├─ Tạo Telegram group/channel riêng
         ├─ Thêm bot vào group
         └─ Lấy Chat ID

Bước 3: Triển Khai Webhook Pipeline
         ├─ Cài webhook endpoint trên server
         ├─ Parse payment gateway payloads
         ├─ Format notification messages
         └─ Gửi đến Telegram API

Bước 4: Test Toàn Bộ Pipeline
         ├─ Gửi test transactions
         ├─ Xác minh message delivery
         └─ Monitor error logs
```

---

## Kiến Trúc Hệ Thống

```
┌─────────────────┐
│  SePay / Gateway │  ← Nguồn sự kiện thanh toán
└────────┬────────┘
         │ Webhook POST (HTTPS)
         ▼
┌─────────────────┐
│  Server của bạn  │  ← Node.js/Express
│  - Parse payload │
│  - Format msg    │
│  - Error handle  │
└────────┬────────┘
         │ HTTPS Request đến Telegram API
         ▼
┌─────────────────┐
│ Telegram Bot API │
└────────┬────────┘
         │ Message
         ▼
┌─────────────────┐
│ Telegram Group  │  → Chủ kinh doanh nhận cảnh báo tức thì
└─────────────────┘
```

---

## Reference Files

### 1. [telegram-bot-notification-setup.md](references/telegram-bot-notification-setup.md)
Hướng dẫn tạo và cấu hình Telegram bot đầy đủ:
- Tạo bot từng bước qua @BotFather
- Lấy token và chat ID
- Sử dụng API endpoint
- Security best practices
- Troubleshoot lỗi thường gặp

### 2. [webhook-to-notification-pipeline.md](references/webhook-to-notification-pipeline.md)
Hướng dẫn triển khai webhook-based notifications:
- Architecture và data flow
- Ví dụ Node.js và PHP
- Error handling và retry logic
- Logging và monitoring
- Testing strategies

### 3. [notification-message-templates.md](references/notification-message-templates.md)
Templates tin nhắn sẵn dùng cho mọi tình huống:
- Thông báo đơn hàng mới
- Cập nhật trạng thái thanh toán
- Daily summaries
- Lead alerts
- Template variable reference
- Formatting guidelines

---

## Use Cases Phổ Biến

### 1. Thông Báo Đơn Hàng E-commerce
```
🛍️ ĐƠN HÀNG MỚI #001

👤 Khách: Nguyễn Văn A
📦 Sản phẩm: AI Landing Engine Kit
💰 Số tiền: 1,997,000 VNĐ
🏦 Ngân hàng: Vietcombank
✅ Trạng thái: Đã xác nhận
📬 Giao hàng: Email tự động
🕐 15/01/2025 — 14:23:45
```

### 2. Lead Generation Alerts
```
🎯 LEAD MỚI

📧 Email: customer@email.com
📝 Form: Landing Page Kit Interest
🔗 Source: Facebook Ad
🕐 15/01/2025 — 14:25:00
```

### 3. Daily Revenue Summary
```
📊 BÁO CÁO NGÀY 15/01/2025

💰 Doanh thu: 9,985,000 VNĐ
📦 Đơn hàng: 5 đơn
✅ Giao thành công: 5/5
⚡ Trung bình/đơn: 1,997,000 VNĐ
```

---

## Tips Triển Khai

- **Bắt đầu đơn giản:** Cài thông báo đơn hàng cơ bản trước, mở rộng dần
- **Test kỹ:** Dùng sandbox/test mode trước production
- **Bảo mật token:** Không commit API tokens vào version control
- **Monitor delivery:** Log mọi lần gửi và các lần thất bại
- **UX tin nhắn:** Ngắn gọn, actionable, emoji có chọn lọc
- **Fallback plan:** Có phương thức thay thế nếu Telegram gặp sự cố

---

## Zalo OA (Tùy Chọn Thêm)

Cho thị trường Việt Nam, xem xét thêm Zalo OA:
- Đăng ký tại oa.zalo.me
- Dùng Zalo OA API để gửi thông báo cho followers
- Tốt nhất cho: Giao tiếp với khách hàng (75M+ người dùng VN)
- Cần: Business verification trên nền tảng Zalo
- Notification flow: Cùng webhook pipeline, thay API call Telegram bằng Zalo OA Send Message API

*AI Landing Engine Kit | Skill: Notification Setup Guide | by 10xSystem*
