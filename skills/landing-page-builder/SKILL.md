---
name: landing-page-builder
description: Tạo landing page HTML hoàn chỉnh với Tailwind CSS — mobile-first, conversion-focused, tích hợp thanh toán SePay VietQR cho thị trường Việt Nam
version: 2.0.0
kit: AI Landing Engine Kit by 10xSystem
---

# Landing Page Builder Skill

## Tổng Quan

**Mục đích:** Tạo landing page HTML đơn file, hoàn chỉnh với Tailwind CSS — chuyển đổi cao cho solopreneur và SME Việt Nam.

**Output:** File HTML duy nhất, nhúng Tailwind CSS via CDN, responsive mobile-first, sẵn sàng production.

**Triết lý:**
- Tốc độ hơn hoàn hảo (launch trong giờ, không phải tuần)
- Conversion-focused (mọi element phục vụ CTA)
- Vietnamese market context (thanh toán local, văn hóa tiêu dùng VN)
- Zero dependencies (chạy offline sau lần tải đầu)

---

## Workflow Chọn Design System

Khi build landing page, theo thứ tự sau:

### Bước 1: Xác Định Loại Sản Phẩm
Hỏi user hoặc suy luận từ context:
- Dịch vụ (tư vấn, freelance, agency)
- Khóa học/đào tạo online
- Làm đẹp/spa/wellness
- Nhà hàng/giao đồ ăn
- Healthcare/y tế
- SaaS/phần mềm
- E-commerce/bán lẻ
- Bất động sản
- Fitness/gym
- Du lịch/tourism
- Fintech/tài chính
- Pháp lý
- Tổ chức sự kiện
- Hàng hóa cao cấp
- AI/tech products

### Bước 2: Chọn Màu Sắc
Tham chiếu `references/design-data.md` cho color scheme phù hợp. Mỗi palette gồm:
- Primary (brand color)
- Secondary (màu hỗ trợ)
- CTA (màu nút call-to-action)
- Background (màu nền)
- Text (màu chữ thân)

### Bước 3: Chọn Font
Chọn font theo brand mood từ `references/design-data.md`:
- **Vietnamese Friendly:** Be Vietnam Pro + Noto Sans
- **Modern Professional:** Poppins + Open Sans
- **Classic Elegant:** Playfair Display + Inter
- **Tech Startup:** Space Grotesk + DM Sans
- **Wellness Calm:** Lora + Raleway

### Bước 4: Chọn Layout Pattern
Từ 10 patterns tối ưu chuyển đổi bên dưới.

---

## 10 Patterns Landing Page

| Pattern | Sections | Vị Trí CTA | Tốt Nhất Cho | Conversion Focus |
|---------|----------|------------|-------------|-----------------|
| Hero + Features + CTA | Hero, 3–6 Features, CTA | Above fold + bottom | Dịch vụ, SaaS | Feature-benefit clarity |
| Hero + Testimonials + CTA | Hero, Social Proof, CTA | Above fold + after testimonials | Legal, Health | Social validation |
| Product Demo + Features | Video/GIF Demo, Features, CTA | After demo | SaaS, apps | Product visualization |
| Minimal Single Column | Hero, 1 CTA, Footer | Center, above fold | Lead magnets, waitlist | Zero distraction |
| Funnel (3-Step) | Problem → Solution → CTA | Mỗi section | High-ticket services | Guided journey |
| Lead Magnet + Form | Hero, Benefits, Form, CTA | Form above fold | Thu email, free giveaway | List building |
| Pricing Page + CTA | Hero, 3-Tier Pricing, FAQ, CTA | Pricing cards | SaaS, membership | Price transparency |
| Before-After | Problem state, Solution, Results | After transformation | Course, beauty, fitness | Transformation proof |
| Waitlist/Coming Soon | Hero, Countdown, Email Form | Email capture | Pre-launch products | FOMO urgency |
| Video-First Hero | Full-screen video, Overlay CTA | Video overlay | High-production brands | Emotional engagement |

### Hướng Dẫn Chọn Pattern
- **Business mới, chưa có testimonials:** Hero + Features + CTA
- **Dịch vụ với social proof mạnh:** Hero + Testimonials + CTA
- **SaaS có demo:** Product Demo + Features
- **Lead magnet offer:** Lead Magnet + Form
- **Khách hàng nhạy cảm về giá:** Pricing Page + CTA
- **Hứa hẹn biến đổi:** Before-After
- **Pre-launch hype:** Waitlist/Coming Soon

---

## Cấu Trúc HTML Chuẩn

```html
<!DOCTYPE html>
<html lang="vi">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>{{TIÊU_ĐỀ_TRANG}}</title>
  <meta name="description" content="{{MÔ_TẢ_META}}">

  <!-- Open Graph cho chia sẻ mạng xã hội -->
  <meta property="og:title" content="{{OG_TITLE}}">
  <meta property="og:description" content="{{OG_DESCRIPTION}}">
  <meta property="og:image" content="{{OG_IMAGE}}">
  <meta property="og:type" content="website">

  <!-- Tailwind CSS CDN — không cần cài đặt gì thêm -->
  <script src="https://cdn.tailwindcss.com"></script>

  <!-- Google Fonts — chọn font Vietnamese-friendly -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  {{FONT_IMPORT}}

  <!-- Cấu hình Tailwind theme tùy chỉnh -->
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            primary: '{{MÀU_CHÍNH}}',
            secondary: '{{MÀU_PHỤ}}',
            accent: '{{MÀU_NHẤN}}'
          },
          fontFamily: {
            heading: [{{FONT_TIÊU_ĐỀ}}, 'sans-serif'],
            body: [{{FONT_THÂN}}, 'sans-serif']
          }
        }
      }
    }
  </script>

  <style>
    /* Font mặc định cho toàn trang */
    body { font-family: {{FONT_THÂN}}, sans-serif; }
    h1, h2, h3, h4, h5, h6 { font-family: {{FONT_TIÊU_ĐỀ}}, sans-serif; }

    /* Smooth scroll khi click link anchor */
    html { scroll-behavior: smooth; }

    /* Animation fade-in cho các section */
    .fade-in { animation: fadeIn 0.6s ease-in; }
    @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
  </style>
</head>
<body class="bg-gray-50 text-gray-900">
  <!-- Nội dung trang đặt ở đây -->
</body>
</html>
```

---

## Section Templates Quan Trọng

### Section Thanh Toán SePay (Bắt Buộc)
```html
<!-- Section QR Thanh Toán VietQR — bắt buộc cho thị trường Việt Nam -->
<section id="payment" class="py-20 bg-gray-50">
  <div class="container mx-auto px-4 text-center">
    <h2 class="text-3xl font-bold mb-4">Thanh Toán Đơn Giản</h2>
    <p class="text-gray-600 mb-8">Quét mã QR bằng app ngân hàng — 44+ ngân hàng Việt Nam</p>

    <div class="max-w-sm mx-auto bg-white rounded-2xl shadow-lg p-8">
      <!-- QR Code được generate tự động bởi SePay API -->
      <img
        src="https://qr.sepay.vn/img?acc=YOUR_ACCOUNT&bank=YOUR_BANK&amount=YOUR_AMOUNT&des=YOUR_PRODUCT"
        alt="Mã QR thanh toán"
        class="w-64 h-64 mx-auto rounded-lg"
      />

      <!-- Thông tin chuyển khoản thủ công -->
      <div class="mt-6 text-left bg-gray-50 rounded-lg p-4 text-sm">
        <p class="mb-2"><strong>Ngân hàng:</strong> YOUR_BANK</p>
        <p class="mb-2"><strong>Số TK:</strong> YOUR_ACCOUNT</p>
        <p class="mb-2"><strong>Số tiền:</strong> X,XXX,XXX VNĐ</p>
        <p class="mb-2"><strong>Nội dung CK:</strong> YOUR_PRODUCT</p>
      </div>

      <p class="mt-4 text-sm text-gray-500">
        Quét bằng bất kỳ app ngân hàng nào • Xác nhận tức thì
      </p>
    </div>
  </div>
</section>
```

### Sticky CTA Bar (Cải Thiện Mobile)
```html
<!-- Sticky bar xuất hiện khi scroll — tăng conversion mobile -->
<div id="sticky-cta" class="fixed bottom-0 left-0 right-0 bg-primary text-white p-4 shadow-lg transform translate-y-full transition-transform duration-300 z-50">
  <div class="container mx-auto flex items-center justify-between">
    <span class="font-semibold">Còn [X] suất với giá ưu đãi</span>
    <a href="#payment" class="bg-white text-primary px-6 py-2 rounded-full font-bold">Mua Ngay</a>
  </div>
</div>

<script>
  // Hiện sticky bar sau khi scroll 300px
  window.addEventListener('scroll', function() {
    const stickyBar = document.getElementById('sticky-cta');
    if (window.scrollY > 300) {
      stickyBar.classList.remove('translate-y-full');
    } else {
      stickyBar.classList.add('translate-y-full');
    }
  });
</script>
```

---

## Templates Có Sẵn

10 HTML templates đặt trong `templates/`:
1. `landing-page-template.html` — Standard light, phù hợp mọi loại
2. `landing-page-dark-modern.html` — Dark + gradient, tech/SaaS
3. `landing-page-minimal-clean.html` — Minimal + clean serif, tư vấn cao cấp
4. `landing-page-creative-bold.html` — Creative + bold, sáng tạo
5. `landing-page-saas-product.html` — SaaS product-focused
6. `landing-page-ecommerce-product.html` — E-commerce sản phẩm
7. `landing-page-webinar-event.html` — Webinar/event registration
8. `landing-page-portfolio-personal.html` — Portfolio/personal brand
9. `landing-page-restaurant-food.html` — Nhà hàng/food
10. `landing-page-mobile-app.html` — Mobile app landing

---

## Best Practices

### Performance
- Ảnh nén xuống < 500KB trước khi embed
- Lazy load ảnh below the fold: `loading="lazy"`
- Dùng WebP format nếu có thể
- Minimize inline JavaScript

### Mobile-First
- Test trên viewport 375px (iPhone SE)
- Button height tối thiểu 44px (thumb-friendly)
- Font size tối thiểu 16px (tránh zoom iOS)
- Khoảng cách giữa các click targets tối thiểu 8px

### Conversion
- CTA button mỗi 3 screens scroll (average reading)
- Màu CTA phải có contrast ratio > 4.5:1
- Countdown timer cho urgency (nếu có)
- Exit-intent popup cho khách sắp rời đi

*AI Landing Engine Kit | Skill: Landing Page Builder | by 10xSystem*
