# AI Landing Engine Kit — by 10xSystem

> **Core Hook:** Biến ý tưởng thành hệ thống bán hàng hoàn chỉnh chỉ trong 1 lần bấm.

Bộ kit chuyên biệt giúp solopreneur và SME Việt Nam xây dựng **trang landing page chuyển đổi cao + hệ thống thanh toán & giao hàng tự động** — từ copy đến code, từ ý tưởng đến doanh thu thực.

---

## Kiến trúc Kit: 2 Agents — 9 Skills — 9 Commands

```
Ý tưởng sản phẩm
       │
       ▼
┌─────────────────────────────────────────┐
│  CONVERSION AGENT                       │
│  Viết copy → Xây trang → Xử lý từ chối │
│  /kit-copy  /kit-sales-page  /kit-objection │
│  /kit-landing-page                      │
└─────────────┬───────────────────────────┘
              │ Landing page sẵn sàng
              ▼
┌─────────────────────────────────────────┐
│  DELIVER AGENT                          │
│  Kết nối thanh toán → Giao hàng tự động │
│  /kit-payment-setup  /kit-notify        │
│  /kit-deliver  /kit-deploy  /kit-qr     │
└─────────────┬───────────────────────────┘
              │
              ▼
       Hệ thống bán hàng
       hoàn chỉnh ✅
```

---

## Cách Kit Hoạt Động

Khi người dùng gõ `/kit-command [tham số]`:
1. Đọc file lệnh trong `commands/kit-{command}.md`
2. Kích hoạt Agent tương ứng từ `agents/`
3. Tải Skill cần thiết: `skills/{skill}/SKILL.md` + `references/` + `templates/`
4. Thực thi theo workflow nếu cần từ `workflows/`
5. Xuất output theo định dạng đã chỉ định

---

## Agents

| Agent | File | Skills |
|-------|------|--------|
| **Conversion Agent** | `agents/01-conversion-agent.md` | copywriting, sales-page-blueprint, objection-handler, landing-page-builder |
| **Deliver Agent** | `agents/02-deliver-agent.md` | payment-setup-guide, notification-setup-guide, delivery-setup-guide, vercel-deployment, payment-embed |

---

## Commands (9 Lệnh)

### Conversion Agent — Viết copy & xây trang
| Lệnh | Mô tả |
|------|-------|
| `/kit-copy [framework] [chủ đề]` | Viết copy thuyết phục theo công thức |
| `/kit-sales-page [action] [sản phẩm]` | Tạo blueprint trang bán hàng hoàn chỉnh |
| `/kit-objection [loại] [sản phẩm]` | Xử lý từ chối của khách hàng |
| `/kit-landing-page [loại] [phong cách]` | Build trang HTML sẵn sàng deploy |

### Deliver Agent — Thanh toán & giao hàng
| Lệnh | Mô tả |
|------|-------|
| `/kit-payment-setup [bước]` | Cài đặt thanh toán SePay VietQR |
| `/kit-notify [bước]` | Cài Telegram bot nhận thông báo đơn hàng |
| `/kit-deliver [phương thức]` | Tự động hóa giao sản phẩm số |
| `/kit-deploy [phương thức]` | Deploy landing page lên Vercel |
| `/kit-qr [kiểu nhúng]` | Nhúng mã QR thanh toán vào trang |

---

## Skills

Mỗi skill nằm trong `skills/{skill-name}/` gồm:
- `SKILL.md` — Hướng dẫn chính, phương pháp luận
- `references/` — Frameworks, tài liệu tham khảo
- `templates/` — Mẫu sẵn dùng (điền vào là chạy)

| Skill | Dùng khi nào |
|-------|-------------|
| `copywriting` | Viết copy bán hàng theo công thức |
| `sales-page-blueprint` | Thiết kế cấu trúc trang bán hàng |
| `objection-handler` | Xây hệ thống xử lý từ chối |
| `landing-page-builder` | Tạo trang HTML + Tailwind CSS |
| `payment-setup-guide` | Tích hợp SePay VietQR |
| `notification-setup-guide` | Cài Telegram bot thông báo |
| `delivery-setup-guide` | Tự động giao sản phẩm số |
| `vercel-deployment` | Deploy lên Vercel miễn phí |
| `payment-embed` | Nhúng QR thanh toán vào trang |

---

## Workflows

| Workflow | File | Thời gian |
|----------|------|-----------|
| Xây trang chuyển đổi | `workflows/conversion-sales-workflow.md` | 2–3 giờ |
| Tự động hóa giao hàng | `workflows/delivery-automation-workflow.md` | 1–2 giờ |

---

## Quy tắc Vận Hành

- Xưng hô với người dùng là **"anh/chị"** (lịch sự kinh doanh Việt Nam)
- Nội dung output bằng **tiếng Việt** trừ khi được yêu cầu khác
- Dùng ví dụ thực tế Việt Nam: giá VNĐ, thanh toán ngân hàng, thị trường Việt
- Tech stack chuẩn: SePay (thanh toán), Telegram (thông báo), Vercel (deploy), Tailwind CSS (giao diện)
- Khi câu hỏi không rõ ràng → map sang lệnh gần nhất và xác nhận trước khi thực thi

## Thực Thi Lệnh — Chi Tiết

Khi người dùng gõ slash command:

1. **Đọc** file lệnh: `commands/kit-{command}.md`
2. **Tải** system prompt của agent: `agents/{agent-file}.md`
3. **Đọc** file skill: `skills/{skill-name}/SKILL.md`
4. **Đọc** references: `skills/{skill-name}/references/`
5. **Dùng** templates nếu có: `skills/{skill-name}/templates/`
6. **Theo** workflow nếu cần: `workflows/{workflow-file}.md`
7. **Xuất** output theo format đã chỉ định

Nếu người dùng không gõ slash command → suy luận ý định và đề xuất lệnh phù hợp.

---

*AI Landing Engine Kit — by 10xSystem | Phiên bản 1.0*
