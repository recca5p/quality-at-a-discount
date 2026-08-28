---
name: Quality-at-a-Discount
description: >-
  Use this whenever the user wants long-term accumulation (tích sản): screen or
  analyze stocks, ETFs, or real-asset ballast for a quality business that is
  hard to replace and currently on a true sale-off. Auto-detect market from the
  question (VN, US, UK, DE, AU, or mixed). Run the full 10-agent committee, not
  a shortcut. Includes AI/semiconductor cycle overlay and gold/metals/fertilizer/oil
  fallback. Valid output is zero names. Never pick a ticker to complete the answer.
---

# Quality-at-a-Discount

Một skill. Thị trường là **biến** (`MARKET`), không phải playbook khác. Cốt lõi không đổi: **doanh nghiệp tốt, khó thay thế, giá đang sale-off thật, nắm dài để tích sản.**

Kết luận hợp lệ có thể là không có gì đáng mua. Không được chọn mã chỉ để hoàn thành câu trả lời. Không được nhảy thị trường khác chỉ vì thị trường nhà đang giá hợp lý.

Chạy **toàn bộ** hệ thống 10 agent dưới đây. Không rút thành “PE thấp + ROE cao”. Bản rút gọn là sai skill này.

---

## 0. Router (chạy trước, mọi lần)

### 0.1 `MARKET`

Đọc câu hỏi, mã, sàn. Gán một `MARKET` chính (hoặc list nếu họ nêu nhiều). Đừng hỏi nếu đã rõ.

| Tín hiệu | MARKET |
|---|---|
| VNIndex, HOSE, HNX, UPCOM, tên Việt, FPT/MBB/HPG, “cổ phiếu Việt” | `VN` |
| NYSE, Nasdaq, S&P, US 10Y, “cổ Mỹ”, NVDA/AAPL/BRK, 10-K | `US` |
| FTSE, LSE, AIM, gilt, “cổ Anh”, SHEL/ULVR/AZN | `UK` |
| DAX, Xetra, Frankfurt, Bund, “cổ Đức/Âu”, SAP/SIE/ALV; Euro-core NL/FR/CH nếu họ gắn với Đức/Âu | `DE` |
| ASX, “cổ Úc”, BHP/CBA/WOW, RBA, franking | `AU` |
| “quốc tế / developed / ra nước ngoài” không chỉ nước | Screen `US` trước, rồi `UK`/`DE`/`AU` chỉ khi US trống hoặc họ nêu tên |
| Vàng, bạc, dầu, phân bón, kim loại, “ETF hàng hóa”, hoặc rổ cổ phiếu trống | `MODE=REAL_ASSETS` (vẫn ghi MARKET cho đồng niêm yết) |

Ticker thắng: FPT=`VN`, NVDA=`US`. Mua niêm yết nào thì dùng pack niêm yết đó.

### 0.2 `MODE`

| MODE | Khi nào |
|---|---|
| `EQUITY` | Mặc định. Cổ phiếu / ETF cổ phiếu của doanh nghiệp. |
| `AI_OVERLAY` | GPU, bán dẫn, foundry, thiết bị wafer, HBM/memory, EDA, hoặc hyperscaler mà luận điểm là capex AI. Chạy **§11 trước khi chấm định giá**. Hard-fail overlay chặn Accumulate / Strong buy. |
| `REAL_ASSETS` | Họ xin vàng/bạc/kim loại/phân bón/dầu, hoặc `EQUITY` không ra mã nào đáng mua. Chạy §12. Không nới tiêu chí cổ phiếu để tránh mode này. |

Một mã có thể `EQUITY` + `AI_OVERLAY`. Một screen có thể kết thúc `REAL_ASSETS`.

### 0.3 Hurdle (gắn MARKET)

So earnings yield và FCF yield với **cột này**, không với cảm giác.

| MARKET | Phi rủi ro | Ghi chú |
|---|---|---|
| VN | Lãi gửi 12 tháng big-4 VND (và 10y VGB nếu hữu ích) | Cổ phiếu thưởng và ESOP mệnh giá không phải yield |
| US | 10-year UST | FCF **sau SBC** |
| UK | 10-year gilt | Cộng stamp 0.5% vào MOS |
| DE | 10-year Bund | IFRS, quỹ hưu trí, chu kỳ xuất khẩu |
| AU | 10-year ACGB | Bỏ franking với nhà đầu tư không cư trú |

### 0.4 Horizon

Mặc định **tích sản nhiều năm** (3–10 năm). Nếu họ nói 1–2 năm, đó là **sàn** nắm giữ, không phải cửa sổ giao dịch.

---

## 1. Nhiệm vụ

Tìm tài sản (cổ phiếu, khi rổ trống thì real-asset ballast) thỏa **đồng thời**:

1. Doanh nghiệp có chất lượng nội tại cao, khó thay thế.
2. Giá thị trường thấp hơn đáng kể so với giá trị nội tại hợp lý (sale-off thật).

Không nhầm lẫn giữa:

- Công ty tốt và cổ phiếu đáng mua.
- Giá giảm và giá rẻ.
- P/E thấp và định giá hấp dẫn.
- Tăng trưởng doanh thu và tăng trưởng tạo giá trị cho cổ đông.
- Lợi nhuận kế toán và tiền mặt thực sự tạo ra.
- Cổ phiếu thưởng / split và giá trị mới được tạo ra.
- Buyback và tạo giá trị (mua lại **trên** giá trị nội tại là phá giá trị).
- SBC / ESOP “phi tiền” và pha loãng kinh tế thật.
- Thành viên chỉ số, Mag-7, “AI winner”, nâng hạng FTSE/MSCI và moat bền.
- Upside chu kỳ và lợi thế cạnh tranh bền vững.
- Thị trường phát triển và cổ phiếu an toàn hơn (vốn chuyên nghiệp hơn → **rẻ rõ** hiếm hơn).

Kết luận hợp lệ:

- Không có cổ phiếu nào đủ tốt để mua tại giá hiện tại.
- Không được cố chọn mã chỉ để hoàn thành câu trả lời.

Mục tiêu không phải tìm nhiều mã. Mục tiêu là chờ đúng doanh nghiệp, đúng mức giá, đúng bất đối xứng lợi nhuận/rủi ro, để tích sản dài hạn.

---

## 2. Chuẩn thu thập dữ liệu

Mỗi phân tích đầy đủ cần khoảng **6–12 tài liệu nguồn**, tối thiểu:

- Báo cáo tài chính hoặc báo cáo thường niên chính thức (10-K / 20-F / BCTC / Geschäftsbericht / annual report).
- Công bố doanh nghiệp, nghị quyết, tài liệu ĐHĐCĐ / proxy DEF 14A, IR.
- Dữ liệu sở giao dịch, cơ quan quản lý hoặc thống kê.
- Báo cáo ngành hoặc phân tích độc lập.
- Giá, số cổ phiếu pha loãng hoàn toàn, corporate action **mới nhất**.
- Báo chí uy tín chỉ để xác minh sự kiện đặc biệt.

**Theo MARKET:**

- `VN` — BCTC/BCTN, SSC, HOSE/HNX/UPCOM, nghị quyết; CafeF/Vietstock/Simplize chỉ để **tìm** filing, không phải nguồn cuối.
- `US` — 10-K, 10-Q, 8-K, DEF 14A, Form 4.
- `UK` — annual report + RNS.
- `DE` — Geschäftsbericht, BaFin / Bundesanzeiger.
- `AU` — annual report + ASX filings.

Thông tin nhân viên, khách hàng, nhà cung cấp, diễn đàn, mạng xã hội = **tín hiệu điều tra**, không tự động là sự thật. Phải tìm chỉ số tài chính xác nhận hoặc bác bỏ.

Ví dụ:

- Nhân viên nói workload tăng → doanh thu/nhân viên, số nhân sự, biên, attrition, chi phí nhân sự.
- Công ty nói đơn hàng tăng → phải thu, tiền khách trả trước, dòng tiền kinh doanh.
- Ngân hàng nói tín dụng tăng tốt → nợ nhóm 2, NPL, dự phòng, tăng trưởng huy động, NIM.
- “AI demand exploding” → capex vs khấu hao của khách, RPO/backlog có hủy được không, tập trung khách, deferred revenue, cam kết GPU/lease.

Mọi giá mục tiêu phải dùng giá, số cổ phiếu pha loãng hoàn toàn, và corporate action mới nhất. Không dùng giá trước chia thưởng để so với EPS sau pha loãng.

Pha loãng hoàn toàn gồm: quyền chọn, RSU/PSU, trái phiếu chuyển đổi, ESOP, quyền mua, cổ phiếu thưởng/pending rights.

Điều chỉnh dữ liệu cho: cổ phiếu thưởng, chia tách, phát hành quyền, ESOP/SBC, lợi nhuận bất thường, đổi phương pháp hợp nhất, M&A/thoái vốn công ty con, restatement.

---

## 3. Hệ thống 10 agent (bắt buộc, không bỏ bước)

Không được trung bình hóa ý kiến. Phải xác định dữ liệu nào quan trọng nhất và xung đột nào chưa giải quyết.

### Agent 1 — Data & Filings

Thu thập và chuẩn hóa:

- Giá hiện tại (đồng niêm yết).
- Số cổ phiếu lưu hành pha loãng hoàn toàn.
- Vốn hóa, EV (gồm lease, quỹ hưu trí unfunded), giá trị sổ sách / tangible book.
- Doanh thu, lợi nhuận, CFO, FCF, SBC **tối thiểu 5 năm** nếu có (10 năm tốt hơn với chu kỳ).
- Nợ, tiền mặt, capex bảo trì vs tăng trưởng, phải thu, tồn kho, deferred revenue.
- ESOP / RSU / quyền mua / phát hành riêng lẻ / buyback authorization.
- Giao dịch cổ đông lớn, bên liên quan, Form 4 / PDMR / substantial holder.
- Kết quả quý gần nhất và so sánh cùng kỳ, và so 8 quý nếu chu kỳ.

### Agent 2 — Business Quality & Moat

Đánh giá:

- Công ty thực sự kiếm tiền từ đâu.
- Tỷ trọng doanh thu và lợi nhuận từng mảng.
- Doanh thu định kỳ hay phải bán lại từ đầu mỗi kỳ.
- Khách hàng có dễ thay nhà cung cấp không.
- Thương hiệu, mạng lưới, giấy phép, dữ liệu, quy mô, chi phí thấp, công nghệ độc quyền.
- Khách hàng hoặc nhà cung cấp có quá tập trung không.
- Sản phẩm có nguy cơ bị AI, tự động hóa, công nghệ mới, hàng nhập, hoặc chính sách thay thế không.
- Lợi thế đến từ năng suất thật hay chỉ từ nhân công giá rẻ, đất rẻ, tín dụng rẻ, hoặc capex của khách.
- Moat mạnh hơn, giữ nguyên, hay yếu đi trong 3–5 năm (với tích sản: nhìn 5–10 năm).

Không được gọi một doanh nghiệp là “công nghệ” hoặc “AI stock” chỉ vì dùng AI. Phải xếp:

- Sở hữu sản phẩm / IP.
- Bán dịch vụ triển khai.
- Outsourcing / body-shopping.
- Nhà phân phối.
- Chỉ đang dùng AI để giảm chi phí.

### Agent 3 — Earnings & Cash-Flow Quality

Với doanh nghiệp **phi tài chính**:

- CFO / lợi nhuận sau thuế 3–5 năm (tốt hơn 5–10).
- FCF sau capex duy trì, **sau SBC** (SBC là tiền, không phải “phi tiền”).
- Phải thu tăng nhanh hơn doanh thu không.
- Tồn kho tăng nhanh hơn sản lượng hoặc doanh thu không.
- Lợi nhuận có đến từ đánh giá lại tài sản, thoái vốn, hoàn nhập, hay khoản bất thường không.
- Biên thay đổi do năng suất hay trì hoãn chi phí.
- Capex duy trì vs capex tăng trưởng.
- Dòng tiền cổ tức từ công ty liên kết có thực sự về công ty mẹ không.
- EPS có tăng nhanh hơn số cổ phiếu không.

Doanh nghiệp tăng lợi nhuận nhưng liên tục CFO yếu, phải thu phình, vay để trả cổ tức, hoặc phát hành để tài trợ hoạt động → **không** có dòng tiền bền vững.

**Ngân hàng:** không dùng CFO/FCF như doanh nghiệp thường. Sang module ngân hàng.

### Agent 4 — Balance Sheet & Survivability

- Nợ ròng / EBITDA trên lãi **giữa chu kỳ**.
- Khả năng trả lãi.
- Cơ cấu nợ ngắn / dài, lịch đáo hạn, covenant.
- Tài sản bảo đảm, nghĩa vụ ngoài bảng, lease, quỹ hưu trí.
- Bảo lãnh bên liên quan, rủi ro tỷ giá.
- Khả năng tồn tại khi doanh thu hoặc biên giảm mạnh (kể cả recession tại MARKET đó).

Cổ phiếu chỉ là sale-off thật khi doanh nghiệp đủ sức sống qua giai đoạn thị trường định giá sai.

### Agent 5 — Governance, Dilution & Capital Allocation

- Lịch sử ESOP / RSU và **pha loãng kinh tế trung bình mỗi năm** (không chỉ số cổ phiếu).
- Giá ESOP / strike RSU so với thị giá.
- Thời gian khóa.
- Phát hành riêng lẻ cho ai, vì mục đích gì.
- Mua bán tài sản với bên liên quan.
- Lương thưởng lãnh đạo so với lợi ích cổ đông (DEF 14A / tờ trình ĐHĐCĐ).
- Cổ tức có bền vững từ FCF không.
- Tiền giữ lại tái đầu tư với ROIC bao nhiêu.
- Ban lãnh đạo mua lại khi rẻ hay phát hành khi rẻ. Buyback trên giá trị nội tại = phá giá trị.
- Tăng trưởng EPS sau pha loãng.

Cổ phiếu thưởng cho tất cả cổ đông **không** phải lợi nhuận hoặc giá trị mới.

Phiên bản thị trường phát triển của ESOP mệnh giá Việt Nam: **RSU rẻ + buyback vừa đủ bù pha loãng = net shrink bằng 0**.

### Agent 6 — Sector & Macro

- Chu kỳ ngành đang đáy, giữa, hay đỉnh.
- Tăng trưởng từ nhu cầu thật hay tín dụng / fiscal.
- Chính sách hỗ trợ có bền vững không.
- Lãi suất, tỷ giá, CPI, giá nguyên liệu.
- Doanh nghiệp hưởng lợi trực tiếp hay chỉ được gắn câu chuyện.
- Chính sách mới tạo thêm lợi nhuận hay chỉ tăng doanh thu biên thấp.
- Cạnh tranh mới, hàng nhập, công nghệ, quy định có đổi economics ngành không.

Không lấy GDP cao làm bằng chứng mọi ngân hàng, thép, BĐS, bán lẻ, hay Mag-7 đều đáng mua.

### Agent 7 — Valuation & Margin of Safety

Tối thiểu **hai** phương pháp phù hợp:

- P/E trên lợi nhuận **chuẩn hóa**.
- P/B kết hợp ROE bền vững với ngân hàng.
- EV/EBIT hoặc EV/EBITDA giữa chu kỳ.
- FCF yield trên owner earnings (sau SBC, capex duy trì).
- DCF với ROIC fading.
- Sum-of-the-parts.
- NAV với tài sản / BĐS / REIT.
- Định giá giữa chu kỳ với thép, hàng hóa, chứng khoán, dầu, phân bón.
- Reverse DCF: giá hiện tại đang đòi hỏi tăng trưởng / ROIC bao nhiêu, so với hurdle của MARKET.

So sánh với: lịch sử chính doanh nghiệp, doanh nghiệp tương đồng, chất lượng và tăng trưởng thực, **lãi suất và chi phí vốn hiện tại của MARKET đó**.

Kịch bản xấu / cơ sở / tốt. Trả lời rõ:

- Giá giảm vì tâm lý hay nội tại suy?
- Lợi nhuận chuẩn hóa có giữ được không?
- Bảng cân đối có đủ sức chờ thị trường sửa sai không?
- Giá đã phản ánh bao nhiêu phần kịch bản xấu?
- Upside cơ sở có đủ lớn so với downside không? (tích sản: base upside nên ≥ ~2× downside thực tế trên 3–5 năm)

### Agent 8 — Red Team / Value-Trap Hunter

Phản bác luận điểm mua. Phải tìm:

- Suy giảm cấu trúc bị che bởi tăng trưởng ngắn hạn.
- Doanh thu tăng nhưng biên và dòng tiền giảm.
- Lợi nhuận tăng nhờ dự phòng thấp hoặc khoản bất thường.
- Mô hình phụ thuộc tín dụng rẻ, đất, chính sách, một khách hàng lớn, hoặc capex của hyperscaler.
- Công nghệ mới (kể cả AI) ép giá hoặc thay thế lao động.
- Ban lãnh đạo pha loãng để đạt mục tiêu tăng trưởng.
- Doanh nghiệp tốt nhưng giá vẫn quá cao.
- Cổ phiếu rẻ vì earnings đang đỉnh chu kỳ.
- Catalyst đã phản ánh hết vào giá.

Red Team bắt buộc:

- Ít nhất **ba** lý do luận điểm có thể sai.
- Một kịch bản giá **−25% đến −40%**.
- Các chỉ số cần theo dõi để phát hiện luận điểm đang hỏng.

### Agent 9 — Portfolio & Entry

Sau khi vượt các vòng trên:

- Core holding, cyclical, tactical, hay tránh.
- Tỷ trọng tối đa.
- Giải ngân ngay bao nhiêu.
- Giá rất tốt / giá tốt / giá hợp lý / giá bắt đầu đắt — **đồng niêm yết**, đã điều chỉnh cổ tức cổ phiếu, quyền, cổ phiếu mới.
- Điều kiện mua thêm.
- Điều kiện **không được** bình quân giá xuống.
- Điều kiện giảm hoặc thoát.

Không dùng một tỷ trọng cố định cho mọi mã. Tỷ trọng phụ thuộc: độ chắc nội tại, biên an toàn, đòn bẩy, tính chu kỳ, thanh khoản, FX, tương quan với vị thế đang có. Mega-cap đã chiếm lớn trong chỉ số thế giới là **kém** đa dạng hóa hơn vẻ ngoài.

### Agent 10 — Investment Committee

Tổng hợp. Không trung bình hóa. Chỉ ra dữ liệu quan trọng nhất và xung đột chưa giải quyết.

Kết luận **bắt buộc** một trong:

- Mua mạnh (Strong buy)
- Mua tích lũy (Accumulate)
- Mở vị thế thăm dò (Probe)
- Giữ nhưng không mua thêm (Hold no add)
- Theo dõi, chờ giá (Watch wait for price)
- Tránh do định giá (Avoid on valuation)
- Tránh do nội tại (Avoid on quality)
- Chỉ phù hợp giao dịch chu kỳ (Cycle-trade only)

Nếu `AI_OVERLAY` hard-fail: không được Strong buy / Accumulate.

---

## 4. Thang điểm 100

| Nhóm tiêu chí | Trọng số |
|---|---|
| Chất lượng mô hình và moat | 20 |
| Tăng trưởng và unit economics | 10 |
| Chất lượng lợi nhuận và dòng tiền | 15 |
| Bảng cân đối và khả năng sống qua chu kỳ | 10 |
| Quản trị, phân bổ vốn và pha loãng | 10 |
| Định giá và biên an toàn | **25** |
| Catalyst | 5 |
| Bất đối xứng rủi ro / lợi nhuận | 5 |
| **Tổng** | **100** |

**Tier**

- **S** — Mua mạnh: chất lượng cao, chiết khấu sâu, bear case đã được phản ánh đáng kể.
- **A** — Mua tích lũy: chất lượng tốt, giá hấp dẫn, còn rủi ro cần theo dõi.
- **B** — Watchlist: doanh nghiệp tốt nhưng giá chưa đủ hời hoặc luận điểm cần xác nhận.
- **C** — Tactical: định giá/catalyst hấp dẫn nhưng chu kỳ, đòn bẩy, hoặc chất lượng dòng tiền không phù hợp core.
- **D** — Avoid: value trap, quản trị yếu, bảng cân đối rủi ro, hoặc không có biên an toàn.

Điểm số không được dùng để che **hard fail**. Quản trị nghiêm trọng hoặc nguy cơ thanh khoản vẫn loại dù điểm định lượng cao.

---

## 5. Điều kiện loại trực tiếp

Không đề xuất mua mạnh / tích lũy nếu **một** trong các tình huống:

- Ý kiến kiểm toán đáng lo, material weakness, restatement lặp, hoặc chất lượng công bố thấp.
- Lợi nhuận phụ thuộc lớn vào khoản bất thường.
- CFO / FCF yếu kéo dài mà không có giải thích hợp lý (phi ngân hàng).
- Nợ ngắn hạn hoặc thanh khoản có nguy cơ; maturity wall không trả được trong bear.
- Giao dịch bên liên quan thiếu minh bạch.
- Pha loãng lặp lại nhưng ROIC không cải thiện (ESOP mệnh giá, RSU + buyback bù, rights).
- Ngành đang suy giảm cấu trúc.
- Giá hiện tại cần một kịch bản hoàn hảo mới hợp lý.
- Không xác định được giá trị nội tại với độ tin cậy tối thiểu.
- Downside thực tế lớn hơn (hoặc không nhỏ hơn) upside cơ sở.
- Reverse DCF đòi tăng trưởng doanh nghiệp chưa từng kiếm được xuyên suốt một chu kỳ đầy đủ.
- `AI_OVERLAY` hard-fail.

---

## 6. Module riêng theo ngành

### Ngân hàng

Không dùng CFO/FCF như doanh nghiệp thường. Phải kiểm tra:

- P/B và ROE bền vững so với COE.
- NIM và chi phí vốn / deposit beta.
- CASA.
- Nợ nhóm 2 (IFRS stage-2) / classified loans (US).
- NPL, tỷ lệ bao phủ / LLR, credit cost / NCO.
- CAR / CET1 / AT1.
- LDR, tăng trưởng tín dụng so với huy động.
- Tập trung BĐS, xây dựng, trái phiếu, CRE.
- Cho vay bên liên quan.
- Cơ cấu tài sản bảo đảm.
- Chất lượng lợi nhuận từ bancassurance, chứng khoán, hoàn nhập, trading/AOCI.
- `US` thêm: HTM vs AFS, AOCI hole.
- `AU` thêm: nhà ở, APRA — không copy rule NPL Việt Nam.
- `VN` thêm: room tín dụng, recap/cổ tức cổ phiếu, SOE policy lending.

### Công nghệ, outsourcing, phần mềm

- Booking và doanh thu ký mới; tỷ lệ chuyển thành doanh thu và tiền mặt.
- Doanh thu trên nhân viên, headcount, utilization, attrition.
- Biên theo mảng; phải thu.
- Tỷ trọng sản phẩm/IP so với dịch vụ nhân công.
- AI tăng năng suất cho doanh nghiệp hay để khách ép giá.
- Khả năng thay thế nhân lực và commoditization.
- Phụ thuộc một thị trường hoặc khách lớn.
- Phần mềm: FCF sau SBC, net revenue retention. Rule of 40 là marketing.
- `VN` FPT/CMG = IT services / SI / viễn thông, **không** phải cổ phiếu AI.

### Bán dẫn, foundry, thiết bị, hyperscaler AI capex

Dừng. Chạy **§11**. Không định giá bằng LTM đỉnh.

### Thép, hàng hóa, công nghiệp nặng, hóa chất

Dùng lợi nhuận **giữa chu kỳ**, không lấy đỉnh:

- Công suất và tỷ lệ sử dụng, cost curve.
- Giá nguyên liệu, giá bán, spread.
- Capex, nợ, FCF sau khi dự án mới hoạt động.
- Phòng vệ thương mại, nhu cầu xây dựng thật, dư cung.

### Hàng tiêu dùng / bán lẻ

- Thị phần và thương hiệu, mạng lưới phân phối.
- Tăng trưởng sản lượng so với tăng giá.
- Gross margin, chi phí quảng cáo.
- Working capital.
- Khả năng tăng giá mà không mất khách.
- Dòng tiền và cổ tức.
- Rủi ro thị trường trưởng thành, private label, online.

### Bất động sản / REIT

- Pháp lý từng dự án (`VN`).
- Presales và tiền thu thật, tiến độ bàn giao.
- NAV có thể chuyển thành tiền.
- Nợ, trái phiếu, lãi vốn hóa, nghĩa vụ nhà thầu.
- Giao dịch bên liên quan, phụ thuộc tăng giá đất.
- Pha loãng và huy động vốn.
- REIT phát triển: LTV, refi wall, occupancy, rent vs lạm phát. Yield cao vẫn có thể là trap.

### Chứng khoán / broker

- Tỷ trọng môi giới, margin, tự doanh.
- Chất lượng danh mục tự doanh, chi phí vốn, VCSH.
- Chu kỳ thanh khoản thị trường.
- Lợi nhuận chuẩn hóa qua nhiều chu kỳ.
- Pha loãng để tăng vốn.
- Không định giá bằng một quý giao dịch bùng nổ.

---

## 7. Cách xác định sale-off thật

### Sale-off thật

- Giá giảm mạnh nhưng earning power dài hạn còn nguyên.
- Dòng tiền và bảng cân đối vẫn khỏe.
- Vấn đề hiện tại tạm thời hoặc đã bị định giá quá mức.
- Định giá thấp hơn lịch sử hợp lý **và** thấp hơn giá trị nội tại.
- Không cần giả định quá lạc quan để có upside.
- Bear case vẫn có mức mất vốn chấp nhận được.

### Giá giảm nhưng chưa rẻ

- Cổ phiếu trước đó quá đắt (40x còn 28x).
- P/E / P/B / FCF yield vẫn chưa hấp dẫn so với hurdle MARKET.
- Giá trị nội tại đang giảm cùng giá.
- Mag-7 giảm 15–20% từ ATH thường là nhóm này.
- FPT −34% từ PE 19–31x là nhóm này, không phải khủng hoảng 2022.

### Value trap

- Doanh thu hoặc lợi nhuận đang đỉnh chu kỳ.
- Dòng tiền yếu, nợ cao.
- Ngành bị thay thế (kể cả AI).
- Quản trị hoặc pha loãng bất lợi.
- Giá rẻ nhưng không có cơ chế tạo giá trị cho cổ đông.
- Catalyst chỉ là kỳ vọng chung của thị trường.

Thị trường phát triển hiếm khi cho bội số khủng hoảng trên doanh nghiệp pháo đài. Chiết khấu 20–30% so với giá trị thận trọng trên compounder chất lượng **có thể** đủ nếu bear bị chặn. Dip 10% trên “AI winner” thì không.

---

## 8. Mẫu đầu ra bắt buộc (mỗi mã)

1. **Verdict một câu** + `MARKET` + `MODE`. Ví dụ: *Doanh nghiệp tốt nhưng chưa đủ rẻ. / Doanh nghiệp trung bình đang có giá rẻ giả. / Doanh nghiệp tốt đang sale-off thật. / Cơ hội chu kỳ, không phải core.*
2. **Tier** S/A/B/C/D, điểm tổng, điểm từng nhóm.
3. **Luận điểm mua** — 3 đến 5 động lực thật.
4. **Moat và nguy cơ bị thay thế** — moat từ đâu, đang mạnh lên hay yếu đi, AI làm gì.
5. **Chất lượng tài chính** — doanh thu, lợi nhuận, biên, CFO/FCF hoặc chỉ số ngành, nợ và thanh khoản, phải thu/tồn kho, chất lượng lợi nhuận.
6. **Pha loãng và quản trị** — tính mức pha loãng kinh tế thật, không liệt kê cho có.
7. **Định giá** — giá hiện tại; FV bear/base/bull; upside/downside; định giá lịch sử; so sánh; reverse DCF vs hurdle MARKET.
8. **Kết luận sale-off** — một trong: Sale-off thật / Hấp dẫn vừa phải / Giá hợp lý / Chưa rẻ / Value trap tiềm năng.
9. **Vùng giá** (đã điều chỉnh cổ tức cổ phiếu, quyền, cổ phiếu mới): rất tốt / tốt / hợp lý / đắt.
10. **Thesis breakers** — số liệu cụ thể khiến luận điểm hỏng.
11. **Hành động** — mua bao nhiêu % vị thế; có cần chờ báo cáo mới không; mua thêm khi nào; **không** bình quân xuống khi nào; thời gian nắm; ghi chú FX.

Dòng committee bắt buộc: Strong buy / Accumulate / Probe / Hold no add / Watch wait for price / Avoid on valuation / Avoid on quality / Cycle-trade only.

Nếu cả rổ trống: nói thẳng, rồi cash hoặc §12. Không nhồi trang.

---

## 9. Nguyên tắc cuối cùng

- Không mua chỉ vì thuộc danh sách nâng hạng.
- Không mua chỉ vì P/E thấp.
- Không mua chỉ vì lợi nhuận quý tăng mạnh.
- Không mua chỉ vì ban lãnh đạo kể câu chuyện lớn (kể cả AI).
- Không lấy target price công ty chứng khoán / Street làm giá trị nội tại.
- Không bỏ qua pha loãng (ESOP, RSU, rights, bonus).
- Không bỏ qua dòng tiền.
- Không coi GDP cao là bảo đảm lợi nhuận cổ đông.
- Không coi thị trường “phát triển / lão luyện” là lý do mua.
- Không coi giá giảm là cơ hội khi mô hình đang suy giảm cấu trúc.
- Không ngại kết luận nên giữ tiền, T-bill, hoặc real-asset ballast.

---

## 10. MARKET packs (áp đúng hàng)

### VN

Filing tiếng Việt, HOSE/HNX/UPCOM. **Cổ phiếu thưởng không phải giá trị** — luôn split-adjust. ESOP mệnh giá là pha loãng kinh tế thật. Ngân hàng: P/B + ROE bền vững, không CFO. BĐS: mặc định tránh trừ khi pháp lý từng dự án + tiền thu thật + NAV-to-cash được tài liệu hóa. CTCK: không định giá một quý bùng nổ. Thép/phân bón: giữa chu kỳ, không H1 đỉnh. FPT/CMG = outsourcing/SI/viễn thông, không phải cổ phiếu AI. Nâng hạng FTSE/MSCI không phải luận điểm. Hurdle: lãi gửi 12 tháng.

### US

10-K/Q, DEF 14A, Form 4. Dilution = RSU + option + convertible. Buyback yield ≈ SBC ⇒ **net shrink = 0**. Ngân hàng: CET1, NCO, AOCI, HTM vs AFS, deposit beta. Energy/materials: strip giữa chu kỳ. Software: FCF sau SBC. Không coi S&P/QQQ/Mag-7 là chất lượng. Sân săn khi chỉ số tập trung: equal-weight, cash compounder bị bỏ quên. Mag-7 −15–20% thường là *down but not cheap*. Hurdle: UST 10y. SBC là analog của ESOP mệnh giá.

### UK

RNS + annual report. Stamp 0.5% là chi phí khứ hồi — nhét vào MOS. FTSE 100 là dầu, miner, ngân hàng, pharma, luxury **toàn cầu**, không phải “nền kinh tế Anh.” Pension deficit, IFRS 16, cổ tức sau capex duy trì (HĐQT Anh dễ over-distribute). GBP yếu là thuận nếu họ kiếm tiền ở nước ngoài.

### DE (Euro-core được)

Geschäftsbericht. Auto và hóa chất: giữa chu kỳ + China-bear. Dual-class gia đình là haircut, không auto-fail. Giá điện / chính sách năng lượng có thể đổi unit economics trước khi P&L hiện. SAP-class software vẫn cần MOS so với peer Mỹ. Hurdle: Bund 10y.

### AU

ASX filings. Big-4 ngân hàng + BHP/RIO chiếm sàn. **Franking vô giá trị với nhà đầu tư nước ngoài** — không trả thêm cho franking. Sắt/than/lithium: nhu cầu Trung Quốc giữa chu kỳ. AUD là currency hàng hóa; miner là cược Trung Quốc có đòn bẩy. Ngân hàng: giá nhà + APRA. Hurdle: ACGB 10y.

Với người tích sản gốc VND: báo cáo giá local, rồi USD và VND xấp xỉ. USD cash là lựa chọn thật. Miner Úc = equity + commodity + FX + Trung Quốc.

---

## 11. Overlay AI / bán dẫn (`MODE=AI_OVERLAY`)

AI là thật. **Giá hạ tầng AI thường là chu kỳ.** Không mua theme. Xếp loại, rồi hỏi earnings hôm nay có đang giả định peak capex mãi không.

### 11.1 Xếp bucket (bắt buộc, một bucket)

1. Vendor accelerator / GPU / custom silicon (CUDA lock-in, tập trung 4–5 hyperscaler).
2. Foundry (process lead, utilization, capex, địa chính trị).
3. Thiết bị wafer / EDA (độc quyền EUV vs etch/deposition/test chu kỳ hơn).
4. Memory (HBM vs DRAM/NAND thường — HBM vẫn chu kỳ).
5. Hyperscaler (MSFT, GOOGL, AMZN, META, Oracle): AI là **capex và khấu hao** trên core ads/cloud/retail. Tách core khỏi spend AI.
6. Application software / “AI feature” — thường không phải chu kỳ silicon. AI tăng willingness-to-pay hay chỉ tăng opex và bị copy 12 tháng? Phần lớn fail QAD vì định giá, không vì wafer.
7. Power, cooling, networking, OSAT, materials — picks-and-shovels, vẫn có mid-cycle riêng.

Nếu 10-K chỉ “dùng AI nội bộ”, overlay này tùy chọn; chấm như doanh nghiệp thường.

### 11.2 Bubble vs cycle vs franchise

- **Franchise:** process lead, độc quyền EUV, CUDA installed base, trust foundry. Vẫn có thể **quá đắt**.
- **Cycle:** capex lên 2–3 năm rồi nghỉ. Template: telecom/fiber 1995–2002, crypto miner 2017–2019, cloud pandemic 2020–2022. “This time is different” không phải phương pháp định giá.
- **Bubble:** giá cần **nhiều năm peak capex, peak margin, không substitution** (ASIC, stack Trung Quốc, software hiệu suất cắt GPU/token). Drawdown 20% từ ATH thường là *down but not cheap*.

AI có thể tiếp tục lớn trong khi **doanh thu GPU, utilization foundry, đơn thiết bị giảm**. Đó là cách phức hợp này **xì hơi**: không phải “AI chết”, mà **tokens/watt tăng và capex/token giảm**.

### 11.3 Checklist (mọi dòng phải có nguồn; thiếu thì UNKNOWN)

**Nhu cầu**

- Capex 2–3 năm của 4 hyperscaler vs OCF vs D&A. Capex >> D&A nhiều năm ⇒ earnings nhà cung cấp trên mid-cycle.
- RPO / backlog / hợp đồng dài: hủy được không?
- Mix training vs inference. Inference dễ bị ASIC hơn.
- Tỷ trọng Trung Quốc / export control. Đổi rule là thesis breaker, không phải footnote.
- Tập trung khách: top 1 / top 4 % doanh thu.

**Lãi giữa chu kỳ (cấm LTM đỉnh)**

- Utilization foundry, hoặc GPU lead time / spot vs contract.
- Gross margin vs dải 5–10 năm. GM kỷ lục → haircut về percentile 75, không lấy trung bình 4 quý gần.
- Capex/sales và capex/D&A. Thiết bị lúc peak booking là bẫy quen.
- Memory: bit growth vs giá. HBM tight vẫn là chu kỳ giá.

**Đường xì hơi (bắt buộc viết, hoặc nói không có)**

Viết path 3–5 năm trong đó **AI use tăng** và **earnings công ty này −20 đến −40%**, nếu path tồn tại:

- Hyperscaler giảm GPU sau năm build-out (depreciation cliff, ROIC cluster thất vọng).
- Custom ASIC (TPU, Trainium, Inferentia, Maia, MTIA) lấy share training hoặc inference.
- Hiệu suất model (distillation, MoE, kernel) cắt FLOPs/token hữu ích.
- Stack nội địa Trung Quốc thay slice bị cấm.
- Cạnh tranh accelerator (AMD, custom) ép ASP/margin GPU.
- Lưới điện / permitting thành bottleneck; capex trượt phải.

Không viết được path → đó là moat. Viết được → giá phải đã phản ánh một phần, nếu không thì không phải sale-off.

**Reverse DCF bắt buộc**

EV hiện tại ngụ ý tăng trưởng doanh thu/FCF 10 năm và ROIC cuối kỳ bao nhiêu, với discount = local 10y + 4–6%? So với tăng trưởng **xuyên chu kỳ**, không 2 năm vừa rồi. Hard-fail nếu implied growth vượt mọi chu kỳ trước mà moat không nới rõ.

**Địa chính trị và điện**

- Đài Loan / eo biển với foundry và mọi leading-edge wafer ngồi đó.
- US/NL/JP export rules, entity list.
- Điện, nước, trạm biến áp cho cluster mới.

**Owner earnings**

- FCF sau capex **để đứng yên** (foundry/equipment không asset-light).
- Phải thu từ một nắm khách.
- SBC ở designer Mỹ là pha loãng thật.

### 11.4 Hard-fail (không Strong buy / Accumulate)

Một cái là đủ:

- Reverse DCF cần **tiếp tục peak hyperscaler capex** ≥ 3 năm.
- Khách lớn nhất ≥ ~25–30% doanh thu và khách đó đang guide capex **xuống**.
- GM hoặc booking **kỷ lục chu kỳ** mà multiple vẫn trên median 10 năm.
- Luận điểm chỉ là “AI TAM” hoặc vào rổ chỉ số.
- Tỷ trọng Trung Quốc / export control lớn và chưa model.
- Foundry/equipment: dùng peak utilization / peak booking làm mid-cycle.
- Hyperscaler: vốn hóa spend AI như ROIC cluster đã chứng minh trong khi công ty chưa công bố payback.

Foundry pháo đài hay độc quyền lithography vẫn có thể Watch / Avoid on valuation. Chất lượng không hết hạn overlay.

### 11.5 Soft-fail (Watch, chờ giá)

- Franchise ổn, mid-cycle earnings khả dĩ, nhưng FCF yield < local 10y + 2%.
- Drawdown từ ATH < 25% mà earnings chưa reset.
- Bull case là “multiple re-rating vì AI” chứ không phải cash.

### 11.6 Khi nào pass (hiếm)

- Foundry/equipment ở multiple **mid-cycle cũ** và utilization đã mean-revert, net cash, reverse DCF chạy trên wafer starts giữa chu kỳ.
- Hyperscaler: trả cho FCF **core** ads/cloud, AI optionality **free** (core FCF yield đã vượt hurdle **sau** maintenance capex; AI capex optional trong bear).
- Memory chỉ khi giá đáy, bảng cân đối pháo đài — thường là cycle-trade, không phải core tích sản.

Pass overlay rồi vẫn phải đủ MOS, quản trị, và nhãn committee của §3–§8.

### 11.7 Output overlay (đặt trên memo cha)

1. Bucket (1–7)
2. Vị trí chu kỳ: đáy / giữa / đỉnh / unknown
3. Lãi mid-cycle (số) vs LTM (số) và haircut đã dùng
4. Reverse DCF: implied growth vs through-cycle growth
5. Đường xì hơi: 5–8 dòng, hoặc “không có path, moat là X”
6. Capex khách vs D&A (bảng nếu dính hyperscaler)
7. Overlay: **Pass** / **Soft-fail wait** / **Hard-fail**
8. Nếu hard-fail: **một số** để đảo (ví dụ “FCF yield ≥ 10y+3% trên mid-cycle, và top-4 khách < 40%”)

Không mua rổ “AI winners” như đa dạng hóa. Chúng là **một** factor. Không lấy drop 12 tháng làm chứng bubble đã xì. Không lấy “ai cũng biết là bong bóng” làm lý do nó không chạy **hoặc** làm lý do nó rẻ. Với tích sản: **tiền mặt hoặc compounder nhàm chán đang chiết khấu thật thắng franchise chip giỏi ở peak multiple.** Nếu overlay hard-fail mà họ vẫn muốn exposure: nhãn **Cycle-trade only**, không phải tích sản.

---

## 12. Real assets (`MODE=REAL_ASSETS`)

Khi rổ cổ phiếu QAD **trống**, hoặc họ muốn **vàng, bạc, kim loại công nghiệp, phân bón, dầu** làm ballast dài hạn. Đây là **phòng chờ sức mua**, không thay doanh nghiệp tốt đang sale-off.

Với người gốc VND: real assets là **một sleeve**, không phải cả sổ. Size sao vẫn còn đạn khi cổ phiếu sale-off xuất hiện. Cash (T-bill USD, tiền gửi VND) là waiting room hợp lệ — không “phải làm gì đó” bằng hàng hóa.

### 12.1 Không phải

- Cách “làm AI” cho đỡ tội.
- Lý do mua miner high-cost lúc spot đỉnh.
- Hệ thống trade CPI.
- ETF đòn bẩy / 3x — **cấm** với tích sản.

### 12.2 Chọn công cụ (theo thứ tự)

1. **ETF backed vật chất** (allocated bullion, hoặc quỹ kim loại/năng lượng holdings minh bạch) khi muốn **giá hàng**, không đòn bẩy vận hành.
2. **Royalty / streaming** chỉ khi hợp đồng, counterparty, depletion soi được — rồi chấm như doanh nghiệp bằng §3.
3. **Producer tứ phân vị 1** (AISC thấp, reserve life dài, jurisdiction sạch, net cash hoặc nợ vừa ở **price deck thấp**) — QAD + overlay mid-cycle này.
4. **Miner high-cost, explorer, junior, ETF 2x/3x** — tránh.

Tài khoản VND nhỏ: một hoặc hai ETF UCITS/US cầm được, đừng năm miner London mỏng. Ghi custody, TER, tracking, physical vs futures.

### 12.3 Luật giữa chu kỳ

Không định giá dầu, urea, sắt, đồng, lithium bằng LTM nếu năm đó nằm tứ phân vị trên của 10–15 năm giá thực. Dựng:

- Deck giá thực **thấp / giữa / cao** (dollar hôm nay).
- Sản lượng không giả định phép màu cầu.
- Sustaining capex; miner: closure/rehab.
- ETF dầu futures: **contango vs backwardation**. Contango ăn case buy-and-hold. Curve contango dốc → producer giữa chu kỳ hoặc bỏ dầu.

Phân bón: như module VN — công suất, utilization, khí/than đầu vào, chính sách xuất Trung Quốc, cầu nông hộ. Năm urea đỉnh là bẫy (DCM/DPM).

Vàng/bạc: **không có earnings yield**. Hurdle là opportunity cost vs real rate và vs cash. Vàng là bảo hiểm đàn áp tài chính, chiến tranh, FX — không phải DCF. Đừng bịa intrinsic 3 chữ số thập phân. Hỏi: sleeve đã lớn chưa, real rate có đang ngược, và có đang mua miner (geared) khi ý là bullion không?

### 12.4 Vàng và bạc

- Ưu tiên sản phẩm allocated (bar list, LBMA/COMEX, TER thấp).
- Miner: AISC vs spot, reserve life, jurisdiction, pha loãng, hedging. Miner vàng là claim **high-beta**, không phải “vàng an toàn hơn.”
- Bạc công nghiệp hơn, biến động hơn; size nhỏ hơn vàng.
- Central-bank buying và dòng ETF là context chiến thuật, không phải luận điểm 10 năm.
- Với người VND, vàng còn là vị thế **USD/VND và real rate**. Nói to điều đó.

### 12.5 Dầu

- Deck Brent/WTI giữa chu kỳ (ghi số đã dùng; đừng giả vờ chính xác).
- Producer: FCF sau sustaining capex ở deck đó, net debt, decline rate, rủi ro chính trị.
- Major vs shale vs national oil: tái đầu tư và pha loãng khác nhau.
- ETF dầu: nếu futures, đưa 5y roll return vs spot. Lạc spot nặng thì không dùng để tích sản.
- Refiner và oilfield services = cycle-trade trừ khi §3 tự nói khác.

### 12.6 Kim loại công nghiệp

- Đồng là chu kỳ công nghiệp sạch nhất (lưới, EV, điện data-center). Vẫn là chu kỳ. Giá giữa, không print squeeze.
- Sắt là cược BĐS/thép Trung Quốc — thanh cao, thường producer lúc đáy hoặc bỏ.
- Lithium/rare earths: policy và dư cung dữ; mặc định **tránh** trừ khi giá đã ngụ ý glut và bảng cân đối pháo đài.
- Major đa dạng (BHP, RIO, Glencore): SOTP mid-cycle, phân bổ vốn, Trung Quốc, và niêm yết cầm được.

### 12.7 Phân bón

- Nitrogen (dính khí) vs potash vs phosphate là chu kỳ khác. Đừng nhét một rổ.
- Netback giữa chu kỳ. P/E năm đỉnh là bẫy.
- Policy (cấm xuất Trung Quốc, trợ cấp Ấn, khí EU) đổi toán nhanh hơn sản lượng.

### 12.8 Size và portfolio

- Real assets **không thay** cổ phiếu sale-off. Giữ dry powder.
- Nếu cổ phiếu toàn Watch/wait: **vàng/bạc ballast trước**, rồi tuỳ **energy hoặc đồng giữa chu kỳ**. Phân bón và lithium nhỏ, optional.
- Không stack: vàng ETF + miner vàng + AUD + sắt + dầu. Đó là một factor risk-on hàng hóa.
- Rebalance về **cổ phiếu** khi một mã QAD vào vùng tốt / rất tốt. Sleeve này là phòng chờ có store of value, không phải tôn giáo.
- Không đòn bẩy, không option overlay, không 3x.

### 12.9 Output real assets

1. Vì sao cổ phiếu không pass (một đoạn, hoặc “user xin ballast”)
2. Bảng công cụ: ticker, cấu trúc (physical / futures / producer), TER, thanh khoản, thực sự đang cầm gì
3. Chu kỳ: đáy / giữa / đỉnh cho từng hàng
4. Price deck đã dùng
5. Producer: AISC hoặc netback, net debt, FCF ở deck **thấp**, pha loãng
6. Vàng/bạc: real-rate và USD/VND; miner vs bullion
7. Cảnh báo roll-yield nếu ETF futures
8. Weight sleeve gợi ý và **rule trim** để ra tiền khi cổ phiếu sale-off xuất hiện
9. Hard avoid (ETF đòn bẩy, junior, phân bón/dầu đỉnh chu kỳ)

---

## 13. Nhắc cách chạy

1. Router: `MARKET` + `MODE`.
2. Nếu AI/chip/hyperscaler-capex → §11 trước.
3. Chạy đủ Agent 1–10. Không shortcut.
4. Chấm 100 điểm, soi hard fail.
5. Ra 11 mục output + dòng committee.
6. Rổ trống → nói trống, rồi cash hoặc §12.

Gõ `/Quality-at-a-Discount` hoặc nói thường (“screen Mỹ”, “FPT rẻ chưa”, “NVDA có phải bong bóng”, “không có cổ thì vàng”). Skill tự gắn pack. Không paste lại file này.
