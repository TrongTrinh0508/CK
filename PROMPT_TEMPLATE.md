# HƯỚNG DẪN SỬ DỤNG PROMPTS PHÂN TÍCH CHỨNG KHOÁN

> Hệ thống 4 prompts chuyên nghiệp cho trader Việt Nam  
> Phân tích T+2/T+3 và trung hạn 2-4 tuần • SL 5% • TP 5-10%

---

## 📋 TỔNG QUAN 4 PROMPTS

| Prompt                    | Khi nào dùng                | Thời gian | Độ phức tạp     |
| ------------------------- | --------------------------- | --------- | --------------- |
| **ck-phan-tich-co-phieu** | Phân tích mã mới hàng ngày  | ~30s      | ⭐ Đơn giản     |
| **ck-cap-nhat-co-phieu**  | Đang giữ CP, hỏi nên làm gì | ~30s      | ⭐ Đơn giản     |
| **ck-so-sanh-co-phieu**   | Chọn giữa 2 mã              | ~45s      | ⭐⭐ Trung bình |
| **ck-phan-tich-tong-hop** | Phiên bất thường + tin tức  | ~60s      | ⭐⭐⭐ Nâng cao |

---

## 🔵 PROMPT 1: Phân tích cổ phiếu mới

### `/ck-phan-tich-co-phieu`

**DÙNG KHI:** Phân tích mã mới mỗi ngày, thuần kỹ thuật, không cần tin tức.

**CẦN CHUẨN BỊ:**

- Mã cổ phiếu (VD: MWG, FPT, VNM)
- 3 hình ảnh:
  1. Chart nến ngày zoom gần (3 tháng) + bảng giá SSI iBoard
  2. Chart nến ngày zoom xa (6-12 tháng)
  3. NN mua ròng 10 phiên từ SSI iBoard app

**CÁCH DÙNG:**

```
1. Gõ: /ck-phan-tich-co-phieu
2. Nhập: MWG
3. Đính kèm 3 hình
4. Enter
```

**NHẬN ĐƯỢC:**

- A. Đọc dữ liệu từ biểu đồ
- B. Phân tích kỹ thuật (xu hướng, MA, Ichimoku, Volume, NN, indicators)
- C. Chiến lược T+2/T+3 + Trung hạn 2-4 tuần
- D. 3 kịch bản (tích cực, sideway, tiêu cực)
- E. Đánh giá tổng hợp (Risk:Reward, độ tin cậy)
- F. Tóm tắt 1 dòng

**VÍ DỤ OUTPUT:**

```
T+:     MUA | Vào: 85-86 | SL: 81.7 | TP: 90-93 | Lệnh mua: LO | Lệnh bán: ATC | Tin cậy: 70%
Trung hạn: MUA | Vào: 85-86 | SL: 81.7 | TP1: 90 | TP2: 95 | Giữ: 2-3 tuần | Tin cậy: 65%
```

---

## 🟢 PROMPT 2: Cập nhật cổ phiếu đang giữ

### `/ck-cap-nhat-co-phieu`

**DÙNG KHI:** Đang giữ cổ phiếu, muốn biết nên giữ tiếp, chốt lời, cắt lỗ hay mua thêm.

**CẦN CHUẨN BỊ:**

- Thông tin vị thế: Mã + Giá mua + Lãi/Lỗ % + Số ngày giữ
- 3 hình ảnh mới nhất (cùng cách chụp như prompt 1)

**CÁCH DÙNG:**

```
1. Gõ: /ck-cap-nhat-co-phieu
2. Nhập: MWG mua 86 lãi 3% giữ 5 ngày
3. Đính kèm 3 hình mới
4. Enter
```

**NHẬN ĐƯỢC:**

- A. Đọc dữ liệu từ biểu đồ
- B. Phân tích kỹ thuật hiện tại
- C. So sánh với vị thế (giá mua vs giá hiện tại, lãi/lỗ, khoảng cách tới SL)
- D. Khuyến nghị: **GIỮ / CHỐT LỜI / CẮT LỖ** + Mua thêm?
- E. 3 kịch bản tiếp theo
- F. Đánh giá tổng hợp
- G. Tóm tắt 1 dòng

**VÍ DỤ OUTPUT:**

```
GIỮ | Giá hiện tại: 88.5 | Lãi: +2.9% | TP mới: 92 | SL mới: 84 | Tin cậy: 75%
- Lý do: Xu hướng ngắn hạn vẫn tăng, MACD chưa cắt xuống, NN tiếp tục mua ròng
- Dời SL lên 84 để bảo vệ lợi nhuận
```

---

## 🟡 PROMPT 3: So sánh 2 mã cổ phiếu

### `/ck-so-sanh-co-phieu`

**DÙNG KHI:** Phân vân giữa 2 mã, muốn biết nên ưu tiên mã nào cho T+ hoặc trung hạn.

**CẦN CHUẨN BỊ:**

- 2 mã cổ phiếu (VD: MWG vs FPT)
- 6 hình ảnh (3 hình cho mỗi mã)

**CÁCH DÙNG:**

```
1. Gõ: /ck-so-sanh-co-phieu
2. Nhập: MWG vs FPT
3. Đính kèm 6 hình (3 hình MWG + 3 hình FPT)
4. Enter
```

**NHẬN ĐƯỢC:**

- Bảng so sánh chi tiết (xu hướng, MA, Volume, NN, RSI, MACD, Risk:Reward...)
- Mã nào ưu tiên cho T+? Lý do?
- Mã nào tốt hơn cho trung hạn? Lý do?
- Nếu chỉ chọn 1: chọn mã nào? Chiến lược nào?
- Tóm tắt 1 dòng cho mỗi mã

**VÍ DỤ OUTPUT:**

```
MWG: MUA | T+3 | Vào: 85-86 | SL: 81.7 | TP: 90 | Tin cậy: 70%
FPT: MUA | Trung hạn | Vào: 125-126 | SL: 119 | TP: 135 | Tin cậy: 75%

Khuyến nghị: Ưu tiên FPT cho trung hạn (xu hướng mạnh hơn, NN mua ròng liên tục).
```

---

## 🔴 PROMPT 4: Phân tích tổng hợp (Kỹ thuật + Cơ bản)

### `/ck-phan-tich-tong-hop`

**DÙNG KHI:**

- Phiên trần/sàn bất thường → cần biết lý do
- Volume đột biến 300-500% → xác định có pump không
- Cổ phiếu ngành nhạy cảm (Ngân hàng, BĐS, CK) → chính sách vĩ mô ảnh hưởng
- Giữ trung hạn 2-4 tuần → KQKD sắp công bố

**CẦN CHUẨN BỊ:**

- Mã cổ phiếu
- 3 hình ảnh
- **Link tin tức (tùy chọn):**
  - KQKD: https://finance.vietstock.vn/MWG...
  - Tin ngành: https://cafef.vn/...
  - CBTT: https://cafef.vn/cong-bo-thong-tin...

**CÁCH DÙNG:**

**Trường hợp 1: Có tin tức/KQKD**

```
1. Gõ: /ck-phan-tich-tong-hop
2. Nhập: MWG + https://finance.vietstock.vn/MWG-ctcp-dau-tu-the-gioi-di-dong.htm
3. Đính kèm 3 hình
4. Enter
```

**Trường hợp 2: Không có tin (phân tích tổng hợp thuần kỹ thuật)**

```
1. Gõ: /ck-phan-tich-tong-hop
2. Nhập: VNM
3. Đính kèm 3 hình (không cần link)
4. Enter
```

**NHẬN ĐƯỢC:**

- A. Đọc dữ liệu từ biểu đồ
- B. Phân tích kỹ thuật
- C. **Phân tích cơ bản** (nếu có link):
  - C1. KQKD (doanh thu, lợi nhuận, EPS, P/E, ROE...)
  - C2. Tin tức & sự kiện (catalyst)
  - C3. Yếu tố vĩ mô & ngành
- D. **Tổng hợp kỹ thuật + cơ bản**:
  - So sánh tín hiệu kỹ thuật vs cơ bản
  - Đồng thuận hay mâu thuẫn?
  - Giải thích sự kiện bất thường (trần/sàn, volume lạ...)
- E. Chiến lược T+ & Trung hạn (tích hợp yếu tố cơ bản)
- F. 3 kịch bản (có thêm yếu tố tin tức)
- G. Đánh giá tổng hợp
- H. Tóm tắt 1 dòng

**VÍ DỤ OUTPUT:**

```
T+:     MUA | Vào: 85-86 | SL: 81.7 | TP: 92 | Tin cậy: 75% | Catalyst: KQKD Q1 tăng 20%
Trung hạn: MUA | Vào: 85-86 | SL: 81.7 | TP1: 92 | TP2: 98 | Giữ: 3-4 tuần | Tin cậy: 80% | Cơ bản: TÍCH CỰC

Nhận xét: Kỹ thuật + Cơ bản ĐỒNG THUẬN MUA. KQKD tốt giải thích phiên trần hôm nay.
Catalyst tiếp theo: ĐHCĐ chia cổ tức 15% vào tháng 5.
```

---

## 📸 HƯỚNG DẪN CHỤP 3 HÌNH CHUẨN

### Hình 1: Chart ngày zoom gần (3 tháng) + Bảng giá SSI iBoard

**Cách chụp:**

1. Mở TradingView trên PC, chọn mã CP, timeframe 1D, zoom 3 tháng
2. Mở SSI iBoard (web hoặc app), hiện bảng giá/depth bên cạnh
3. Chụp màn hình (split screen) hoặc ghép 2 ảnh

**Phải hiển thị:**

- Chart: Nến Nhật + MA(9) / Ichimoku + Volume + BBW + Stoch RSI + MACD + Momentum
- Bảng giá: Giá trần/sàn/tham chiếu, dư mua/bán, phân tích khối lượng

**Ví dụ:** (như hình MWG bạn đã gửi trước đó)

---

### Hình 2: Chart ngày zoom xa (6-12 tháng)

**Cách chụp:**

1. TradingView, timeframe 1D, zoom ra 6-12 tháng
2. Full screen, chụp màn hình

**Phải hiển thị:**

- Cùng bộ indicator như hình 1
- Để thấy xu hướng trung hạn, đỉnh/đáy lớn, vùng hỗ trợ/kháng cự

---

### Hình 3: NN mua ròng 10 phiên (SSI iBoard app)

**Cách chụp:**

1. Mở app SSI trên điện thoại
2. Vào mã CP → tab "NN mua ròng" hoặc "Khối ngoại"
3. Chụp màn hình

**Phải hiển thị:**

- KL NN mua hôm nay
- KL NN bán hôm nay
- Room NN còn lại
- Biểu đồ cột NN mua ròng 10 phiên gần nhất

**Ví dụ:** (như hình NN của MWG bạn đã gửi)

---

## ⚙️ SETUP INDICATOR CHUẨN TRÊN TRADINGVIEW

| Indicator     | Thông số                 | Mục đích                      |
| ------------- | ------------------------ | ----------------------------- |
| **MA**        | 9, 26                    | Xu hướng ngắn hạn             |
| **Ichimoku**  | 9, 26, 52, 26 (mặc định) | Cloud, trend, hỗ trợ/kháng cự |
| **Volume**    | Mặc định                 | Dòng tiền                     |
| **BBW**       | 20, 2                    | Phát hiện squeeze/breakout    |
| **Stoch RSI** | 14, 14, 3, 3             | Quá mua / quá bán             |
| **MACD**      | 12, 26, 9                | Tín hiệu mua/bán trung hạn    |
| **Momentum**  | 10                       | Đo sức mạnh đà tăng/giảm      |

**Cách setup nhanh:**

1. TradingView → mở mã CP
2. Click "Indicators" → tìm từng indicator theo tên
3. Add vào chart → điều chỉnh thông số (nếu cần)
4. Lưu layout để dùng lại

---

## 🔗 NGUỒN TIN ĐÁNG TIN CẬY (cho prompt 4)

### 1. Tin tức & Phân tích vĩ mô

- **CafeF** - https://cafef.vn/ (tin nhanh nhất, realtime)
- **VnEconomy** - https://vneconomy.vn/ (phân tích chiều sâu)

### 2. KQKD & Tài chính (QUAN TRỌNG NHẤT)

- **VietStock Finance** - https://finance.vietstock.vn/ (báo cáo tài chính chuẩn)
- **Fireant** - https://fireant.vn/ (dashboard trực quan)

### 3. Công bố thông tin chính thức

- **CafeF CBTT** - https://cafef.vn/cong-bo-thong-tin.chn
- **HOSE/HNX** - Thông báo chính thức từ sàn

**Lưu ý:** Chỉ dùng link khi thực sự cần (phiên bất thường, tin quan trọng). Hầu hết trường hợp, phân tích thuần kỹ thuật (prompt 1) đã đủ.

---

## 📊 SO SÁNH 4 PROMPTS

| Tính năng                     | Prompt 1  | Prompt 2  | Prompt 3   | Prompt 4            |
| ----------------------------- | --------- | --------- | ---------- | ------------------- |
| Phân tích kỹ thuật            | ✅ Đầy đủ | ✅ Đầy đủ | ✅ So sánh | ✅ Đầy đủ           |
| Phân tích cơ bản              | ❌        | ❌        | ❌         | ✅ Có (nếu có link) |
| Chiến lược T+                 | ✅        | ✅        | ✅         | ✅                  |
| Chiến lược trung hạn          | ✅        | ✅        | ✅         | ✅                  |
| So sánh vị thế hiện tại       | ❌        | ✅        | ❌         | ❌                  |
| So sánh 2 mã                  | ❌        | ❌        | ✅         | ❌                  |
| Đọc link tin tức              | ❌        | ❌        | ❌         | ✅                  |
| Giải thích sự kiện bất thường | ❌        | ❌        | ❌         | ✅                  |
| Thời gian phân tích           | ~30s      | ~30s      | ~45s       | ~60s                |

---

## 🎯 WORKFLOW ĐỀ XUẤT

### Kịch bản 1: Phân tích mã mới hàng ngày (90% trường hợp)

```
Sáng → Chụp 3 hình mã muốn vào
      → /ck-phan-tich-co-phieu
      → Đọc phân tích → Quyết định vào lệnh
```

**LÝ DO:** Nhanh, đơn giản, thuần kỹ thuật, không cần đọc tin.

---

### Kịch bản 2: Cập nhật cổ phiếu đang giữ

```
Chiều (hoặc sáng hôm sau) → Chụp 3 hình mới
                          → /ck-cap-nhat-co-phieu
                          → Quyết định giữ/chốt/cắt
```

---

### Kịch bản 3: Phân vân giữa 2 mã

```
Chụp 3 hình cho mỗi mã (6 hình total)
→ /ck-so-sanh-co-phieu
→ Chọn mã tốt hơn
```

---

### Kịch bản 4: Phiên bất thường / Tin tức quan trọng

```
Thấy phiên trần/sàn, volume lạ, hoặc có tin KQKD/M&A
→ Tìm link tin tức từ CafeF / VietStock Finance
→ Chụp 3 hình
→ /ck-phan-tich-tong-hop + Gửi kèm link
→ Hiểu rõ nguyên nhân → Chiến lược phù hợp
```

---

## 💡 MẸO SỬ DỤNG HIỆU QUẢ

### ✅ NÊN:

1. Chụp hình RÕ NÉT, đủ indicator, không cắt xén trục giá
2. Gửi đúng 3 hình theo thứ tự (zoom gần → zoom xa → NN)
3. Dùng prompt 1 cho 90% trường hợp (T+ hàng ngày)
4. Dùng prompt 4 chỉ khi có sự kiện đặc biệt (trần/sàn, tin quan trọng)
5. Lưu lại các phân tích để so sánh với kết quả thực tế → học hỏi

### ❌ KHÔNG NÊN:

1. Gửi hình mờ, thiếu indicator, zoom quá sát (chỉ thấy 1-2 nến)
2. Hỏi chung chung "cổ phiếu này thế nào" mà không gửi hình
3. Dùng prompt 4 cho mọi trường hợp → mất thời gian, overthink
4. Gửi quá nhiều link tin tức không liên quan → làm loãng phân tích
5. Bỏ qua hình 3 (NN mua ròng) → thiếu góc nhìn dòng tiền

---

## 🚀 BẮT ĐẦU NHANH - 3 BƯỚC

### Bước 1: Setup TradingView (1 lần duy nhất)

- Add đủ 7 indicator theo bảng trên
- Save layout để dùng lại

### Bước 2: Chụp 3 hình (mỗi ngày)

- Hình 1: Chart 3 tháng + bảng giá SSI
- Hình 2: Chart 6-12 tháng
- Hình 3: NN mua ròng từ SSI app

### Bước 3: Chọn prompt phù hợp và gửi

- 90% trường hợp: `/ck-phan-tich-co-phieu`
- Đang giữ CP: `/ck-cap-nhat-co-phieu`
- Phân vân 2 mã: `/ck-so-sanh-co-phieu`
- Có tin bất thường: `/ck-phan-tich-tong-hop`

---

## 📞 HỖ TRỢ & GHI CHÚ

- **Repository:** https://github.com/TrongTrinh0508/CK
- **Branch hiện tại:** `ck-prompts`
- **Phiên bản:** 1.0 (17/04/2026)

**Lưu ý quan trọng:**

- Prompts này là công cụ hỗ trợ, KHÔNG phải lời khuyên đầu tư
- Luôn tuân thủ SL -5% nghiêm ngặt
- Quản lý vốn: Không bao giờ all-in 1 lệnh
- Đầu tư có rủi ro, chỉ bỏ số tiền có thể chấp nhận mất

---

**Chúc bạn giao dịch thành công! 📈**
