---
description: Deploy landing page lên Vercel — nhận URL live trong 60 giây
argument-hint: [vercel|cli|git|drag|domain]
---

Anh/chị đang yêu cầu deploy landing page lên internet.

<args>$ARGUMENTS</args>

## Thực Thi

Đọc và áp dụng theo thứ tự:
1. Load `agents/02-deliver-agent.md` — System prompt Deliver Agent
2. Load `skills/vercel-deployment/SKILL.md` — Vercel deployment skill
3. Load `skills/vercel-deployment/templates/vercel-config.json` — Config template

## Actions

- **vercel** / **cli** → Deploy qua Vercel CLI: `vercel --prod` (khuyến nghị)
- **git** → Cài auto-deploy từ GitHub repo (push = tự deploy)
- **drag** → Kéo thả folder vào dashboard (không cần terminal)
- **domain** → Hướng dẫn gắn tên miền + DNS records + SSL

## Yêu Cầu Output

- Hướng dẫn từng bước theo phương thức được chọn
- Lệnh cụ thể để chạy (copy-paste được)
- Checklist pre-deployment và post-deployment
- Troubleshooting lỗi phổ biến (404, Build Failed, DNS)

## Checklist Bắt Buộc Trước Deploy

```
✅ File tên index.html (chính xác, không phải Index.html)
✅ Đường dẫn file dùng relative paths (./assets/...)
✅ Tên file viết thường, dùng gạch nối
✅ Ảnh đã nén (< 500KB mỗi file)
✅ Không URL localhost trong code
✅ Script ngoài dùng HTTPS
✅ Meta title + description + og:image đầy đủ
```

## Lệnh Nhanh

```bash
vercel login    # Đăng nhập (lần đầu)
vercel          # Deploy preview
vercel --prod   # Deploy production
vercel logs     # Xem logs khi lỗi
```
