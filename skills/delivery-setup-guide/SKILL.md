---
name: delivery-setup-guide
description: Hệ thống giao sản phẩm số tự động — email, redirect và Telegram bot — khách nhận hàng trong 60 giây sau thanh toán
version: 2.0.0
kit: AI Landing Engine Kit by 10xSystem
---

# Auto Delivery Setup Guide Skill

Hệ thống fulfillment tự động cho sản phẩm số. Giao hàng ngay sau thanh toán qua email, redirect links hoặc Telegram bot — không cần thao tác thủ công.

## Kích Hoạt Skill Này Khi

- Cài tự động giao hàng lần đầu tiên
- Thay thế quy trình gửi thủ công sau thanh toán
- Cấu hình giao hàng đa kênh (email + Telegram)
- Xây fulfillment có thể scale mà không dùng Gumroad/Payhip
- Đảm bảo truy cập sản phẩm số tức thì

---

## So Sánh Phương Thức Giao Hàng

| Phương Thức | Thời Gian Cài | Chi Phí | Tốt Nhất Cho | Độ Tin Cậy |
|-------------|---------------|---------|-------------|------------|
| Email | 30 phút | 0–200k/tháng | Tài liệu, khóa học, file < 50MB | Cao |
| Redirect | 15 phút | Miễn phí | Links đến hosted content | Rất Cao |
| Telegram | 45 phút | Miễn phí | Cộng đồng + nội dung, tương tác ongoing | Cao |
| Hybrid | 60 phút | 0–200k/tháng | Sản phẩm cao cấp, reach tối đa | Cao Nhất |

---

## Workflow Cài Đặt Nhanh

```
Bước 1: Chọn phương thức giao hàng
         └─> Email: Cài transactional service + template
         └─> Redirect: Tạo access page + token system
         └─> Telegram: Build bot + webhook handler

Bước 2: Cấu hình webhook receiver
         └─> Parse payment data
         └─> Trigger delivery function
         └─> Log transaction

Bước 3: Triển khai delivery logic
         └─> Generate secure access link
         └─> Gửi qua kênh đã chọn
         └─> Confirm delivery

Bước 4: Cài error handling
         └─> Retry khi delivery thất bại (3 lần)
         └─> Alert khi có lỗi nghiêm trọng
         └─> Manual override option

Bước 5: Test end-to-end
         └─> Test luồng payment → delivery
         └─> Xác minh access links hoạt động
         └─> Kiểm tra delivery timing
```

---

## Kiến Trúc Hệ Thống

```
SePay/Payment Gateway
    ↓ (webhook)
Webhook Handler (Node.js/Express)
    ↓ (xác minh thanh toán)
Delivery Orchestrator
    ├─> Email Service     → Hộp thư khách hàng
    ├─> Redirect Generator → Trang truy cập
    └─> Telegram Bot      → Tin nhắn trực tiếp / Private Channel
```

---

## Reference Files

### [digital-product-delivery-methods.md](references/digital-product-delivery-methods.md)
So sánh chi tiết email, redirect và Telegram delivery. Cân nhắc bảo mật, hướng dẫn cài đặt, pros/cons từng phương thức.

### [automated-delivery-workflow.md](references/automated-delivery-workflow.md)
Triển khai kỹ thuật đầy đủ. Webhook handling, code examples giao hàng (có chú thích tiếng Việt), error handling, retry mechanisms, monitoring.

### [post-purchase-engagement-sequence.md](references/post-purchase-engagement-sequence.md)
Chuỗi 7 điểm chạm từ mua đến upsell. Email/Telegram templates, chiến lược timing, hướng dẫn automation.

---

## Nguyên Tắc Cốt Lõi

**Giao tức thì** — Khách nhận truy cập trong 60 giây sau thanh toán  
**Dự phòng** — Dùng 2+ kênh cho sản phẩm giá trị cao  
**Bảo mật** — Token có hạn thời gian, one-time access links  
**Monitoring** — Log mọi giao hàng, alert khi thất bại  
**Đơn giản** — Dùng hạ tầng có sẵn, tránh vendor lock-in  

---

## Chuỗi Tương Tác Sau Mua (7 Điểm Chạm)

```
Ngay lập tức: Cảm ơn + xác nhận truy cập (Telegram/Email)
Ngày 1:       Hướng dẫn bắt đầu (Email)
Ngày 3:       Quick win tip — tăng perceived value (Email)
Ngày 5:       Check-in hỗ trợ (Telegram)
Ngày 7:       Yêu cầu testimonial (Email)
Ngày 14:      Offer upsell/cross-sell (Email + Telegram)
```

---

## Common Pitfalls — Tránh Những Lỗi Này

- Dùng marketing email cho transactional sends → deliverability kém
- Không có retry mechanism khi delivery thất bại → khách không nhận được
- Link không bảo mật, có thể share công khai → mất doanh thu
- Không log delivery confirmation → không support được khi có tranh chấp
- Setup phức tạp → dễ break, khó maintain

---

## Success Metrics

- **Delivery success rate:** > 99%
- **Average delivery time:** < 60 giây
- **Support requests về access:** < 2%
- **Link security breach:** 0

*AI Landing Engine Kit | Skill: Delivery Setup Guide | by 10xSystem*
