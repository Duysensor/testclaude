---
description: Nhúng mã QR thanh toán SePay VietQR vào landing page — copy-paste ready
argument-hint: [qr|pricing|modal|dynamic|multi]
---

Anh/chị đang yêu cầu tạo code nhúng QR thanh toán SePay VietQR.

<args>$ARGUMENTS</args>

## Thực Thi

Đọc và áp dụng theo thứ tự:
1. Load `agents/02-deliver-agent.md` — System prompt Deliver Agent
2. Load `skills/payment-embed/SKILL.md` — Payment embed skill
3. Load `skills/payment-embed/references/sepay-embed-guide.md`

## Kiểu Nhúng

- **qr** → Section QR đơn giản + thông tin ngân hàng (dễ nhất, phù hợp mọi trang)
- **pricing** → 3 pricing cards với QR riêng cho từng gói (chuyên nghiệp)
- **modal** → QR popup khi click "Mua ngay" (UX tốt nhất, không làm lộn trang)
- **dynamic** → JavaScript generate QR theo sản phẩm/gói khách chọn
- **multi** → Nhiều sản phẩm, mỗi cái QR riêng (catalog-style)

## Yêu Cầu Output

- HTML/JavaScript hoàn chỉnh, sẵn sàng copy-paste
- Placeholder rõ ràng: `YOUR_ACCOUNT`, `YOUR_BANK`, `YOUR_AMOUNT`
- Hướng dẫn thay thế placeholder
- Ghi chú cách test QR với app ngân hàng

## Format URL QR SePay

```
https://qr.sepay.vn/img?acc={TÀI_KHOẢN}&bank={NGÂN_HÀNG}&amount={SỐ_TIỀN}&des={NỘI_DUNG}
```

**Lưu ý:**
- Amount là số nguyên VNĐ (1997000, không phải 1,997,000)
- Description ngắn gọn, không dấu cách, dưới 50 ký tự
- Dùng gạch dưới thay khoảng trắng: `KIT_LANDING_001`

## Ngân Hàng Phổ Biến

`Vietcombank` · `VPBank` · `BIDV` · `Techcombank` · `ACB` · `MBBank` · `Sacombank` · `VietinBank` · `TPBank`

Danh sách đầy đủ: `https://qr.sepay.vn/banks.json`
