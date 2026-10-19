# Hướng Dẫn Sử Dụng
## AI Landing Engine Kit — by 10xSystem

**Phiên bản:** 1.0  
**Cập nhật:** 2025  

---

## Mục Lục

1. [Cài Đặt Môi Trường](#1-cài-đặt-môi-trường)
2. [Cách Sử Dụng Lệnh](#2-cách-sử-dụng-lệnh)
3. [Hành Trình Nhanh — Bán Hàng Trong 4 Giờ](#3-hành-trình-nhanh)
4. [Hướng Dẫn Từng Lệnh](#4-hướng-dẫn-từng-lệnh)
5. [Lựa Chọn Template Landing Page](#5-lựa-chọn-template)
6. [Tích Hợp SePay VietQR](#6-tích-hợp-sepayvietqr)
7. [Cài Telegram Notifications](#7-cài-telegram-notifications)
8. [Deploy Lên Vercel](#8-deploy-lên-vercel)
9. [FAQ & Troubleshoot](#9-faq--troubleshoot)

---

## 1. Cài Đặt Môi Trường

### Yêu Cầu Cơ Bản

**1. Claude Code CLI**
```bash
# Cài qua npm
npm install -g @anthropic-ai/claude-code

# Xác nhận cài thành công
claude --version
```

**2. Node.js** (cần cho Vercel CLI và backend)
- Tải tại: nodejs.org/en/download
- Phiên bản khuyến nghị: v20 LTS
- Xác nhận: `node --version`

**3. Vercel CLI** (cần cho deploy)
```bash
npm install -g vercel
vercel --version
```

### Mở Kit Trong Claude Code

```bash
# Vào thư mục AI Landing Engine Kit
cd "đường dẫn đến/AI Landing Engine Kit"

# Mở Claude Code
claude

# Kiểm tra CLAUDE.md đã load
# → Claude sẽ xác nhận đang ở trong AI Landing Engine Kit
```

---

## 2. Cách Sử Dụng Lệnh

### Cú Pháp Cơ Bản

```
/kit-[tên lệnh] [tham số]
```

**Ví dụ:**
```
/kit-copy par email subject line
/kit-landing-page course bold
/kit-deploy vercel
```

### Danh Sách 9 Lệnh

| Lệnh | Agent | Dùng Khi |
|------|-------|---------|
| `/kit-copy` | Conversion | Cần viết copy theo công thức |
| `/kit-sales-page` | Conversion | Cần blueprint trang bán hàng |
| `/kit-objection` | Conversion | Cần xử lý từ chối khách hàng |
| `/kit-landing-page` | Conversion | Cần build landing page HTML |
| `/kit-payment-setup` | Deliver | Cần cài SePay VietQR |
| `/kit-notify` | Deliver | Cần cài Telegram bot |
| `/kit-deliver` | Deliver | Cần tự động giao sản phẩm |
| `/kit-deploy` | Deliver | Cần deploy lên Vercel |
| `/kit-qr` | Deliver | Cần nhúng QR thanh toán |

---

## 3. Hành Trình Nhanh

### Launch Hệ Thống Bán Hàng Trong 4 Giờ

```
═══════════════════════════════════════════
   AI LANDING ENGINE KIT — LAUNCH JOURNEY
═══════════════════════════════════════════

GIỜ 1 — XÂY COPY
─────────────────
/kit-sales-page [sản phẩm] [giá]
→ Nhận: Copy 14 sections đầy đủ

/kit-objection scam [sản phẩm]
→ Nhận: Script xử lý "lừa đảo không?"

GIỜ 2 — BUILD TRANG
────────────────────
/kit-landing-page [loại] [phong cách]
→ Nhận: File HTML hoàn chỉnh

/kit-qr modal
→ Nhận: QR payment modal code

GIỜ 3 — CÀI THANH TOÁN
────────────────────────
/kit-payment-setup start
→ Hướng dẫn: Tạo SePay → lấy API token

/kit-notify start
→ Hướng dẫn: Tạo bot Telegram → test

GIỜ 4 — DEPLOY & LIVE
─────────────────────
/kit-deploy vercel
→ Nhận: URL live https://page.vercel.app

/kit-deliver email
→ Nhận: Code tự động giao hàng

✅ HỆ THỐNG BÁN HÀNG SẴN SÀNG!
```

---

## 4. Hướng Dẫn Từng Lệnh

### `/kit-copy` — Viết Copy Thuyết Phục

**Công thức có sẵn:**
- `par` — Khi khách biết mình có vấn đề
- `arc` — Cho before/after, testimonial
- `cascade` — Cho traffic lạnh, chưa nhận thức
- `pven` — Cho offer cao cấp, cần trust cao
- `fep` — Cho mô tả sản phẩm ngắn
- `story` — Cho brand narrative, emotional connection

**Ví dụ thực tế:**
```
# Viết email subject line theo PAR
/kit-copy par email subject line cho khóa học online 997k

# Viết headline cho traffic lạnh
/kit-copy cascade headline khóa học copywriting

# Viết mô tả sản phẩm
/kit-copy fep mô tả AI Landing Engine Kit
```

**Output nhận được:**
- Phiên bản chính (có lý giải chiến lược)
- 2–3 biến thể (hooks khác nhau)
- Ghi chú triển khai
- Bản đồ xử lý từ chối

---

### `/kit-sales-page` — Blueprint Trang Bán Hàng

**Actions:**
- Không có → Full 14 sections
- `outline` → Chỉ wireframe và headlines
- `review` → Audit trang hiện có
- `hero` → Chỉ hero section
- `faq` → Chỉ FAQ section

**Ví dụ thực tế:**
```
# Tạo trang bán hàng đầy đủ
/kit-sales-page khóa học viết content cho Facebook 1.497.000 VNĐ

# Chỉ cấu trúc wireframe
/kit-sales-page outline dịch vụ tư vấn SEO

# Review trang hiện có
/kit-sales-page review [paste nội dung trang]
```

**Output nhận được:**
- Copy đầy đủ 14 sections
- Lý giải chiến lược từng section
- Ghi chú mobile optimization
- Gợi ý A/B test

---

### `/kit-objection` — Xử Lý Từ Chối

**Loại từ chối:**
- `scam` — "Có phải lừa đảo không?" ← Ưu tiên #1
- `price` — "Đắt quá"
- `trust` — "Không biết anh/chị"
- `timing` — "Để sau"
- `need` — "Không cần"
- `authority` — "Để hỏi vợ/chồng"

**Ví dụ thực tế:**
```
# Xử lý từ chối lừa đảo (luôn làm đầu tiên)
/kit-objection scam AI Landing Engine Kit

# Xử lý đắt quá
/kit-objection price khóa học 1.997.000 VNĐ

# Xử lý tùy chỉnh
/kit-objection "Tôi không có thời gian" khóa học online
```

**Output nhận được:**
- Phân loại từ chối
- Phân tích nỗi sợ gốc rễ
- Script phản hồi 5 bước
- Copy preemptive để nhúng vào trang

---

### `/kit-landing-page` — Build HTML Landing Page

**Loại sản phẩm:**
`service` `course` `saas` `ecommerce` `lead-magnet` `event`

**Phong cách:**
`minimal` `bold` `elegant` `tech` `warm`

**Ví dụ thực tế:**
```
# Trang khóa học bold, ấn tượng
/kit-landing-page course bold

# Trang dịch vụ tư vấn tối giản, chuyên nghiệp
/kit-landing-page service minimal

# Trang SaaS tool modern
/kit-landing-page saas tech

# Trang thu email, thân thiện
/kit-landing-page lead-magnet warm
```

**Output nhận được:**
- File HTML đầy đủ từ `<!DOCTYPE>` đến `</html>`
- Tailwind CSS via CDN
- Section thanh toán SePay
- Placeholder rõ ràng để thay thế

---

### `/kit-payment-setup` — Cài SePay VietQR

**Các bước:**
`start` → `api` → `qr` → `webhook` → `test`

**Ví dụ thực tế:**
```
# Bắt đầu từ đầu
/kit-payment-setup start

# Chỉ cài webhook
/kit-payment-setup webhook

# Test toàn bộ luồng
/kit-payment-setup test

# So sánh options
/kit-payment-setup compare
```

**Output nhận được:**
- Hướng dẫn từng bước có thể follow ngay
- Code webhook handler (Node.js) với chú thích tiếng Việt
- Checklist bảo mật bắt buộc

---

### `/kit-notify` — Cài Telegram Bot

**Các bước:**
`start` → `bot` → `webhook` → `test` → `templates`

**Ví dụ thực tế:**
```
# Hướng dẫn đầy đủ từ đầu
/kit-notify start

# Chỉ tạo bot và lấy token
/kit-notify bot

# Lấy tất cả message templates
/kit-notify templates
```

**Output nhận được:**
- Hướng dẫn tạo bot @BotFather
- Code kết nối webhook → Telegram
- Tất cả message templates sẵn dùng

---

### `/kit-deliver` — Tự Động Giao Hàng

**Phương thức:**
`email` `redirect` `telegram` `compare` `post-purchase`

**Ví dụ thực tế:**
```
# So sánh phương thức (làm trước)
/kit-deliver compare

# Cài email delivery
/kit-deliver email

# Cài chuỗi sau mua
/kit-deliver post-purchase
```

**Output nhận được:**
- Code delivery handler hoàn chỉnh
- Hướng dẫn deploy server
- Chuỗi 7 email sau mua templates

---

### `/kit-deploy` — Deploy Lên Vercel

**Phương thức:**
`vercel`/`cli` → `git` → `drag` → `domain`

**Ví dụ thực tế:**
```
# Deploy ngay qua CLI (khuyến nghị)
/kit-deploy vercel

# Cài auto-deploy từ GitHub
/kit-deploy git

# Gắn tên miền riêng
/kit-deploy domain
```

**Sau khi deploy:**
- URL live: `https://ten-trang.vercel.app`
- Tự động SSL
- 100GB bandwidth/tháng miễn phí

---

### `/kit-qr` — Nhúng QR Thanh Toán

**Kiểu nhúng:**
`qr` `pricing` `modal` `dynamic` `multi`

**Ví dụ thực tế:**
```
# QR đơn giản (dễ nhất)
/kit-qr qr

# Modal popup (UX tốt nhất, khuyến nghị)
/kit-qr modal

# Pricing cards với QR
/kit-qr pricing

# Nhiều sản phẩm
/kit-qr multi
```

**Sau khi nhận code:**
1. Copy code vào `index.html`
2. Thay `YOUR_ACCOUNT` → Số TK SePay
3. Thay `YOUR_BANK` → Tên ngân hàng
4. Thay `YOUR_AMOUNT` → Giá (số nguyên VNĐ)
5. Test bằng app ngân hàng thực

---

## 5. Lựa Chọn Template Landing Page

### 10 Templates Có Sẵn

| Template File | Phong Cách | Tốt Nhất Cho |
|--------------|-----------|-------------|
| `landing-page-template.html` | Standard Light | Dịch vụ, sản phẩm chung |
| `landing-page-dark-modern.html` | Dark + Gradient | Tech, SaaS, AI tools |
| `landing-page-minimal-clean.html` | Minimal + Serif | Tư vấn cao cấp, coaching |
| `landing-page-creative-bold.html` | Creative Bold | Marketing, sáng tạo |
| `landing-page-saas-product.html` | SaaS Focused | Phần mềm, app |
| `landing-page-ecommerce-product.html` | E-commerce | Sản phẩm vật lý/số |
| `landing-page-webinar-event.html` | Event | Webinar, workshop, event |
| `landing-page-portfolio-personal.html` | Portfolio | Personal brand, freelancer |
| `landing-page-restaurant-food.html` | Warm Food | F&B, nhà hàng, quán ăn |
| `landing-page-mobile-app.html` | App Store Style | Mobile app, SaaS |

### Cách Dùng Template

**Option A: Dùng template trực tiếp**
```bash
# Mở template trong text editor
# Tìm và thay thế:
# YOUR_PRODUCT_NAME → Tên sản phẩm
# YOUR_TAGLINE → Tagline
# YOUR_PRICE → Giá
# YOUR_ACCOUNT → Số TK SePay
# YOUR_BANK → Ngân hàng
```

**Option B: Generate mới từ lệnh (khuyến nghị)**
```
/kit-landing-page course bold
```
Claude sẽ tạo file HTML mới dựa trên brief của anh/chị, không phải template cứng.

---

## 6. Tích Hợp SePay VietQR

### Bước 1: Tạo Tài Khoản SePay
1. Vào my.sepay.vn
2. Đăng ký tài khoản
3. Xác minh định danh
4. Kết nối tài khoản ngân hàng

### Bước 2: Lấy API Token
1. Đăng nhập dashboard
2. Settings → API → Generate Token
3. Copy và lưu token (chỉ hiển thị 1 lần)

### Bước 3: Test QR URL
```
Mở link này trong browser:
https://qr.sepay.vn/img?acc=SỐ_TK&bank=NGÂN_HÀNG&amount=10000&des=TEST

Phải hiển thị QR code hợp lệ
```

### Bước 4: Nhúng Vào Landing Page
```
/kit-qr modal
```
Thay các placeholder trong code nhận được.

### Tên Ngân Hàng Đúng Định Dạng
```
Vietcombank    VPBank    BIDV
Techcombank    ACB       MBBank
Sacombank      VietinBank TPBank
```
Danh sách đầy đủ: https://qr.sepay.vn/banks.json

---

## 7. Cài Telegram Notifications

### Bước 1: Tạo Bot
1. Mở Telegram, tìm @BotFather
2. Gõ: `/newbot`
3. Đặt tên hiển thị: `[Tên Shop] Orders`
4. Đặt username: `ten_shop_orders_bot`
5. **Lưu token nhận được** (dạng: `123456789:ABCdef...`)

### Bước 2: Lấy Chat ID
1. Tạo group Telegram tên `[Shop] Đơn Hàng`
2. Add bot vào group
3. Gửi 1 tin nhắn bất kỳ trong group
4. Mở link: `https://api.telegram.org/bot{TOKEN}/getUpdates`
5. Tìm `"chat":{"id": -XXXXXXXXXX}` → Đây là Chat ID

### Bước 3: Test Bot
```
/kit-notify test
```

### Bước 4: Cài Webhook Pipeline
```
/kit-notify webhook
```
→ Nhận code Node.js, configure env variables, deploy.

---

## 8. Deploy Lên Vercel

### Cách Nhanh Nhất (CLI)

```bash
# 1. Vào thư mục landing page
cd my-landing-page

# 2. Đăng nhập (1 lần)
vercel login

# 3. Deploy production
vercel --prod

# Nhận URL: https://my-landing-page.vercel.app
```

### Cấu Trúc Thư Mục Cần Có
```
my-landing-page/
├── index.html    ← PHẢI đặt tên này
├── assets/       ← Ảnh, CSS, JS (nếu có)
└── vercel.json   ← Cấu hình (tùy chọn)
```

### Sau Khi Deploy
1. Mở URL trên điện thoại
2. Test QR payment
3. Test tất cả links và buttons
4. Check load speed (< 3 giây)
5. Xác nhận SSL (ổ khóa xanh)

---

## 9. FAQ & Troubleshoot

### Câu Hỏi Thường Gặp

**Q: Tôi cần biết code không?**  
A: Không cần biết code để viết copy và build landing page. Cần biết cơ bản về terminal/command line để deploy và cài backend.

**Q: SePay miễn phí không?**  
A: Không phí merchant cho chuyển khoản ngân hàng. Chỉ phí khi dùng tính năng nâng cao. Xem pricing tại my.sepay.vn.

**Q: Vercel miễn phí đến bao giờ?**  
A: Gói free không giới hạn thời gian, bao gồm 100GB bandwidth/tháng — đủ cho hầu hết landing pages.

**Q: Tôi có thể dùng kit này cho nhiều sản phẩm không?**  
A: Có, mỗi lần gõ lệnh có thể tạo cho sản phẩm khác nhau.

**Q: Landing page có hỗ trợ tiếng Việt không?**  
A: Có, kit mặc định tạo nội dung tiếng Việt với `lang="vi"` và font Vietnamese-friendly.

---

### Troubleshoot Phổ Biến

**Lỗi: QR không hiển thị**
```
Kiểm tra:
1. Tên ngân hàng đúng format (Vietcombank không phải VCB)
2. Số TK đúng
3. Amount là số nguyên (1997000 không phải 1.997.000)
```

**Lỗi: 404 khi deploy Vercel**
```
Fix: File chính phải tên chính xác là index.html
Kiểm tra: ls → phải thấy index.html (không phải Index.html)
```

**Lỗi: Webhook không nhận được**
```
Kiểm tra:
1. Server đang chạy với HTTPS (không phải HTTP)
2. URL webhook đã config trong SePay dashboard
3. Xem logs: vercel logs
```

**Lỗi: Telegram không nhận thông báo**
```
Kiểm tra:
1. Bot đã được add vào group
2. Chat ID là của group (âm: -XXXXXXXX)
3. Bot token đúng
4. Test bằng: /kit-notify test
```

**Lỗi: Ảnh không load sau deploy**
```
Fix: Dùng relative paths
Sai: /Users/admin/project/image.jpg
Đúng: ./assets/images/image.jpg
```

---

## Hỗ Trợ

Nếu gặp vấn đề không có trong guide này:

1. **Hỏi Claude trực tiếp:** Mô tả vấn đề trong Claude Code session
2. **Dùng lệnh review:** `/kit-sales-page review [nội dung gặp vấn đề]`
3. **Xem reference files:** Vào `skills/{skill}/references/` để đọc tài liệu chi tiết

---

*AI Landing Engine Kit | Hướng Dẫn Sử Dụng | by 10xSystem*  
*Phiên bản 1.0 — Cập nhật 2025*
