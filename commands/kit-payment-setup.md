---
description: Cài đặt cổng thanh toán SePay VietQR từng bước
argument-hint: [bước]
---

Hướng dẫn cài đặt SePay thanh toán tự động cho solopreneur Việt Nam.

<args>$ARGUMENTS</args>

## Các Bước

- `start` — Bắt đầu từ đầu (tạo tài khoản → QR đầu tiên)
- `api` — Cấu hình API token và xác thực
- `qr` — Tạo link VietQR payment
- `webhook` — Cài webhook nhận xác nhận thanh toán tự động
- `test` — Chạy test toàn bộ luồng thanh toán
- `compare` — So sánh các phương thức thanh toán phù hợp

## Quy Trình

1. Kích hoạt Deliver Agent
2. Dùng skill Payment Setup Guide
3. Hướng dẫn từng bước cấu hình SePay
4. Output: Link thanh toán hoạt động + webhook endpoint

## Ví Dụ

- `/kit-payment-setup start` — Hướng dẫn đầy đủ từ tạo tài khoản SePay đến QR code đầu tiên
- `/kit-payment-setup webhook` — Cấu hình webhook nhận xác nhận thanh toán realtime
- `/kit-payment-setup test` — Chạy test transaction để xác minh toàn bộ luồng hoạt động
- `/kit-payment-setup compare` — Xem ưu nhược điểm của SePay vs. chuyển khoản thủ công vs. Stripe

## Mẹo Bảo Mật Bắt Buộc

- Dùng SePay sandbox mode trước, chỉ chuyển production sau khi đã test hoàn toàn
- Luôn xác minh chữ ký HMAC trên webhook callbacks — phòng tránh thanh toán giả mạo
- Lưu API keys trong environment variables — KHÔNG bao giờ hardcode trong source code
- Implement deduplication để không giao hàng 2 lần cho cùng 1 giao dịch

## Thông Tin SePay VietQR

```
✅ Hỗ trợ 44+ ngân hàng Việt Nam
✅ Không phí merchant cho chuyển khoản
✅ Webhook realtime (< 5 giây)
✅ API đơn giản, dễ tích hợp
✅ Phù hợp solopreneur, không cần giấy phép phức tạp
✅ Tích hợp vào landing page không cần backend (QR embed)
```
