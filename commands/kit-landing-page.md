---
description: Build trang HTML landing page hoàn chỉnh, sẵn sàng deploy
argument-hint: [loại sản phẩm] [phong cách]
---

Tạo trang landing page HTML đầy đủ với Tailwind CSS — mobile-first, tích hợp thanh toán Việt Nam.

<args>$ARGUMENTS</args>

## Loại Sản Phẩm / Dịch Vụ

- `service` — Dịch vụ, tư vấn, freelance, agency
- `course` — Khóa học online, đào tạo, workshop
- `saas` — Phần mềm, tool, ứng dụng SaaS
- `ecommerce` — Sản phẩm vật lý hoặc số
- `lead-magnet` — Thu email, tặng tài liệu miễn phí
- `event` — Webinar, hội thảo, sự kiện đăng ký

## Phong Cách Thiết Kế

- `minimal` — Tối giản, đơn cột, dễ đọc
- `bold` — Tương phản cao, statement mạnh
- `elegant` — Font serif, cảm giác sang trọng
- `tech` — Modern, startup aesthetic
- `warm` — Thân thiện, gần gũi, vibe Việt Nam

## Quy Trình

1. Kích hoạt Conversion Agent
2. Dùng skill Landing Page Builder
3. Chọn design system từ `references/design-data.md` (màu sắc, font, pattern)
4. Generate HTML hoàn chỉnh với Tailwind CSS
5. Output: File HTML đơn, sẵn sàng deploy

## Ví Dụ

- `/kit-landing-page course bold` — Trang bán khóa học bold với testimonials và QR thanh toán
- `/kit-landing-page service minimal` — Trang dịch vụ tối giản: hero, features, pricing, FAQ
- `/kit-landing-page saas tech` — Trang SaaS modern với demo section và pricing tiers
- `/kit-landing-page lead-magnet warm` — Trang thu email với vibe thân thiện, Việt Nam
- `/kit-landing-page event elegant` — Trang đăng ký webinar sang trọng với countdown

## Mẹo Tối Ưu

- Bắt đầu từ templates trong `skills/landing-page-builder/templates/` rồi customize
- Luôn tích hợp section thanh toán SePay QR cho thị trường Việt Nam
- Deploy ngay sau khi build bằng `/kit-deploy vercel`
- Test trên mobile trước — 70%+ người dùng Việt đọc trên điện thoại

## Tính Năng Nổi Bật

```
✅ Single-file HTML (không cần build step)
✅ Tailwind CSS CDN (zero dependencies)
✅ Mobile-first responsive
✅ 10 template designs sẵn có
✅ Tích hợp SePay VietQR payment section
✅ SEO meta tags đầy đủ
✅ Open Graph cho social sharing
✅ Google Fonts (Vietnamese-friendly)
✅ Scroll-triggered CTAs
✅ FAQ section với accordion
```
