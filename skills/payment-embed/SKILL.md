---
name: payment-embed
description: Nhúng thanh toán SePay VietQR vào landing page — 4 patterns sẵn dùng, không cần backend cho basic integration
version: 2.0.0
kit: AI Landing Engine Kit by 10xSystem
---

# SePay Payment Embed Skill

## Tổng Quan

Skill này hướng dẫn cách nhúng SePay VietQR vào landing page để nhận chuyển khoản ngân hàng tại Việt Nam.

### Mục Đích
- Thêm VietQR payment vào landing page
- Nhận thanh toán VNĐ qua chuyển khoản ngân hàng
- Không cần backend cho basic QR embed

### Lợi Ích Chính
- Không cần backend cho integration cơ bản
- QR code thân thiện, khách quét bằng app ngân hàng quen thuộc
- Chuyển tiền thẳng vào tài khoản ngân hàng của anh/chị
- 44+ ngân hàng Việt Nam được hỗ trợ
- Xác nhận tức thì qua webhook (nếu cần backend)

---

## Cách SePay VietQR Hoạt Động

```
1. Đăng ký tài khoản SePay tại my.sepay.vn
2. Kết nối tài khoản ngân hàng (44+ ngân hàng VN)
3. Generate QR codes qua SePay API URL
4. Khách quét QR bằng app ngân hàng
5. Tiền chuyển thẳng vào tài khoản ngân hàng của anh/chị
6. SePay gửi webhook khi xác nhận thanh toán (optional)
```

### Không Cần Backend Cho Basic Integration
Chỉ cần URL hình ảnh — phù hợp hoàn hảo cho static landing pages.

---

## Generate QR Code

### Format URL API
```
https://qr.sepay.vn/img?acc={TÀI_KHOẢN}&bank={NGÂN_HÀNG}&amount={SỐ_TIỀN}&des={NỘI_DUNG}
```

### Parameters

| Parameter | Bắt Buộc | Mô Tả | Ví Dụ |
|-----------|----------|-------|-------|
| `acc` | Có | Số tài khoản ngân hàng | `0123456789` |
| `bank` | Có | Tên ngân hàng (chính xác theo SePay) | `Vietcombank` |
| `amount` | Không | Số tiền VNĐ (số nguyên) | `1997000` |
| `des` | Không | Nội dung chuyển khoản (URL encoded) | `KIT_LANDING_001` |
| `template` | Không | Kiểu QR: trống (default), `compact`, `qronly` | `compact` |

### Ví Dụ URL

```
# QR cơ bản — khách tự nhập số tiền
https://qr.sepay.vn/img?acc=0123456789&bank=Vietcombank

# QR cố định số tiền
https://qr.sepay.vn/img?acc=0123456789&bank=Vietcombank&amount=1997000

# QR đầy đủ với nội dung chuyển khoản
https://qr.sepay.vn/img?acc=0123456789&bank=Vietcombank&amount=1997000&des=KIT_LANDING_001

# Kiểu compact (nhỏ gọn hơn)
https://qr.sepay.vn/img?acc=0123456789&bank=Vietcombank&amount=1997000&template=compact
```

---

## 4 Patterns Nhúng HTML

### Pattern 1: QR Đơn Giản (Dễ Nhất)
Phù hợp mọi loại trang, chỉ cần copy-paste và thay placeholder.

```html
<!-- Section thanh toán QR đơn giản -->
<div class="payment-section text-center p-8 bg-gray-50 rounded-2xl">
  <h3 class="text-2xl font-bold mb-2 text-gray-800">Thanh Toán Nhanh</h3>
  <p class="text-gray-500 mb-6">Quét QR bằng app ngân hàng — 44+ ngân hàng hỗ trợ</p>

  <!-- QR Code từ SePay API — thay YOUR_ACCOUNT, YOUR_BANK, YOUR_AMOUNT -->
  <img
    src="https://qr.sepay.vn/img?acc=YOUR_ACCOUNT&bank=YOUR_BANK&amount=YOUR_AMOUNT&des=YOUR_PRODUCT"
    alt="Mã QR thanh toán"
    class="mx-auto w-64 h-64 rounded-xl shadow-lg"
  />

  <!-- Thông tin cho khách thích chuyển thủ công -->
  <div class="mt-6 text-left max-w-sm mx-auto bg-white rounded-xl p-4 shadow-sm">
    <p class="mb-2 text-sm"><strong>Ngân hàng:</strong> YOUR_BANK</p>
    <p class="mb-2 text-sm"><strong>Số TK:</strong> YOUR_ACCOUNT</p>
    <p class="mb-2 text-sm"><strong>Số tiền:</strong> X,XXX,XXX VNĐ</p>
    <p class="mb-2 text-sm"><strong>Nội dung CK:</strong> YOUR_PRODUCT</p>
  </div>

  <p class="mt-4 text-xs text-gray-400">
    Xác nhận tự động • Giao hàng trong 60 giây
  </p>
</div>
```

### Pattern 2: Pricing Card Với QR (Chuyên Nghiệp)
Tích hợp QR ngay trong pricing card — tăng trust và tiện lợi.

```html
<!-- Pricing card với QR tích hợp -->
<div class="bg-white rounded-2xl shadow-xl p-8 border-2 border-blue-500 max-w-sm mx-auto">
  <!-- Header pricing -->
  <div class="text-center">
    <span class="bg-blue-100 text-blue-700 text-xs font-semibold px-3 py-1 rounded-full">PHỔ BIẾN NHẤT</span>
    <h3 class="text-xl font-bold text-gray-800 mt-3">AI Landing Engine Kit</h3>
    <div class="mt-4">
      <span class="text-4xl font-bold text-blue-600">1,997,000</span>
      <span class="text-gray-500 ml-1">VNĐ</span>
    </div>
    <p class="text-sm text-gray-400 mt-1">Trọn bộ, dùng vĩnh viễn</p>
  </div>

  <!-- Danh sách tính năng -->
  <ul class="mt-6 space-y-3">
    <li class="flex items-center text-gray-700 text-sm">
      <span class="text-green-500 mr-2">✓</span> 2 AI Agents chuyên biệt
    </li>
    <li class="flex items-center text-gray-700 text-sm">
      <span class="text-green-500 mr-2">✓</span> 9 Skills + 9 Commands
    </li>
    <li class="flex items-center text-gray-700 text-sm">
      <span class="text-green-500 mr-2">✓</span> 10 Landing page templates
    </li>
    <li class="flex items-center text-gray-700 text-sm">
      <span class="text-green-500 mr-2">✓</span> Hỗ trợ SePay VietQR
    </li>
  </ul>

  <!-- QR Payment -->
  <div class="mt-8 text-center border-t pt-6">
    <p class="text-sm text-gray-500 mb-3">Quét QR để mua ngay</p>
    <img
      src="https://qr.sepay.vn/img?acc=YOUR_ACCOUNT&bank=YOUR_BANK&amount=1997000&des=KIT_LANDING&template=compact"
      alt="Quét để thanh toán"
      class="mx-auto w-40 h-40 rounded-lg shadow-md"
    />
    <p class="text-xs text-gray-400 mt-2">44+ ngân hàng • Xác nhận tức thì</p>
  </div>
</div>
```

### Pattern 3: Modal Popup (UX Tốt Nhất)
QR hiện trong popup khi click "Mua ngay" — trang sạch sẽ, UX tốt.

```html
<!-- Nút trigger -->
<button
  onclick="showPaymentModal()"
  class="bg-blue-600 text-white px-8 py-4 rounded-xl font-bold text-lg hover:bg-blue-700 transition-all shadow-lg hover:shadow-xl">
  Mua Ngay — 1,997,000 VNĐ →
</button>

<!-- Modal overlay -->
<div id="payment-modal" class="hidden fixed inset-0 bg-black/60 flex items-center justify-center z-50 p-4">
  <div class="bg-white rounded-2xl p-8 max-w-md w-full relative shadow-2xl">

    <!-- Nút đóng -->
    <button
      onclick="hidePaymentModal()"
      class="absolute top-4 right-4 text-gray-400 hover:text-gray-600 text-2xl font-bold w-8 h-8 flex items-center justify-center">
      ×
    </button>

    <!-- Header -->
    <div class="mb-6">
      <h3 class="text-xl font-bold text-gray-800">Hoàn Tất Thanh Toán</h3>
      <p class="text-sm text-gray-500 mt-1">Quét QR bằng app ngân hàng của bạn</p>
    </div>

    <!-- QR Code -->
    <div class="text-center">
      <img
        src="https://qr.sepay.vn/img?acc=YOUR_ACCOUNT&bank=YOUR_BANK&amount=1997000&des=KIT_001"
        alt="QR thanh toán"
        class="mx-auto w-56 h-56 rounded-xl shadow-lg"
      />

      <!-- Thông tin chuyển khoản -->
      <div class="mt-4 bg-gray-50 rounded-xl p-4 text-sm text-left">
        <p class="mb-1"><strong>Ngân hàng:</strong> YOUR_BANK</p>
        <p class="mb-1"><strong>Số TK:</strong> YOUR_ACCOUNT</p>
        <p class="mb-1"><strong>Số tiền:</strong> 1,997,000 VNĐ</p>
        <p><strong>Nội dung:</strong> KIT_001</p>
      </div>

      <!-- Thông tin sau thanh toán -->
      <div class="mt-4 bg-blue-50 rounded-xl p-3 text-sm text-blue-800">
        <p class="font-semibold">Sau khi thanh toán:</p>
        <p class="mt-1">Anh/chị sẽ nhận sản phẩm qua email trong 60 giây</p>
      </div>
    </div>
  </div>
</div>

<script>
// Hiện modal thanh toán
function showPaymentModal() {
  document.getElementById('payment-modal').classList.remove('hidden');
  document.body.style.overflow = 'hidden'; // Ngăn scroll nền
}

// Ẩn modal thanh toán
function hidePaymentModal() {
  document.getElementById('payment-modal').classList.add('hidden');
  document.body.style.overflow = '';
}

// Click ngoài modal để đóng
document.getElementById('payment-modal').addEventListener('click', function(e) {
  if (e.target === this) hidePaymentModal();
});
</script>
```

### Pattern 4: Dynamic QR (Nhiều Sản Phẩm)
JavaScript generate QR động theo sản phẩm/gói khách chọn.

```html
<div id="payment-container" class="text-center">
  <img id="qr-code" alt="QR thanh toán" class="w-64 h-64 mx-auto rounded-xl shadow-lg" />
  <div id="payment-details" class="mt-4 text-sm text-gray-600"></div>
</div>

<script>
// Hàm generate URL QR từ SePay
function generatePaymentQR(options) {
  const params = new URLSearchParams({
    acc: options.account,
    bank: options.bank,
  });

  // Thêm các params tùy chọn nếu có
  if (options.amount) params.set('amount', options.amount);
  if (options.description) params.set('des', options.description);
  if (options.template) params.set('template', options.template);

  return `https://qr.sepay.vn/img?${params}`;
}

// Cập nhật QR theo sản phẩm được chọn
function updatePaymentQR(productId, amount, label) {
  const qrUrl = generatePaymentQR({
    account: 'YOUR_ACCOUNT',
    bank: 'YOUR_BANK',
    amount: amount,
    description: `KIT_${productId}`,
    template: 'compact'
  });

  document.getElementById('qr-code').src = qrUrl;
  document.getElementById('payment-details').innerHTML = `
    <p class="font-semibold">${label}</p>
    <p class="text-lg font-bold text-blue-600">${amount.toLocaleString('vi-VN')} VNĐ</p>
    <p class="text-xs text-gray-400 mt-1">Nội dung CK: KIT_${productId}</p>
  `;
}

// Mặc định hiển thị gói Basic
updatePaymentQR('BASIC', 997000, 'Gói Cơ Bản');
</script>
```

---

## Reference Files

- **`sepay-embed-guide.md`** — Quick reference cho QR URL format, parameters, bank codes và embed snippets

---

## Ngân Hàng Hỗ Trợ (Phổ Biến)

`Vietcombank` · `VPBank` · `BIDV` · `Techcombank` · `ACB` · `MBBank` · `Sacombank` · `VietinBank` · `TPBank` · `OCB` · `HDBank` · `MSB` · `VIB` · `SHB`

Danh sách đầy đủ: `https://qr.sepay.vn/banks.json`

---

## Best Practices

### UX
- Luôn hiển thị thông tin ngân hàng bên cạnh QR — một số khách thích chuyển thủ công
- Bao gồm nội dung chuyển khoản — cần thiết để khớp đơn hàng
- Thêm hướng dẫn rõ: "Quét bằng app ngân hàng"
- Hiển thị số tiền theo format Việt Nam (1,997,000)

### Kỹ Thuật
- Dùng số tiền cố định cho sản phẩm, số tiền linh hoạt chỉ cho donation
- URL encode description — tránh ký tự đặc biệt trong `des` parameter
- Test trước khi go live — quét QR bằng app ngân hàng của chính anh/chị
- Thêm loading state khi QR image đang tải

### Bảo Mật
- QR URLs là public — chỉ encode thông tin thanh toán (an toàn để nhúng)
- Không expose webhook keys ở client-side
- Validate webhook signatures phía server
- Dùng HTTPS cho webhooks

*AI Landing Engine Kit | Skill: Payment Embed | by 10xSystem*
