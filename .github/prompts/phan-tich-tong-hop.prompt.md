---
description: "Phân tích tổng hợp cổ phiếu — Kết hợp kỹ thuật + cơ bản (KQKD, tin tức, vĩ mô). Gửi kèm 3 hình + link tin. Tự động đọc & ghi lịch sử theo mã."
argument-hint: "Mã CP + link KQKD/tin tức (VD: MWG + https://finance.vietstock.vn/MWG...)"
---

Phân tích tổng hợp ${input}.

HÌNH ẢNH ĐÍNH KÈM:

- Hình 1: Biểu đồ nến NGÀY (Daily) gần nhất (3 tháng) — hiển thị MA, Ichimoku, Volume, BBW, Stoch RSI, MACD, Momentum + bảng giá/độ sâu thị trường bên phải (từ SSI iBoard)
- Hình 2: Biểu đồ nến NGÀY (Daily) zoom ra 6-12 tháng — cùng bộ indicator, full screen
- Hình 3: NN mua ròng 10 phiên (từ SSI iBoard app) — bao gồm KL NN mua, KL NN bán, Room NN, biểu đồ cột NN mua ròng 10 phiên

THÔNG TIN BỔ SUNG (tùy chọn):

- Link 1: Báo cáo tài chính / KQKD (VD: https://finance.vietstock.vn/...)
- Link 2: Tin tức doanh nghiệp / ngành (VD: https://cafef.vn/...)
- Link 3: Thông báo CBTT quan trọng (nếu có)

(Nếu có link, tôi sẽ tự động đọc nội dung và phân tích kết hợp)

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
⚙️ BƯỚC 0 — ĐỌC LỊCH SỬ (LUÔN LÀM TRƯỚC KHI PHÂN TÍCH)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Trước khi bắt đầu phân tích, thực hiện các bước sau:

1. Xác định mã cổ phiếu từ input (VD: MWG)
2. Đọc file: stocks/[MÃ]/summary.json
   - Nếu file tồn tại và tong_phien > 0: lấy 3 phiên gần nhất từ mảng lich_su[]
   - Nếu file không tồn tại hoặc lich_su rỗng: ghi nhận "Đây là phiên đầu tiên theo dõi mã này"
3. Đọc file: stocks/[MÃ]/index.md
   - Lấy: thesis hiện tại, trạng thái vị thế, vùng giá quan trọng, sự kiện sắp tới

SAU KHI ĐỌC, IN RA PHẦN NÀY TRƯỚC TIÊN:

---
### 🔄 BỐI CẢNH LỊCH SỬ — [MÃ CP]

**Tổng phiên đã theo dõi:** X phiên | **Vị thế:** KHÔNG GIỮ / ĐANG GIỮ tại xxx

**3 phiên gần nhất:**
| Ngày | Giá đóng | Tín hiệu | MACD | NN ròng | Kết quả |
|------|----------|----------|------|---------|---------|
| (lấy từ summary.json) | | | | | |

**Thesis hiện tại:** (từ index.md)
**Invalidation cũ:** (từ index.md)

**So sánh với hôm nay:**
- Giá thay đổi: xxx → xxx (+/-x%)
- MACD: [giữ nguyên trend / đảo chiều / phân kỳ mới]
- NN: [tiếp tục mua ròng / đảo chiều / cạn room]
- Kịch bản phiên trước: [Tích cực / Sideway / Tiêu cực] — [XÁC NHẬN / BỊ VÔ HIỆU vì...]
- Thesis: [VẪN GIỮ NGUYÊN / CẦN CẬP NHẬT vì...]

*(Nếu chưa có lịch sử: "Đây là phiên đầu tiên — chưa có dữ liệu lịch sử để so sánh")*
---

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
QUY TẮC PHÂN TÍCH:
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

- Đọc toàn bộ chỉ báo từ hình: giá OHLC, MA, Ichimoku (Tenkan/Kijun/Cloud), Volume, BBW, Stoch RSI, MACD (line/signal/histogram), Momentum
- Đọc bảng giá: giá trần/sàn/tham chiếu, dư mua/bán, phân tích khối lượng theo giá
- Đọc dữ liệu NN từ hình 3: KL mua/bán ròng hôm nay, xu hướng NN 10 phiên, Room NN còn lại
- Đọc và phân tích thông tin từ link (nếu có): KQKD, tin tức, sự kiện
- Đưa ra chiến lược TỔNG HỢP cho CẢ HAI: T+2/T+3 VÀ trung hạn 2-4 tuần
- SL cứng: 5% từ giá mua | TP: 5-10% từ giá mua

TRẢ LỜI THEO CẤU TRÚC SAU:

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 A. ĐỌC DỮ LIỆU TỪ BIỂU ĐỒ
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Liệt kê tất cả số liệu đọc được từ hình:

- Giá: O / H / L / C, % thay đổi, trần / sàn / tham chiếu
- MA: MA9, các đường Ichimoku (Tenkan, Kijun, Senkou A, Senkou B)
- Volume phiên + Volume trung bình (đọc từ chart)
- BBW: giá trị, đang co (squeeze) hay mở rộng?
- Stoch RSI: %K, %D, vùng nào (quá mua >80 / quá bán <20 / trung tính)
- MACD: MACD line, Signal line, Histogram (dương/âm, đang mở/thu hẹp)
- Momentum: giá trị, trên/dưới đường 0
- Dư mua/bán trần (nếu đọc được từ bảng giá)
- NN: KL mua ròng hôm nay, xu hướng 10 phiên (đang tăng/giảm/đảo chiều), Room NN còn lại

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📈 B. PHÂN TÍCH KỸ THUẬT
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

1. XU HƯỚNG:
   - Ngắn hạn (1-5 phiên): [TĂNG / GIẢM / SIDEWAY] + lý do
   - Trung hạn (2-4 tuần): [TĂNG / GIẢM / SIDEWAY] + lý do

2. VỊ TRÍ GIÁ SO VỚI CÁC MA & ICHIMOKU:
   - Giá nằm trên/dưới MA nào?
   - Giá so với mây Ichimoku: trên mây / trong mây / dưới mây?
   - Tenkan cắt Kijun? (golden cross / dead cross / chưa)

3. VOLUME & DÒNG TIỀN:
   - So volume hôm nay vs trung bình: đột biến / bình thường / cạn?
   - Phân bổ volume theo giá (từ biểu đồ depth): tập trung vùng nào?
   - Dòng tiền đang vào hay ra? Tín hiệu gom/xả?

4. KHỐI NGOẠI (NN):
   - NN mua/bán ròng hôm nay bao nhiêu KL? Quy ra tỷ VNĐ?
   - Xu hướng NN 10 phiên: đang mua ròng liên tục / bán ròng / đảo chiều?
   - Room NN còn bao nhiêu? Có cạn room không?
   - NN đang gom hay xả? Phiên hôm nay có bất thường so với 10 phiên không?

5. CÁC CHỈ BÁO KỸ THUẬT:
   - Stoch RSI, MACD, BBW, Momentum (tóm gọn)

6. MẪU HÌNH NẾN & HỖ TRỢ/KHÁNG CỰ:
   - Pattern nến gần nhất
   - Hỗ trợ 1, 2 / Kháng cự 1, 2

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
💼 C. PHÂN TÍCH CƠ BẢN (nếu có link)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
(Nếu không có link → bỏ qua mục này)

### C1. KẾT QUẢ KINH DOANH (KQKD)

- Doanh thu quý gần nhất: tăng/giảm bao nhiêu % YoY, QoQ?
- Lợi nhuận sau thuế: tăng/giảm bao nhiêu % YoY, QoQ?
- EPS, P/E hiện tại: cao/thấp so với ngành?
- ROE, ROA, nợ/vốn: tốt/xấu/trung bình?
- Đánh giá: KQKD [TÍCH CỰC / TRUNG LẬP / TIÊU CỰC]

### C2. TIN TỨC & SỰ KIỆN

- Tin chính từ link: tóm tắt 2-3 câu
- Ảnh hưởng đến giá cổ phiếu: [TÍCH CỰC / TRUNG LẬP / TIÊU CỰC]
- Catalyst (động lực tăng trưởng): M&A / mở rộng / hợp đồng mới / chính sách...?

### C3. YẾU TỐ VĨ MÔ & NGÀNH

- Xu hướng ngành hiện tại: tăng trưởng / trì trệ / suy thoái?
- Chính sách ảnh hưởng: lãi suất, tỷ giá, thuế...?
- Vị thế doanh nghiệp trong ngành: dẫn đầu / top 3 / nhỏ?

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🔀 D. TỔNG HỢP KỸ THUẬT + CƠ BẢN
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

| Góc độ         | Tín hiệu                        | Lý do chính            |
| -------------- | ------------------------------- | ---------------------- |
| Kỹ thuật       | MUA / BÁN / TRUNG LẬP           | ... (từ mục B)         |
| Cơ bản         | MUA / BÁN / TRUNG LẬP           | ... (từ mục C, nếu có) |
| NN & Dòng tiền | TÍCH CỰC / TRUNG LẬP / TIÊU CỰC | ...                    |

### D1. PHÂN TÍCH SỰ PHÙ HỢP:

- Kỹ thuật + Cơ bản có đồng thuận không?
  → [ĐỒNG THUẬN MUA / ĐỒNG THUẬN BÁN / MÂU THUẪN]
- Nếu mâu thuẫn: yếu tố nào quan trọng hơn trong ngắn hạn? Trung hạn?

### D2. GIẢI THÍCH SỰ KIỆN BẤT THƯỜNG (nếu có):

- Phiên trần/sàn bất thường → do tin gì?
- Volume đột biến → do tin tức hay pump/dump?
- NN đảo chiều đột ngột → lý do?

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🎯 E. CHIẾN LƯỢC GIAO DỊCH TỔNG HỢP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

### E1. CHIẾN LƯỢC T+ (T+2 hoặc T+3)

- Có nên vào T+ không? [CÓ / KHÔNG / CHỜ]
- Nếu CÓ:
  | Mục | Chi tiết |
  |-----|----------|
  | Loại T+ đề xuất | T+2 hay T+3, lý do |
  | Vùng giá MUA | xxx - xxx |
  | Lệnh mua | ATO / LO / MP + lý do |
  | Thời điểm mua | Mở cửa / sáng / chiều / ATC |
  | Vùng giá BÁN (TP) | xxx - xxx (+x%) |
  | Lệnh bán | LO / ATC / MP + lý do |
  | SL nếu sai | xxx (-5%) |
  | Lệnh cắt lỗ | MP / ATO |
  | Rủi ro đặc biệt | Tin tức đảo chiều? Catalyst hết hiệu lực? |

### E2. CHIẾN LƯỢC TRUNG HẠN (2-4 tuần)

- Có nên vào trung hạn không? [CÓ / KHÔNG / CHỜ]
- Nếu CÓ:
  | Mục | Chi tiết |
  |-----|----------|
  | Vùng giá MUA | xxx - xxx |
  | Lệnh mua | ATO / LO / MP + lý do |
  | TP1 | xxx (+x%) — chốt bao nhiêu % vị thế |
  | TP2 | xxx (+x%) — chốt phần còn lại |
  | SL | xxx (-5%) |
  | Trailing stop | Có/Không, điều kiện dời SL |
  | Thời gian giữ dự kiến | x tuần |
  | Sự kiện cần theo dõi | KQKD quý tới, ĐHCĐ, chia cổ tức... |

### E3. KHUYẾN NGHỊ: NÊN CHỌN T+ HAY TRUNG HẠN?

- So sánh Risk:Reward của 2 chiến lược
- Yếu tố cơ bản hỗ trợ chiến lược nào?
- Chiến lược nào phù hợp hơn với tình hình hiện tại, lý do

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📉 F. 3 KỊCH BẢN SAU KHI MUA
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

KỊCH BẢN 1 — TÍCH CỰC (xác suất: x%):

- Giá hướng tới đâu? Dấu hiệu xác nhận?
- Catalyst tiếp theo để đẩy giá lên?
- TP1, TP2, lệnh bán, thời gian

KỊCH BẢN 2 — SIDEWAY (xác suất: x%):

- Giá dao động vùng nào?
- Chờ tin tức/sự kiện gì để breakout?
- Xử lý: giữ / bán 1 phần / mua thêm / chuyển sang T+?

KỊCH BẢN 3 — TIÊU CỰC (xác suất: x%):

- SL chạm ở giá nào?
- Dấu hiệu cảnh báo từ tin tức (trước khi chạm SL -5%)?
- Dấu hiệu kỹ thuật cắt lỗ sớm?

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
⚖️ G. ĐÁNH GIÁ TỔNG HỢP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
| Chỉ số | Giá trị |
|--------|---------|
| Tín hiệu KỸ THUẬT | MUA / BÁN / TRUNG LẬP |
| Tín hiệu CƠ BẢN | MUA / BÁN / TRUNG LẬP / KHÔNG CÓ DỮ LIỆU |
| Tín hiệu TỔNG HỢP | MUA / BÁN / TRUNG LẬP |
| Risk : Reward (T+) | x : x |
| Risk : Reward (trung hạn) | x : x |
| Độ tin cậy | CAO / TRUNG BÌNH / THẤP |
| Lý do chính ủng hộ | ... (kỹ thuật + cơ bản) |
| Rủi ro lớn nhất | ... (kỹ thuật + yếu tố bên ngoài) |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📋 H. TÓM TẮT NHANH
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
T+: [MUA/KHÔNG] | Vào: xxx | SL: xxx | TP: xxx | Lệnh: xx/xx | Tin cậy: x% | Catalyst: [xxx]
Trung hạn: [MUA/KHÔNG] | Vào: xxx | SL: xxx | TP1: xxx | TP2: xxx | Giữ: x tuần | Tin cậy: x% | Cơ bản: [TÍCH CỰC/TRUNG LẬP/TIÊU CỰC]

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
💾 BƯỚC CUỐI — GHI LỊCH SỬ (LUÔN LÀM SAU KHI PHÂN TÍCH XONG)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Sau khi hoàn thành phân tích A→H, thực hiện 3 thao tác ghi file sau:

### 1. Tạo file history ngày hôm nay
Tạo file mới: stocks/[MÃ]/history/[YYYY-MM-DD].md
Dùng template từ: stocks/_template/history/YYYY-MM-DD.md
Điền đầy đủ toàn bộ kết quả phân tích từ mục A đến H vào file này.
Phần "BỐI CẢNH TỪ PHIÊN TRƯỚC" điền từ dữ liệu đã đọc ở Bước 0.
Phần "KẾT QUẢ THỰC TẾ" để trống — người dùng điền sau khi lệnh kết thúc.

### 2. Cập nhật summary.json
Mở file stocks/[MÃ]/summary.json và:
- Tăng tong_phien lên 1
- Nếu theo_doi_tu là null: điền ngày hôm nay
- Thêm 1 object mới vào đầu mảng lich_su[] với toàn bộ dữ liệu số từ phân tích hôm nay:
  - Điền tất cả trường số: gia_close, volume, ma9, ma26, stoch_rsi, bbw, nn_rong, nn_room_pct, ho_tro_1/2, khang_cu_1/2
  - Điền các trường text: macd_trend, xu_huong_ngan_han, xu_huong_trung_han, tin_hieu_tong_hop
  - Điền chien_luoc_t_plus và chien_luoc_trung_han với giá vào/SL/TP/tin_cay
  - ket_qua: để null — người dùng điền sau
- Cập nhật vi_the_hien_tai nếu người dùng thông báo đã vào lệnh
- Tự động tính lại thong_ke.win_rate_pct nếu đủ dữ liệu ket_qua (đếm TP_DAT / tổng lệnh đã có kết quả)

### 3. Cập nhật index.md
Mở file stocks/[MÃ]/index.md và cập nhật:
- "Cập nhật lần cuối": ngày hôm nay
- "Tổng số phiên đã theo dõi": số mới
- Bảng "TRẠNG THÁI KỸ THUẬT GẦN NHẤT": thay bằng dữ liệu hôm nay
- Bảng "VÙNG GIÁ QUAN TRỌNG": cập nhật hỗ trợ/kháng cự mới
- Bảng "LỊCH SỬ TÓM TẮT": thêm dòng hôm nay vào đầu, giữ tối đa 5 dòng gần nhất
- Nếu thesis thay đổi: cập nhật mục THESIS ĐẦU TƯ HIỆN TẠI

Sau khi ghi xong, thông báo:
> ✅ Đã lưu phân tích vào stocks/[MÃ]/history/[YYYY-MM-DD].md
> ✅ Đã cập nhật stocks/[MÃ]/summary.json (tổng X phiên)
> ✅ Đã cập nhật stocks/[MÃ]/index.md
> 📌 Nhắc nhở: Sau khi lệnh kết thúc, hãy điền kết quả vào mục H (KẾT QUẢ THỰC TẾ) trong file history để tính win rate.
