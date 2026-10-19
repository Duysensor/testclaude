---
description: Deploy landing page lên Vercel và nhận URL live
argument-hint: [phương thức]
---

Đưa landing page của anh/chị lên internet trong vài phút.

<args>$ARGUMENTS</args>

## Phương Thức Deploy

- `vercel` / `cli` — Deploy qua Vercel CLI (khuyến nghị, nhanh nhất)
- `git` — Auto-deploy từ GitHub (mỗi lần push → tự động cập nhật)
- `drag` — Kéo thả folder vào Vercel dashboard (không cần code)
- `domain` — Hướng dẫn gắn tên miền tùy chỉnh

## Quy Trình

1. Kích hoạt Deliver Agent
2. Dùng skill Vercel Deployment
3. Hướng dẫn từng bước deploy
4. Output: URL live + hướng dẫn cài tên miền tùy chỉnh

## Ví Dụ

- `/kit-deploy vercel` — Deploy ngay qua CLI, nhận URL live trong 60 giây
- `/kit-deploy git` — Cài auto-deploy từ GitHub (push code = site tự cập nhật)
- `/kit-deploy drag` — Kéo thả folder vào Vercel dashboard, không cần gõ lệnh
- `/kit-deploy domain` — Gắn tên miền riêng với DNS records đầy đủ

## Mẹo Vận Hành

- Cài Node.js trước khi dùng Vercel CLI (tải tại nodejs.org)
- Gói free Vercel đủ dùng cho hầu hết landing pages (100GB bandwidth/tháng)
- Dùng `/kit-landing-page` để build trang trước, sau đó `/kit-deploy` để publish
- Kiểm tra file `index.html` đặt đúng thư mục gốc — Vercel tìm đúng tên này

## Lệnh Vercel Nhanh

```bash
# Đăng nhập (một lần duy nhất)
vercel login

# Deploy bản preview để test
vercel

# Deploy production (URL chính thức)
vercel --prod

# Xem logs khi có lỗi
vercel logs

# Xem danh sách deployments
vercel list
```

## Checklist Trước Khi Deploy

```
✅ File chính đặt tên là index.html
✅ Tất cả đường dẫn file dùng relative paths
✅ Tên file viết thường, dùng gạch nối
✅ Ảnh đã nén (< 500KB mỗi file)
✅ Không có URL localhost hardcoded
✅ Script bên ngoài dùng HTTPS
✅ Meta tags đầy đủ (title, description, og:image)
```
