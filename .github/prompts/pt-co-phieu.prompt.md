---
description: "Phân tích kỹ thuật cổ phiếu Việt Nam — T+2/T+3 và trung hạn 2-4 tuần. Gửi kèm 3 hình."
argument-hint: "Mã cổ phiếu (VD: MWG, FPT, VNM...)"
---

Phân tích kỹ thuật ${input}.

THỜI GIAN PHÂN TÍCH (BẮT BUỘC):

- Ghi rõ: **HH:MM DD/MM/YYYY (UTC+7)** tại thời điểm người dùng hỏi.
- Nếu người dùng không ghi thời gian, trợ lý phải tự lấy thời gian hệ thống hiện tại và nêu rõ trong phần mở đầu.
- Tất cả khuyến nghị phải bám theo thời điểm hỏi (trước phiên / trong phiên / sau phiên), không dùng một kịch bản chung cho mọi thời điểm.

HÌNH ẢNH ĐÍNH KÈM:

- Hình 1: Biểu đồ nến NGÀY (Daily) gần nhất (3 tháng) — hiển thị MA, Ichimoku, Volume, BBW, Stoch RSI, MACD, Momentum + bảng giá/độ sâu thị trường bên phải (từ SSI iBoard)
- Hình 2: Biểu đồ nến NGÀY (Daily) zoom ra 6-12 tháng — cùng bộ indicator, full screen
- Hình 3: NN mua ròng 10 phiên (từ SSI iBoard app) — bao gồm KL NN mua, KL NN bán, Room NN, biểu đồ cột NN mua ròng 10 phiên

QUY TẮC PHÂN TÍCH:

- Đọc toàn bộ chỉ báo từ hình: giá OHLC, MA, Ichimoku (Tenkan/Kijun/Cloud), Volume, BBW, Stoch RSI, MACD (line/signal/histogram), Momentum
- Đọc bảng giá: giá trần/sàn/tham chiếu, dư mua/bán, phân tích khối lượng theo giá
- Đọc dữ liệu NN từ hình 3: KL mua/bán ròng hôm nay, xu hướng NN 10 phiên, Room NN còn lại
- Phân tích thuần kỹ thuật, KHÔNG cần tin tức/cơ bản trừ khi tôi cung cấp
- Đưa ra chiến lược cho CẢ HAI: T+2 hoặc T+3 VÀ trung hạn 2-4 tuần
- SL cứng: 5% từ giá mua | TP: 5-10% từ giá mua
- BẮT BUỘC thêm logic theo khung giờ hỏi:
  - Nếu hỏi **trước 09:00**: đưa kế hoạch mở cửa (ATO/LO), vùng quan sát 15-30 phút đầu phiên.
  - Nếu hỏi **09:00-11:30 hoặc 13:00-14:45**: ưu tiên lệnh thực chiến trong phiên, nêu trigger vào/ra theo giá và khối lượng realtime.
  - Nếu hỏi **sau 14:45**: xây kế hoạch cho phiên kế tiếp (entry trigger, điều kiện hủy kịch bản, cách xử lý gap up/gap down).
  - Nếu hỏi **sau 22:00**: ưu tiên kế hoạch cho ngày mai + mức giá đặt sẵn đầu phiên.

TRẢ LỜI THEO CẤU TRÚC SAU:

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📊 A. ĐỌC DỮ LIỆU TỪ BIỂU ĐỒ
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
Liệt kê tất cả số liệu đọc được từ hình:

- Thời điểm hỏi: HH:MM DD/MM/YYYY (UTC+7)
- Trạng thái thị trường theo thời điểm hỏi: [Trước phiên / Trong phiên / Sau phiên]

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

5. STOCH RSI:
   - Giá trị hiện tại, vùng nào?
   - %K cắt %D chưa? Hướng cắt?
   - Đang phân kỳ (divergence) với giá không?

6. MACD:
   - MACD line vs Signal: đã cắt / sắp cắt / xa nhau?
   - Histogram: dương hay âm? Đang mở rộng hay thu hẹp?
   - Có phân kỳ (divergence) với giá không?

7. BOLLINGER BAND WIDTH (BBW):
   - Đang squeeze (co hẹp) hay expansion (mở rộng)?
   - Nếu squeeze → breakout tiềm năng hướng nào?

8. MOMENTUM:
   - Trên hay dưới đường 0?
   - Đang tăng hay giảm dần?

9. MẪU HÌNH NẾN (1-3 phiên gần nhất):
   - Có pattern nào? (Marubozu, Hammer, Engulfing, Doji, Harami, Morning/Evening Star...)
   - Ý nghĩa của pattern đó trong bối cảnh hiện tại?

10. HỖ TRỢ & KHÁNG CỰ:
    | Loại | Mức giá | Căn cứ (MA/Ichimoku/đáy-đỉnh cũ/fibo...) |
    |------|---------|-------------------------------------------|
    | Hỗ trợ 1 | xxx | ... |
    | Hỗ trợ 2 | xxx | ... |
    | Kháng cự 1 | xxx | ... |
    | Kháng cự 2 | xxx | ... |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
🎯 C. CHIẾN LƯỢC GIAO DỊCH
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

### C1. CHIẾN LƯỢC T+ (T+2 hoặc T+3)

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

### C2. CHIẾN LƯỢC TRUNG HẠN (2-4 tuần)

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

### C3. KHUYẾN NGHỊ: NÊN CHỌN T+ HAY TRUNG HẠN?

- So sánh Risk:Reward của 2 chiến lược
- Chiến lược nào phù hợp hơn với biểu đồ hiện tại, lý do

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📉 D. 3 KỊCH BẢN SAU KHI MUA
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

KỊCH BẢN 1 — TÍCH CỰC (xác suất: x%):

- Giá hướng tới đâu? Dấu hiệu xác nhận?
- TP1, TP2, lệnh bán, thời gian

KỊCH BẢN 2 — SIDEWAY (xác suất: x%):

- Giá dao động vùng nào?
- Xử lý: giữ / bán 1 phần / mua thêm / chuyển sang T+?

KỊCH BẢN 3 — TIÊU CỰC (xác suất: x%):

- SL chạm ở giá nào?
- Dấu hiệu cắt lỗ SỚM (dù chưa chạm SL -5%)?
  → VD: giá đóng dưới MA nào? Volume bán đột biến? MACD dead cross?

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
⚖️ E. ĐÁNH GIÁ TỔNG HỢP
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
| Chỉ số | Giá trị |
|--------|---------|
| Tín hiệu KỸ THUẬT tổng hợp | MUA / BÁN / TRUNG LẬP |
| Risk : Reward (T+) | x : x |
| Risk : Reward (trung hạn) | x : x |
| Độ tin cậy | CAO / TRUNG BÌNH / THẤP |
| Lý do chính ủng hộ | ... |
| Rủi ro lớn nhất | ... |

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
📋 F. TÓM TẮT NHANH
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
T+: [MUA/KHÔNG] | Vào: xxx | SL: xxx | TP: xxx | Lệnh mua: xx | Lệnh bán: xx | Tin cậy: x%
Trung hạn: [MUA/KHÔNG] | Vào: xxx | SL: xxx | TP1: xxx | TP2: xxx | Giữ: x tuần | Tin cậy: x%

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
💾 BƯỚC CUỐI — GHI LỊCH SỬ (LUÔN LÀM SAU KHI PHÂN TÍCH XONG)
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Sau khi hoàn thành phân tích A→H, thực hiện 3 thao tác ghi file sau:

### 1. Tạo file history ngày hôm nay

Tạo file mới: stocks/[MÃ]/history/[YYYY-MM-DD].md
Dùng template từ: stocks/\_template/history/YYYY-MM-DD.md
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
