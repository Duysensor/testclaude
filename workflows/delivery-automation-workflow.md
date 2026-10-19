# Workflow: Tự Động Hóa Hệ Thống Giao Hàng

**Thương hiệu:** 10xSystem  
**Bộ kit:** AI Landing Engine Kit  
**Thời gian hoàn thành:** 1–2 giờ  
**Output:** Hệ thống giao hàng zero-touch hoàn chỉnh — thanh toán → thông báo → giao sản phẩm tự động  

---

## Kết Quả Sau Khi Hoàn Thành Workflow

```
✅ Landing page live trên URL public (Vercel)
✅ QR thanh toán SePay VietQR tích hợp
✅ Telegram bot nhận thông báo realtime
✅ Tự động giao sản phẩm sau thanh toán
✅ Chuỗi tương tác sau mua được cài đặt
```

---

## Phase 1: Deploy Landing Page (15–20 phút)

### Bước 1.1 — Cài Vercel CLI
```bash
# Cài Node.js trước (nếu chưa có) — nodejs.org
node --version  # Kiểm tra: phải hiện v18+

# Cài Vercel CLI toàn cục
npm install -g vercel

# Đăng nhập
vercel login
```

### Bước 1.2 — Deploy Lên Production
```
/kit-deploy vercel
```

Sau khi chạy lệnh trong folder project:
```bash
vercel --prod
```

→ Nhận URL live: `https://your-page.vercel.app`

### Bước 1.3 — Kiểm Tra Sau Deploy
```
Checklist:
✅ Trang load tại URL .vercel.app
✅ Mobile responsive (mở trên điện thoại)
✅ QR payment hiển thị đúng
✅ Tất cả links hoạt động
✅ SSL certificate (ổ khóa xanh)
```

---

## Phase 2: Cài Thanh Toán SePay (20–30 phút)

### Bước 2.1 — Tạo Tài Khoản SePay
```
/kit-payment-setup start
```

Hướng dẫn sẽ đi qua:
- Đăng ký tại my.sepay.vn
- Kết nối tài khoản ngân hàng
- Lấy API token

### Bước 2.2 — Cập Nhật QR Trong Landing Page

Sau khi có tài khoản SePay, cập nhật trong `index.html`:
```html
<!-- Tìm và thay thế các placeholder này -->
YOUR_ACCOUNT → [Số TK ngân hàng của bạn]
YOUR_BANK    → [Tên ngân hàng: Vietcombank, VPBank...]
YOUR_AMOUNT  → [Giá bán: 1997000]
YOUR_PRODUCT → [Mã sản phẩm: KIT_001]
```

### Bước 2.3 — Test QR Payment
```
/kit-payment-setup test
```
1. Mở trang live trên điện thoại
2. Quét QR bằng app ngân hàng
3. Xác nhận số tiền và nội dung đúng
4. Hủy trước khi xác nhận (chỉ test UI)

---

## Phase 3: Cài Thông Báo Telegram (20–30 phút)

### Bước 3.1 — Tạo Bot
```
/kit-notify bot
```

Hướng dẫn từng bước:
1. Nhắn @BotFather trên Telegram
2. Gõ `/newbot` → Đặt tên → Nhận bot token
3. Tạo group riêng cho thông báo
4. Add bot vào group
5. Lấy Chat ID bằng cách gọi API

### Bước 3.2 — Kết Nối SePay → Telegram
```
/kit-notify webhook
```

→ Nhận code webhook handler, cấu hình:
- `BOT_TOKEN` → Token từ @BotFather
- `CHAT_ID` → ID của group thông báo
- `SEPAY_API_TOKEN` → Token từ SePay dashboard

### Bước 3.3 — Test Thông Báo
```
/kit-notify test
```

Gửi test notification và xác nhận:
```
✅ Bot đã gửi tin nhắn vào group
✅ Tin nhắn format đúng (emoji, thông tin đủ)
✅ Nhận được trên mobile
```

---

## Phase 4: Cài Giao Hàng Tự Động (20–30 phút)

### Bước 4.1 — Chọn Phương Thức Giao Hàng

```
/kit-deliver compare
```

**Khuyến nghị theo loại sản phẩm:**
- PDF/Template/Tài liệu → Email + link tải
- Khóa học có video → Redirect to protected page
- File nhỏ + cộng đồng → Telegram bot
- Sản phẩm cao cấp → Hybrid (email + Telegram)

### Bước 4.2 — Cài Delivery System

```
/kit-deliver [phương thức đã chọn]
```

→ Nhận code và hướng dẫn deploy webhook server

**Cài server (với email delivery):**
```bash
# Cài dependencies
npm install express nodemailer dotenv

# Tạo .env file
SEPAY_TOKEN=xxx
TELEGRAM_BOT_TOKEN=xxx
TELEGRAM_CHAT_ID=xxx
EMAIL_HOST=smtp.gmail.com
EMAIL_USER=your@email.com
EMAIL_PASS=xxx
PRODUCT_DOWNLOAD_URL=https://drive.google.com/...

# Chạy server
node server.js
```

### Bước 4.3 — Cài Post-Purchase Sequence
```
/kit-deliver post-purchase
```

→ Nhận template chuỗi 7 email theo lịch:
- Ngay: Cảm ơn + Link truy cập
- Ngày 1: Hướng dẫn bắt đầu
- Ngày 3: Quick win tip
- Ngày 5: Check-in
- Ngày 7: Yêu cầu testimonial
- Ngày 14: Offer upsell

---

## Phase 5: Test Toàn Bộ Luồng (15–20 phút)

### Test End-to-End

```
Scenario test:
1. Mở trang landing page trên mobile
2. Cuộn qua tất cả sections
3. Click "Mua Ngay" → QR modal hiện
4. Thực hiện thanh toán thật (số tiền nhỏ để test: 10,000 VNĐ)
5. Xác nhận nhận thông báo Telegram
6. Xác nhận nhận email giao hàng
7. Click link tải → Download thành công
```

### Checklist Final

```
✅ Trang live, load nhanh (< 3 giây)
✅ QR thanh toán hoạt động với app ngân hàng thật
✅ Nhận thông báo Telegram trong < 30 giây
✅ Email giao hàng đến inbox (không vào spam)
✅ Link tải xuống hoạt động
✅ Post-purchase email sequence đã cài
```

---

## Troubleshoot Nhanh

| Vấn Đề | Nguyên Nhân | Fix |
|--------|-------------|-----|
| QR không load | URL sai parameter | Kiểm tra tên ngân hàng chính xác |
| Không nhận Telegram | Webhook URL sai | Xác minh HTTPS, check logs |
| Email vào spam | SMTP không đúng | Dùng transactional email (SendGrid) |
| Webhook không fire | SePay chưa cấu hình | Kiểm tra URL webhook trong dashboard |
| Server lỗi | Thiếu env variables | Check .env file đầy đủ |

---

## Bước Tiếp Theo

Sau khi hoàn thành workflow này:
- Chia sẻ URL landing page để thu traffic
- Theo dõi conversion rate hàng ngày
- Collect testimonials từ khách hàng đầu tiên
- Dùng testimonials để cải thiện trang

---

*AI Landing Engine Kit — Delivery Automation Workflow | by 10xSystem*
