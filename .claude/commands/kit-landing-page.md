---
description: Build landing page HTML hoàn chỉnh với Tailwind CSS — mobile-first, ready to deploy
argument-hint: [service|course|saas|ecommerce|lead-magnet|event] [minimal|bold|elegant|tech|warm]
---

Anh/chị đang yêu cầu build landing page HTML hoàn chỉnh.

<args>$ARGUMENTS</args>

## Thực Thi

Đọc và áp dụng theo thứ tự:
1. Load `agents/01-conversion-agent.md` — System prompt Conversion Agent
2. Load `skills/landing-page-builder/SKILL.md` — Landing page builder skill
3. Load `skills/landing-page-builder/references/design-data.md` — Color palettes + font pairings
4. Chọn template phù hợp từ `skills/landing-page-builder/templates/`
5. (Nếu cần copy) Load `skills/copywriting/SKILL.md`
6. (Nếu cần payment embed) Load `skills/payment-embed/SKILL.md`

## Quy Trình Build

1. **Xác định loại sản phẩm** — từ args hoặc hỏi user
2. **Chọn color palette** — từ design-data.md theo product type
3. **Chọn font pairing** — Vietnamese-friendly hoặc theo brand mood
4. **Chọn layout pattern** — từ 10 patterns có sẵn
5. **Generate HTML** — đầy đủ từ `<!DOCTYPE>` đến `</html>`
6. **Tích hợp QR payment** — SePay VietQR section bắt buộc

## Yêu Cầu Output

File HTML duy nhất, hoàn chỉnh gồm:
- Tailwind CSS via CDN (không cần build step)
- Google Fonts (Vietnamese-friendly)
- Responsive mobile-first
- SEO meta tags + Open Graph
- SePay VietQR payment section
- FAQ accordion section
- Smooth scroll + sticky header
- Tất cả placeholder rõ ràng để anh/chị thay thế

## Ghi Chú Quan Trọng

- **KHÔNG** tạo file giả — chỉ xuất HTML thực sự hoạt động
- **LUÔN** bao gồm section thanh toán SePay cho thị trường Việt Nam
- **LUÔN** test trên mobile viewport (375px) trước khi xuất
- **ƯU TIÊN** conversion: mọi element phải phục vụ CTA
