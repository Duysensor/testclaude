---
description: Nhúng mã QR thanh toán SePay VietQR vào landing page
argument-hint: [kiểu nhúng]
---

Tích hợp thanh toán VietQR trực tiếp vào trang — khách quét QR, tiền về tài khoản.

<args>$ARGUMENTS</args>

## Kiểu Nhúng

- `qr` — QR code đơn giản + thông tin ngân hàng (dễ nhất)
- `pricing` — Pricing card với QR thanh toán tích hợp (chuyên nghiệp)
- `modal` — Modal popup khi click "Mua ngay" (trải nghiệm tốt nhất)
- `dynamic` — JavaScript generate QR động theo sản phẩm đã chọn
- `multi` — Nhiều sản phẩm với QR riêng biệt cho từng cái

## Quy Trình

1. Kích hoạt Deliver Agent
2. Dùng skill Payment Embed
3. Generate code HTML/JS nhúng QR SePay
4. Output: Đoạn code sẵn sàng copy-paste vào landing page

## Ví Dụ

- `/kit-qr qr` — Tạo section QR code đơn giản với thông tin ngân hàng bên dưới
- `/kit-qr pricing` — Tạo pricing cards 3 gói với QR riêng cho từng gói
- `/kit-qr modal` — Modal thanh toán xuất hiện khi click nút "Mua ngay"
- `/kit-qr dynamic` — JavaScript generate QR theo sản phẩm khách chọn
- `/kit-qr multi` — Section nhiều sản phẩm, mỗi sản phẩm có QR riêng

## Mẹo Triển Khai

- Thay `YOUR_ACCOUNT` và `YOUR_BANK` bằng thông tin tài khoản SePay thực của anh/chị
- Luôn hiển thị thông tin ngân hàng bên cạnh QR — một số khách thích chuyển khoản thủ công
- Test QR bằng app ngân hàng của chính anh/chị trước khi go live
- Dùng kiểu `modal` cho UX tốt nhất — giữ trang sạch, chỉ show QR khi khách sẵn sàng mua

## Format URL QR SePay

```
https://qr.sepay.vn/img?acc={SỐ_TÀI_KHOẢN}&bank={TÊN_NGÂN_HÀNG}&amount={SỐ_TIỀN}&des={NỘI_DUNG}
```

**Ví dụ:**
```
https://qr.sepay.vn/img?acc=0123456789&bank=Vietcombank&amount=1997000&des=KIT_LANDING_001
```

**Ngân hàng thường gặp:**
`Vietcombank` · `VPBank` · `BIDV` · `Techcombank` · `ACB` · `MBBank` · `Sacombank`
