---
name: payment-setup-guide
description: Hướng dẫn từng bước tích hợp thanh toán SePay VietQR — từ tạo tài khoản đến webhook tự động cho thị trường Việt Nam
version: 2.0.0
kit: AI Landing Engine Kit by 10xSystem
---

# Payment Setup Guide Skill

## Kích Hoạt Skill Này Khi

- Tích hợp thu tiền tự động vào ứng dụng/trang bán hàng
- Chấp nhận chuyển khoản ngân hàng không cần xác minh thủ công
- Cài đặt luồng thanh toán QR code
- Xử lý webhook thông báo xác nhận thanh toán
- Xây checkout page tối ưu cho khách hàng Việt Nam

---

## So Sánh Phương Thức Thanh Toán

### SePay VietQR (Khuyến Nghị)
**Tốt nhất cho:** Business đang scale, tự động hóa
- ✅ Webhook thông báo thanh toán realtime
- ✅ Hỗ trợ 44+ ngân hàng Việt Nam
- ✅ API generate QR code
- ✅ Lịch sử giao dịch và đối soát
- ❌ Phí dịch vụ nhỏ
- ❌ Cần xác minh business

### Chuyển Khoản Thủ Công
**Tốt nhất cho:** MVP ban đầu, volume thấp
- ✅ Không tốn chi phí tích hợp
- ✅ Không cần setup kỹ thuật
- ❌ Phải xác minh thủ công từng đơn
- ❌ Xác nhận đơn hàng chậm
- ❌ Trải nghiệm khách hàng kém khi scale

### Stripe / PayPal (Quốc Tế)
**Tốt nhất cho:** Khách hàng nước ngoài, thanh toán thẻ
- ✅ Hỗ trợ thẻ credit/debit
- ✅ Tiếp cận quốc tế
- ❌ Phí cao (2–4%)
- ❌ Overhead quy đổi tiền tệ
- ❌ Tích hợp ngân hàng Việt hạn chế

---

## Workflow Cài Đặt Nhanh

```
Bước 1: Đăng Ký Tài Khoản
         └─> Tạo tài khoản sandbox để test an toàn

Bước 2: API Credentials
         └─> Generate authentication token

Bước 3: Cấu Hình Webhook
         └─> Cài endpoint nhận thông báo thanh toán

Bước 4: Tích Hợp QR Code
         └─> Thêm generate QR động vào trang

Bước 5: Order Matching Logic
         └─> Parse nội dung chuyển khoản để khớp đơn

Bước 6: Testing
         └─> Xác minh giao dịch sandbox hoạt động

Bước 7: Production Deploy
         └─> Chuyển sang môi trường live
```

---

## Khả Năng Tích Hợp

| Tính Năng | Khả Năng | Chi Tiết |
|-----------|----------|---------|
| Phương Thức TT | Bank QR, Card, Virtual Account | Integration Guide |
| Ngân Hàng | 44+ ngân hàng Việt | Integration Guide |
| Tốc Độ Phản Hồi | Realtime qua webhook | Integration Guide |
| Xác Thực | API Token | Integration Guide |
| Rate Limits | 2 calls/giây | Integration Guide |
| Retry | Tự động retry tối đa 7 lần | Integration Guide |
| QR Generation | Dynamic URL-based | Checkout Flow Patterns |
| Order Matching | Parse content với fallbacks | Checkout Flow Patterns |

---

## Checklist Triển Khai

### Phase 1: Setup
- [ ] Đăng ký tài khoản sandbox
- [ ] Generate API authentication token
- [ ] Cấu hình URL webhook endpoint
- [ ] Test webhook với mock payload
- [ ] Xác minh xử lý 200 response

### Phase 2: Tích Hợp
- [ ] Triển khai generate QR code
- [ ] Build checkout page UI
- [ ] Thêm order status polling
- [ ] Xử lý payment confirmation
- [ ] Test transaction matching logic

### Phase 3: Bảo Mật
- [ ] Triển khai timing-safe auth validation
- [ ] Thêm duplicate transaction prevention
- [ ] Bật HTTPS cho webhooks
- [ ] Cài đặt error logging
- [ ] Cấu hình retry limits

### Phase 4: Production
- [ ] Hoàn thành business verification
- [ ] Chuyển sang production API endpoint
- [ ] Monitor webhook delivery rate
- [ ] Cài transaction reconciliation
- [ ] Cấu hình customer support flows

---

## Reference Files

### [payment-gateway-integration-guide.md](./references/payment-gateway-integration-guide.md)
Cài đặt kỹ thuật đầy đủ gồm:
- Tạo tài khoản và cấu hình API
- Triển khai webhook kèm code examples (có chú thích tiếng Việt)
- Best practices bảo mật
- Quy trình test và deploy
- Troubleshoot lỗi phổ biến

### [checkout-flow-design-patterns.md](./references/checkout-flow-design-patterns.md)
Hướng dẫn UX optimization gồm:
- Thiết kế checkout page chuyển đổi cao
- Chiến lược hiển thị QR code
- Layout responsive mobile
- Payment confirmation patterns
- Error handling workflows

---

## Use Cases Phổ Biến

**Bán sản phẩm số (AI Landing Engine Kit use case):**
```
Khách chọn sản phẩm → Hiện QR → Quét ngân hàng
→ SePay confirm → Webhook → Tự động giao hàng
```

**Dịch vụ đặt lịch:**
```
Chọn slot → Thanh toán cọc QR → Confirm tức thì
→ Gửi xác nhận email → Add to calendar
```

**Sự kiện/Workshop:**
```
Đăng ký → Thanh toán QR → Nhận ticket tự động
→ Nhắc nhở trước sự kiện
```

---

## Ước Tính Thời Gian Cài Đặt

- **Basic Setup:** 2–4 giờ (webhook + QR display)
- **Full Checkout Flow:** 1–2 ngày (UI + matching logic + testing)
- **Production Hardening:** 1–2 ngày (security + monitoring + edge cases)

*AI Landing Engine Kit | Skill: Payment Setup Guide | by 10xSystem*
