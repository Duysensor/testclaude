# Workflow: Xây Trang Bán Hàng Chuyển Đổi Cao

**Thương hiệu:** 10xSystem  
**Bộ kit:** AI Landing Engine Kit  
**Thời gian hoàn thành:** 2–3 giờ  
**Output:** Trang landing page HTML hoàn chỉnh + copy thuyết phục + hệ thống xử lý từ chối  

---

## Kết Quả Sau Khi Hoàn Thành Workflow

```
✅ Copy trang bán hàng đầy đủ (14 sections)
✅ File HTML landing page sẵn sàng deploy
✅ FAQ section với 10+ từ chối được xử lý
✅ 3 biến thể headline để A/B test
✅ Section thanh toán SePay VietQR tích hợp
```

---

## Phase 1: Chuẩn Bị (15 phút)

### Bước 1.1 — Thu Thập Brief
Trả lời các câu hỏi sau trước khi bắt đầu:

```
📋 BRIEF TEMPLATE

Sản phẩm/dịch vụ: _______________
Giá bán: _______________
Đối tượng khách hàng: _______________
Top 3 nỗi đau của họ:
  1. _______________
  2. _______________
  3. _______________
Top 3 lợi ích khi mua:
  1. _______________
  2. _______________
  3. _______________
Từ chối thường gặp nhất:
  1. _______________
  2. _______________
Social proof hiện có: _______________
Guarantee muốn đưa ra: _______________
```

### Bước 1.2 — Chọn Chiến Lược
- **Có testimonials + social proof** → Dùng Hero + Testimonials + CTA pattern
- **Chưa có testimonials** → Dùng Hero + Features + Benefits pattern
- **Offer cao cấp (> 5 triệu)** → Dùng Funnel 3-step pattern
- **Khóa học/đào tạo** → Dùng Before-After + Proof pattern

---

## Phase 2: Viết Copy (45–60 phút)

### Bước 2.1 — Viết Headline Variations
```
/kit-copy pven [sản phẩm] + [đối tượng] + [kết quả]
```
→ Nhận 3 biến thể headline + 3 subheadline

### Bước 2.2 — Viết Full Sales Page Copy
```
/kit-sales-page full [tên sản phẩm + giá]
```
→ Nhận toàn bộ 14 sections theo brief đã chuẩn bị

### Bước 2.3 — Xây FAQ Section
```
/kit-objection [các từ chối từ brief]
```
→ Nhận script phản hồi + copy preemptive cho mỗi từ chối

**Từ chối ưu tiên cần xử lý:**
1. "Có phải lừa đảo không?" (luôn đặt đầu tiên)
2. "Đắt quá / không có tiền"
3. "Để sau / chưa phải lúc"
4. "Tôi không chắc mình có làm được không"
5. "Chỗ khác rẻ hơn"

---

## Phase 3: Build Landing Page (60–90 phút)

### Bước 3.1 — Generate HTML
```
/kit-landing-page [loại sản phẩm] [phong cách]
```

**Chọn phong cách theo sản phẩm:**
- Khóa học online → `course bold`
- Dịch vụ tư vấn → `service minimal`
- SaaS tool → `saas tech`
- Sản phẩm số → `ecommerce bold`

### Bước 3.2 — Tích Hợp Copy Vào HTML
Thay thế các placeholder trong HTML với copy từ Phase 2:
- `{{HEADLINE}}` → Headline đã chọn
- `{{SUBHEADLINE}}` → Subheadline phù hợp
- `{{PROBLEM_SECTION}}` → Copy pain agitation
- `{{BENEFITS}}` → Danh sách lợi ích
- `{{TESTIMONIALS}}` → Social proof
- `{{OFFER_STACK}}` → Offer và bonus
- `{{FAQ}}` → FAQ từ bước 2.3

### Bước 3.3 — Tích Hợp Thanh Toán
```
/kit-qr modal
```
→ Nhận code modal QR payment, thay thế:
- `YOUR_ACCOUNT` → Số tài khoản SePay
- `YOUR_BANK` → Ngân hàng
- `YOUR_AMOUNT` → Giá bán (số nguyên VNĐ)
- `YOUR_PRODUCT` → Mã sản phẩm cho nội dung CK

---

## Phase 4: Review & Tối Ưu (15–30 phút)

### Checklist Review

**Copy:**
- [ ] Headline đọc trong 3 giây hiểu ngay lợi ích
- [ ] Mỗi section dẫn đến section tiếp theo tự nhiên
- [ ] Social proof có số liệu cụ thể, có ảnh thực
- [ ] Guarantee rõ ràng, không ambiguous
- [ ] FAQ xử lý đầy đủ "lừa đảo không?"

**Design:**
- [ ] CTA button màu tương phản mạnh
- [ ] Mobile responsive (test viewport 375px)
- [ ] Font size tối thiểu 16px trên mobile
- [ ] Button height tối thiểu 44px (thumb-friendly)
- [ ] QR code load nhanh và rõ nét

**Kỹ Thuật:**
- [ ] QR URL đúng format SePay
- [ ] Test QR bằng app ngân hàng thực
- [ ] Không URL localhost trong code
- [ ] Meta title + description đầy đủ

---

## Bước Tiếp Theo Sau Workflow Này

1. **Deploy trang:** Chạy [Delivery Automation Workflow](./delivery-automation-workflow.md)
2. **Cài thanh toán:** `/kit-payment-setup start`
3. **Cài thông báo:** `/kit-notify start`
4. **Deploy live:** `/kit-deploy vercel`

---

*AI Landing Engine Kit — Conversion Sales Workflow | by 10xSystem*
