---
description: Tạo blueprint trang bán hàng hoàn chỉnh theo 14-section framework
argument-hint: [full|outline|review|hero|faq] [tên sản phẩm hoặc URL]
---

Anh/chị đang yêu cầu xây dựng trang bán hàng chuyển đổi cao.

<args>$ARGUMENTS</args>

## Thực Thi

Đọc và áp dụng theo thứ tự:
1. Load `agents/01-conversion-agent.md` — System prompt Conversion Agent
2. Load `skills/sales-page-blueprint/SKILL.md` — Blueprint skill
3. Load `skills/sales-page-blueprint/references/sales-page-section-by-section-guide.md`
4. Load `skills/sales-page-blueprint/references/conversion-elements-library.md`
5. Load `skills/sales-page-blueprint/templates/sales-page-copy-template.md`
6. (Nếu cần copy) Load `skills/copywriting/SKILL.md`
7. (Nếu cần FAQ) Load `skills/objection-handler/SKILL.md`

## Actions

- **Không có action** hoặc **full** → Tạo trang bán hàng đầy đủ 14 sections
- **outline** → Chỉ tạo cấu trúc wireframe và headline cho từng section
- **review** → Review và đề xuất cải thiện trang/copy hiện có
- **hero** → Chỉ viết hero section: pre-headline + headline + subheadline + CTA
- **faq** → Chỉ xây dựng FAQ section xử lý 8–12 từ chối phổ biến

## Yêu Cầu Output

Cho mỗi section được tạo:
- Copy hoàn chỉnh (tiếng Việt)
- Lý giải chiến lược (tại sao cấu trúc này)
- Ghi chú mobile (đặc biệt với CTA và form)
- Gợi ý A/B test

## Framework 14 Sections

```
1. Pre-headline  5. Solution      9. Offer Stack   13. FAQ
2. Headline      6. Benefits     10. Guarantee     14. Final CTA
3. Subheadline   7. How it works 11. Price
4. Problem       8. Proof        12. Urgency
```

Nhắc nhở: Mọi trang đều cần section SePay VietQR payment tích hợp cho thị trường Việt Nam.
