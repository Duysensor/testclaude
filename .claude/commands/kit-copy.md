---
description: Viết copy thuyết phục — chọn công thức, nhận copy hoàn chỉnh ngay
argument-hint: [par|arc|cascade|pven|fep|story] [chủ đề]
---

Anh/chị đang yêu cầu viết copy theo công thức thuyết phục.

<args>$ARGUMENTS</args>

## Thực Thi

Đọc và áp dụng theo thứ tự:
1. Load `agents/01-conversion-agent.md` — System prompt của Conversion Agent
2. Load `skills/copywriting/SKILL.md` — Skill high-impact-copy
3. Load `skills/copywriting/references/persuasion-formulas-library.md`
4. Load `skills/copywriting/references/power-words-and-emotional-triggers.md`
5. Load `skills/copywriting/references/headline-and-hook-patterns.md`

## Yêu Cầu Output

Dựa vào công thức được chọn (hoặc đề xuất công thức phù hợp nhất), tạo:

1. **Phiên bản chính** — Copy hoàn chỉnh theo công thức, có lý giải chiến lược
2. **2–3 biến thể** — Thử nghiệm hooks khác nhau (tò mò / nỗi đau / ham muốn)
3. **Ghi chú triển khai** — Nền tảng phù hợp, A/B test suggestion
4. **Bản đồ từ chối** — Các từ chối tiềm ẩn và cách phản hồi

## Công Thức

| Code | Tên | Dùng khi |
|------|-----|----------|
| `par` | Problem-Amplify-Resolve | Khách biết mình có vấn đề |
| `arc` | Transformation Arc | Cần before/after, testimonial |
| `cascade` | Attention Cascade | Traffic lạnh, chưa nhận thức |
| `pven` | Promise-Vision-Evidence-Nudge | Offer cao cấp, cần trust cao |
| `fep` | Feature-Edge-Payoff | Mô tả sản phẩm, feature announcement |
| `story` | Storytelling Arc | Brand narrative, emotional connection |

Nếu không chỉ định công thức → phân tích context và chọn công thức phù hợp nhất, giải thích lý do.
