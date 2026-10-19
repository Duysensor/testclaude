---
name: vercel-deployment
description: Deploy landing page HTML lên Vercel — nhận URL live trong 60 giây, miễn phí, tự động SSL
version: 2.0.0
kit: AI Landing Engine Kit by 10xSystem
---

# Vercel Deployment Skill

## Kích Hoạt Skill Này Khi

- Deploy HTML landing page lên production
- Nhận URL live cho khách hàng test
- Gắn custom domain vào website
- Cài auto-deployment từ Git repository
- Cần SSL certificate tự động
- Deploy static site không cần backend phức tạp

---

## Tổng Quan

**Mục đích:** Deploy HTML landing page lên Vercel với một lệnh  
**Đối tượng:** Solopreneur/SME không chuyên kỹ thuật  
**Kết quả:** Website live trên `.vercel.app` hoặc tên miền riêng  
**Chi phí:** Gói free đủ dùng cho hầu hết landing pages  

---

## Yêu Cầu Trước Khi Deploy

### Phần Mềm Cần Cài
- **Node.js** (bắt buộc cho Vercel CLI)
  - Tải tại: nodejs.org/en/download
  - Windows: Download và chạy file cài `.msi`
  - Kiểm tra: `node --version` (phải hiện v18+ hoặc v20+)

- **Vercel CLI**
  - Cài: `npm install -g vercel`
  - Kiểm tra: `vercel --version`

### Tài Khoản
- **Vercel Account:** Đăng ký tại vercel.com/signup
  - Gói free bao gồm:
    - Unlimited deployments
    - SSL certificates tự động
    - 100GB bandwidth/tháng
    - Custom domain support

---

## 3 Phương Thức Deploy

### Phương Thức 1: Vercel CLI (Khuyến Nghị)
**Tốt nhất cho:** Deploy nhanh, test, phát triển iterative

```bash
# Bước 1: Mở terminal trong folder project
cd path/to/your/landing-page

# Bước 2: Đăng nhập Vercel (chỉ cần làm 1 lần)
vercel login
# → Mở browser để xác thực

# Bước 3: Deploy lên production
vercel --prod
# → Nhận URL live ngay lập tức
```

**Output mẫu:**
```
✅ Production: https://your-landing-page.vercel.app [3s]
```

**Câu hỏi lần deploy đầu:**
```
Set up and deploy? → Yes
Which scope? → Your Account
Link to existing project? → No
Project name? → your-landing-page
Directory? → ./
Framework? → Other (cho HTML thuần)
Override settings? → No
```

### Phương Thức 2: Git Auto-Deploy
**Tốt nhất cho:** Team, workflow tự động, production sites

```bash
# Push code lên GitHub
git init
git add .
git commit -m "Initial landing page"
git remote add origin https://github.com/username/repo.git
git push -u origin main

# Kết nối với Vercel Dashboard
# → vercel.com/new → Import Git Repository
# → Chọn repo → Deploy
```

**Tính năng Auto-Deploy:**
- Push lên `main` → Tự deploy production
- Push lên branch khác → Preview deploy với URL riêng
- Pull request → Preview URL unique

### Phương Thức 3: Drag & Drop
**Tốt nhất cho:** Người không quen terminal, test nhanh

1. Vào vercel.com/new
2. Kéo thả folder project vào upload area
3. Đợi upload xong
4. Click "Deploy"
5. Nhận URL live

**Hạn chế:** Phải upload lại thủ công mỗi khi thay đổi

---

## Cấu Trúc Project Chuẩn

```
landing-page/
├── index.html           ← Trang chính (BẮT BUỘC đặt tên này)
├── thank-you.html       ← Trang sau mua (tùy chọn)
├── privacy-policy.html  ← Chính sách bảo mật (tùy chọn)
├── assets/
│   ├── images/
│   │   ├── hero-image.jpg
│   │   └── product-photo.png
│   ├── css/
│   │   └── styles.css
│   └── js/
│       └── main.js
└── vercel.json          ← Cấu hình (tùy chọn)
```

**Quy tắc đặt tên file:**
- File chính PHẢI là `index.html` (không phải `Index.html` hay `home.html`)
- Viết thường, dùng gạch nối: `thank-you.html`
- Không dấu cách hay ký tự đặc biệt

---

## vercel.json — Cấu Hình Nâng Cao

```json
{
  "headers": [
    {
      "source": "/(.*)",
      "headers": [
        { "key": "X-Content-Type-Options", "value": "nosniff" },
        { "key": "X-Frame-Options", "value": "DENY" },
        { "key": "X-XSS-Protection", "value": "1; mode=block" }
      ]
    }
  ],
  "redirects": [
    {
      "source": "/mua-ngay",
      "destination": "/#payment",
      "permanent": false
    }
  ]
}
```

Xem `templates/vercel-config.json` để dùng config đầy đủ.

---

## Gắn Custom Domain

```
Bước 1: Dashboard → Chọn project → Settings → Domains
Bước 2: Nhập tên miền → Add
Bước 3: Cài DNS records tại nhà cung cấp tên miền:
         A record:     @ → 76.76.21.21
         CNAME record: www → cname.vercel-dns.com
Bước 4: Đợi DNS propagate (5 phút → 48 giờ)
Bước 5: SSL certificate tự động issued
```

---

## Troubleshoot Lỗi Phổ Biến

| Lỗi | Nguyên Nhân | Cách Fix |
|-----|-------------|---------|
| 404 Not Found | File không tên `index.html` | Đổi tên file chính thành `index.html` |
| Build Failed | Cấu hình build sai | Xóa Build Command, Output Dir đặt `.` |
| Images Not Loading | Đường dẫn tuyệt đối | Đổi sang relative path: `./assets/img.jpg` |
| DNS Not Working | DNS chưa propagate | Đợi tối đa 48h, kiểm tra tại dnschecker.org |

---

## Checklist Pre-Deploy

```
✅ File chính đặt tên index.html
✅ Tất cả đường dẫn dùng relative URLs
✅ Tên file viết thường, dùng gạch nối
✅ Ảnh đã nén (< 500KB mỗi file)
✅ Không URL localhost trong code
✅ Script ngoài dùng HTTPS
✅ Meta tags: title, description, og:image
```

## Lệnh Nhanh

```bash
vercel login      # Đăng nhập (1 lần)
vercel            # Deploy preview
vercel --prod     # Deploy production
vercel list       # Danh sách deployments
vercel logs       # Xem logs khi lỗi
vercel --version  # Kiểm tra version CLI
```

*AI Landing Engine Kit | Skill: Vercel Deployment | by 10xSystem*
