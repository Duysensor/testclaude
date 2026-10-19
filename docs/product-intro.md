# AI Landing Engine Kit
## Tài Liệu Giới Thiệu Sản Phẩm

**Thương hiệu:** 10xSystem  
**Phiên bản:** 1.0  
**Dành cho:** Solopreneur và SME Việt Nam  

---

## Tuyên Ngôn Sản Phẩm

> **"Biến ý tưởng thành hệ thống bán hàng hoàn chỉnh chỉ trong 1 lần bấm."**

---

## Vấn Đề Chúng Tôi Giải Quyết

Hầu hết solopreneur Việt Nam khi muốn bán sản phẩm số đều gặp phải 3 rào cản lớn:

**Rào cản 1 — Không biết viết copy**  
"Tôi có sản phẩm tốt nhưng không biết cách diễn đạt để khách muốn mua."  
→ Mất hàng tuần loay hoay với text, kết quả vẫn không thuyết phục.

**Rào cản 2 — Không biết build trang**  
"Thuê designer đắt, tự làm mất nhiều ngày, dùng landing page builder lại bị giới hạn."  
→ Trang xong rồi không có QR thanh toán, không biết deploy lên đâu.

**Rào cản 3 — Vận hành thủ công**  
"Mỗi đơn hàng phải tự gửi file, tự check chuyển khoản, không ngủ được vì sợ bỏ lỡ."  
→ Scale không được, mệt mỏi, burnout.

**AI Landing Engine Kit giải quyết cả 3 rào cản này — bằng một bộ lệnh AI thông minh.**

---

## AI Landing Engine Kit Là Gì?

AI Landing Engine Kit là **bộ công cụ AI hoàn chỉnh** chạy trên Claude Code, được thiết kế đặc biệt cho thị trường Việt Nam, giúp solopreneur và SME:

1. **Viết copy bán hàng thuyết phục** — trong 15 phút, không phải 15 ngày
2. **Build landing page chuyển đổi cao** — HTML + Tailwind CSS, mobile-first, sẵn sàng deploy
3. **Tích hợp thanh toán SePay VietQR** — 44+ ngân hàng, không phí merchant
4. **Tự động giao sản phẩm** — Khách thanh toán → Nhận hàng trong 60 giây
5. **Nhận thông báo realtime** — Telegram bot cảnh báo mọi đơn hàng

---

## Ai Nên Dùng Bộ Kit Này?

### Phù Hợp Với
- **Solopreneur** bán sản phẩm số (khóa học, template, ebook, tư vấn)
- **Freelancer** muốn có trang dịch vụ chuyên nghiệp
- **SME nhỏ** cần tự động hóa quy trình bán hàng online
- **Người mới bắt đầu** kinh doanh online, chưa có nền tảng kỹ thuật

### Không Phù Hợp Với
- Doanh nghiệp cần ERP/CRM phức tạp
- Marketplace đa bên (nhiều seller)
- Thanh toán quốc tế / thẻ tín dụng (cần Stripe/PayPal)
- Fulfillment sản phẩm vật lý

---

## Kiến Trúc Hệ Thống

```
AI Landing Engine Kit
│
├── 2 AI Agents Chuyên Biệt
│   ├── Conversion Agent → Viết copy, xây trang, xử lý từ chối
│   └── Deliver Agent   → Kết nối thanh toán, giao hàng, deploy
│
├── 9 Skills (Kiến thức chuyên sâu)
│   ├── Nhóm Conversion: copywriting, sales-page-blueprint, objection-handler, landing-page-builder
│   └── Nhóm Deliver: payment-setup, notification, delivery, vercel-deployment, payment-embed
│
├── 9 Commands (Lệnh slash /kit-*)
│   ├── /kit-copy          → Viết copy theo công thức
│   ├── /kit-sales-page    → Blueprint trang bán hàng
│   ├── /kit-objection     → Xử lý từ chối
│   ├── /kit-landing-page  → Build HTML landing page
│   ├── /kit-payment-setup → Cài SePay VietQR
│   ├── /kit-notify        → Cài Telegram notifications
│   ├── /kit-deliver       → Tự động giao hàng
│   ├── /kit-deploy        → Deploy lên Vercel
│   └── /kit-qr            → Nhúng QR thanh toán
│
├── 2 Workflows (Quy trình end-to-end)
│   ├── Conversion Sales Workflow (2–3 giờ)
│   └── Delivery Automation Workflow (1–2 giờ)
│
└── 10 Landing Page Templates
    ├── Standard, Dark Modern, Minimal Clean
    ├── Creative Bold, SaaS, E-commerce
    ├── Webinar/Event, Portfolio
    ├── Restaurant/Food, Mobile App
```

---

## Hành Trình Từ Ý Tưởng Đến Doanh Thu

```
GIỜ 1: Có Ý Tưởng
   ↓
   Gõ: /kit-sales-page [tên sản phẩm]
   Nhận: Copy trang bán hàng đầy đủ 14 sections
   
GIỜ 2: Có Copy
   ↓
   Gõ: /kit-landing-page course bold
   Nhận: File HTML landing page hoàn chỉnh
   
GIỜ 2.5: Có Trang
   ↓
   Gõ: /kit-qr modal
   Nhận: Code QR thanh toán tích hợp vào trang
   
GIỜ 3: Có Thanh Toán
   ↓
   Gõ: /kit-deploy vercel
   Nhận: URL live https://your-page.vercel.app
   
GIỜ 4: Có Hệ Thống Bán Hàng Hoàn Chỉnh ✅
   ↓
   Gõ: /kit-notify start
   Nhận: Telegram thông báo mỗi đơn hàng
```

---

## Stack Kỹ Thuật Cốt Lõi

| Thành Phần | Công Nghệ | Mục Đích |
|-----------|-----------|---------|
| AI Engine | Claude Code (Anthropic) | Xử lý lệnh, tạo nội dung |
| Frontend | HTML + Tailwind CSS CDN | Landing page, không cần build step |
| Thanh toán | SePay VietQR | 44+ ngân hàng VN, không phí merchant |
| Thông báo | Telegram Bot API | Cảnh báo đơn hàng realtime |
| Backend | Node.js + Express | Webhook handler, delivery |
| Database | SQLite/JSON | Log giao dịch |
| Deploy | Vercel (Free tier) | Hosting landing page |

---

## Điểm Khác Biệt So Với Giải Pháp Khác

| Tiêu Chí | AI Landing Engine Kit | Thuê Freelancer | Dùng Page Builder | Tự Code |
|----------|----------------------|----------------|-------------------|---------|
| Tốc độ | 3–4 giờ | 1–2 tuần | 1–3 ngày | 1–2 tuần |
| Chi phí | Một lần | 5–20 triệu | 500k–2tr/tháng | Thời gian |
| Tùy chỉnh | Cao | Cao | Thấp | Rất cao |
| Thanh toán VN | ✅ Built-in | Tùy designer | ❌ Hạn chế | Tự làm |
| Tự động giao hàng | ✅ Built-in | Phải yêu cầu | ❌ Hạn chế | Tự làm |
| Cần kỹ thuật | Không | Không | Không | Có |

---

## Giá Trị Bộ Kit Mang Lại

**Tiết kiệm thời gian:**
- Copy trang bán hàng: Từ 1 tuần → 15 phút
- Build landing page: Từ 3 ngày → 2 giờ
- Cài thanh toán: Từ 2 ngày → 30 phút
- Cài giao hàng tự động: Từ thủ công → Zero-touch

**Tiết kiệm chi phí:**
- Không thuê copywriter (5–15 triệu/trang)
- Không thuê developer (10–30 triệu)
- Không cần page builder subscription (500k–2tr/tháng)
- Không phí merchant SePay cho chuyển khoản

**Tăng doanh thu:**
- Landing page chuyển đổi cao (structure đã được optimize)
- Hệ thống xử lý từ chối chuyên nghiệp
- Giao hàng tức thì (giảm churn rate)
- Chuỗi tương tác sau mua (tăng LTV)

---

## Được Xây Dựng Cho Thị Trường Việt Nam

**Thanh toán local:** SePay VietQR — 44+ ngân hàng, không phí merchant  
**Copy tiếng Việt:** Framework đã điều chỉnh cho tâm lý người mua VN  
**Xử lý từ chối VN:** Đặc biệt cho "lừa đảo không?" — từ chối số 1 VN market  
**Thông báo tức thì:** Telegram — ứng dụng phổ biến trong cộng đồng kinh doanh VN  
**Mobile-first:** 70%+ người dùng Việt xem trên điện thoại  

---

## Nội Dung Bộ Kit

```
AI Landing Engine Kit/
├── CLAUDE.md                    → Tài liệu hướng dẫn chính
├── agents/                      → 2 AI Agents system prompts
│   ├── 01-conversion-agent.md
│   └── 02-deliver-agent.md
├── commands/                    → 9 lệnh documentation
│   └── kit-*.md
├── .claude/commands/            → 9 slash commands thực tế
│   └── kit-*.md
├── skills/                      → 9 Skills chuyên sâu
│   ├── copywriting/
│   ├── sales-page-blueprint/
│   ├── objection-handler/
│   ├── landing-page-builder/    → 10 HTML templates
│   ├── payment-setup-guide/
│   ├── notification-setup-guide/
│   ├── delivery-setup-guide/
│   ├── vercel-deployment/
│   └── payment-embed/
├── workflows/                   → 2 quy trình end-to-end
│   ├── conversion-sales-workflow.md
│   └── delivery-automation-workflow.md
└── docs/                        → Tài liệu sản phẩm
    ├── product-intro.md          → File này
    └── user-guide.md             → Hướng dẫn sử dụng chi tiết
```

---

## Bắt Đầu Ngay

**Yêu cầu:**
- Claude Code (CLI) đã cài đặt
- Tài khoản Claude Pro hoặc API key
- Kiến thức cơ bản về máy tính

**Khởi động:**
```bash
# Mở Claude Code trong thư mục AI Landing Engine Kit
cd "AI Landing Engine Kit"
claude

# Gõ lệnh đầu tiên
/kit-sales-page [tên sản phẩm của bạn]
```

**Xem hướng dẫn chi tiết:** [user-guide.md](./user-guide.md)

---

*AI Landing Engine Kit — by 10xSystem*  
*Phiên bản 1.0 | Dành cho thị trường Việt Nam*
