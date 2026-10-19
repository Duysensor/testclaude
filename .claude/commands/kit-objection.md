---
description: Xây hệ thống phản hồi và xử lý từ chối của khách hàng
argument-hint: [price|trust|timing|need|scam|authority] [context]
---

Anh/chị đang yêu cầu xây dựng hệ thống xử lý từ chối.

<args>$ARGUMENTS</args>

## Thực Thi

Đọc và áp dụng theo thứ tự:
1. Load `agents/01-conversion-agent.md` — System prompt Conversion Agent
2. Load `skills/objection-handler/SKILL.md` — Objection handler skill
3. Load `skills/objection-handler/references/objection-classification-framework.md`
4. Load `skills/objection-handler/references/objection-response-library.md`

## Yêu Cầu Output

Cho mỗi từ chối được xử lý:
1. **Loại từ chối** — Phân loại chính xác
2. **Nỗi sợ gốc rễ** — Điều thực sự đằng sau từ chối bề mặt
3. **Framework phản hồi** — Acknowledge → Reframe → Resolve → Redirect
4. **Script phản hồi hoàn chỉnh** — Tiếng Việt, giọng điệu tự nhiên
5. **Proof points** — Testimonial, data, guarantee cần đưa vào
6. **Copy preemptive** — Đoạn copy để nhúng vào trang trước khi từ chối xuất hiện

## Phân Loại Từ Chối VN

| Loại | Biểu Hiện | Nỗi Sợ Thực |
|------|-----------|-------------|
| `scam` | "Có phải lừa đảo không?" | Sợ mất tiền oan |
| `price` | "Đắt quá", "Không có tiền" | Không chắc về giá trị |
| `trust` | "Không biết anh/chị là ai" | Sợ thất vọng |
| `timing` | "Để sau", "Chưa phải lúc" | Trì hoãn, ưu tiên khác |
| `need` | "Mình không cần" | Không thấy liên quan |
| `authority` | "Để hỏi vợ/chồng/sếp" | Sợ quyết định sai |

Nếu cung cấp từ chối tùy chỉnh → Phân loại vào category phù hợp và tạo phản hồi.
