# Báo cáo cá nhân — 2A202603529_NguyenDacThe

> Tình huống doanh nghiệp minh họa: công ty, hoạt động và số liệu dưới đây được xây dựng cho bài phân tích, không phải dữ liệu thu thập tại một doanh nghiệp thực tế. Cách trình bày theo template và bài mẫu của repo.

## 1. Thông tin học viên

- Họ tên: Nguyễn Đắc Thể
- MSSV: 2A202603529
- Tên nhóm: VibeCode
- Link repo nhóm: https://github.com/NguyenDacThe/K5-L3A-Day02-NhomVibeCode-DiscoveryProblemFraming.git
- Chủ đề: cải thiện công việc vận hành kinh doanh tại công ty phân phối thiết bị văn phòng.

**Bối cảnh phân tích:** một công ty phân phối thiết bị văn phòng có khoảng 30 nhân sự, phục vụ khách hàng doanh nghiệp. Bộ phận kinh doanh nhận yêu cầu qua email và Zalo; danh mục hàng, bảng giá, đơn hàng và lịch sử chăm sóc được lưu ở các bảng tính khác nhau. Nhân viên vận hành kinh doanh phối hợp với sales, kế toán và kho để chuẩn hóa đơn hàng, đối chiếu thanh toán và hỗ trợ khách hàng.

**Vai trò được phân tích:** nhân viên vận hành kinh doanh (Sales Operations). Phạm vi tập trung vào công việc từ khi nhận yêu cầu đến khi tạo đơn hoặc chuẩn bị thông tin cho bộ phận liên quan; chưa bao gồm quyết định giá đặc biệt, duyệt công nợ hay điều phối toàn bộ doanh nghiệp.

### CP0 — Đọc và phân tích bài mẫu

Bài mẫu về Product Manager cho thấy cần bắt đầu bằng công việc cụ thể, xác định bước nghẽn rồi mới cân nhắc công cụ. Nhóm mẫu chọn thử nghiệm nhỏ với công cụ có sẵn và người duyệt, vì các bước xử lý đã rõ và chưa cần Agent tự quyết bước tiếp theo.

Áp dụng vào tình huống công ty phân phối:

- Scan nhiều công việc trong một vai trò trước khi chọn vấn đề ưu tiên.
- Mỗi card cần mô tả quy trình hiện tại, số phút từng bước, bước nghẽn và tác động.
- So sánh cả cách đổi quy trình, dùng biểu mẫu, công thức và phương án có AI.
- Đo cả thời gian và chất lượng; xử lý nhanh hơn nhưng sai mã hàng hoặc số tiền thì không đạt.
- CP2 chọn card để chuẩn bị pitch; candidate chung của nhóm chỉ được chọn tại CP3.

---

## 2. Scan problem (CP1)

Danh sách gồm **10 candidate**, trải đủ 4 lăng kính. Cột định lượng dùng bộ số liệu của tình huống minh họa nêu ở đầu báo cáo; các thời lượng là thời gian thao tác chủ động, không bao gồm chờ khách hàng hoặc bộ phận khác phản hồi.

| # | Lăng kính | Job Story: Khi… tôi muốn… để… | Ai chịu ảnh hưởng? | Dấu hiệu định lượng trong tình huống |
|---:|---|---|---|---|
| 1 | Lặp lại | Khi nhận đơn đặt hàng qua email hoặc tin nhắn, tôi muốn chuyển yêu cầu của khách thành danh sách mặt hàng và số lượng chính xác, để tạo đơn bán hàng mà không phải nhập lại nhiều lần. | Nhân viên vận hành kinh doanh, sales, kho | 20 đơn/ngày, trung bình 6 phút/đơn, tương đương 120 phút/ngày; 3/100 đơn phải sửa sau khi tạo vì sai mã hoặc số lượng. |
| 2 | Lặp lại | Khi khách yêu cầu báo giá, tôi muốn tìm đúng sản phẩm và giá đang áp dụng, để gửi báo giá nhất quán và đúng thời hạn. | Sales, nhân viên vận hành kinh doanh, khách hàng | 6 báo giá/ngày, khoảng 10 phút/báo giá; phải đối chiếu 3 bảng: danh mục sản phẩm, giá và chiết khấu. |
| 3 | Tốn thời gian | Khi đến kỳ đối chiếu công nợ hằng tuần, tôi muốn ghép đúng khoản thanh toán với hóa đơn, để xác định khách nào còn nợ và tránh nhắc thanh toán nhầm. | Kế toán công nợ, nhân viên vận hành kinh doanh, sales | 60 hóa đơn và 45 giao dịch/tuần; đối chiếu mất 150 phút/tuần; 8/45 giao dịch không ghi đầy đủ mã hóa đơn. |
| 4 | Cần đọc, tổng hợp nhiều thông tin | Khi khách liên hệ lại về một đơn hàng, tôi muốn nắm được lịch sử trao đổi và cam kết trước đó, để phản hồi đúng mà không bắt khách kể lại từ đầu. | Nhân viên chăm sóc khách hàng, sales, khách hàng | 12 yêu cầu/ngày, 8 phút/yêu cầu; riêng tìm lịch sử mất 3 phút/yêu cầu; 4/12 yêu cầu phải xem ít nhất 2 nguồn. |
| 5 | Tốn thời gian | Khi kết thúc cuộc họp kinh doanh, tôi muốn có danh sách việc cần làm, người phụ trách và hạn hoàn thành, để các quyết định được thực hiện đầy đủ. | Trưởng phòng kinh doanh, sales, nhân viên vận hành | 2 cuộc họp/tuần; mỗi lần mất 25 phút tổng hợp ghi chú; 3/12 đầu việc trong tuần chưa có hạn hoàn thành rõ ràng. |
| 6 | Cần đọc, tổng hợp nhiều thông tin | Khi chuẩn bị xác nhận thời gian giao hàng, tôi muốn biết số lượng có thể bán sau khi trừ hàng đã giữ cho đơn khác, để tránh hứa giao hàng vượt khả năng đáp ứng. | Sales, kho, khách hàng | Đối chiếu 100 mã hàng/tuần giữa tồn kho và đơn chờ; mất 60 phút/tuần; 5 mã có số lượng khả dụng lệch giữa hai bảng. |
| 7 | Pain từ người khác | Khi kho nhận yêu cầu xuất hàng, tôi muốn có đủ mã hàng, địa chỉ và thời điểm giao, để chuẩn bị hàng mà không phải hỏi lại bộ phận kinh doanh. | Nhân viên kho, nhân viên vận hành, người giao hàng | 8/100 yêu cầu bàn giao thiếu địa chỉ hoặc thời điểm giao; mỗi yêu cầu mất thêm 5 phút trao đổi, tương đương 40 phút/100 yêu cầu. |
| 8 | Pain từ người khác | Khi quản lý xem các khiếu nại trong tuần, tôi muốn biết từng trường hợp đang ở trạng thái nào và ai chịu trách nhiệm, để ưu tiên xử lý các trường hợp chưa có người theo dõi. | Quản lý chăm sóc khách hàng, nhân viên xử lý, khách hàng | 30 khiếu nại/tuần; 5 trường hợp chưa có người phụ trách; mất 35 phút tổng hợp trạng thái từ các cuộc trao đổi. |
| 9 | Cần đọc, tổng hợp nhiều thông tin | Khi cần đặt thêm một mặt hàng, tôi muốn so sánh giá, thời gian giao và điều kiện thanh toán của các nhà cung cấp, để chọn phương án phù hợp với nhu cầu giao hàng. | Nhân viên mua hàng, quản lý, kế toán | Mỗi tuần so sánh 3 báo giá cho một đợt mua; mất 45 phút chuẩn hóa tên hàng, đơn vị tính và điều kiện giao nhận. |
| 10 | Lặp lại | Khi khách hỏi tiến độ giao hàng, tôi muốn tìm được trạng thái cập nhật mới nhất của đơn, để phản hồi đúng mà không phải hỏi riêng từng bộ phận. | Sales, kho, khách hàng | 15 lượt hỏi/ngày, trung bình 2 phút/lượt tra cứu và soạn trả lời, tương đương 30 phút/ngày; dữ liệu nằm ở bảng đơn và bảng giao hàng. |

**Gợi ý được giữ lại:** các công việc có actor cụ thể, quy trình lặp lại, đầu vào/đầu ra xác định được và chỉ số có thể đo. #4 tập trung vào lịch sử trao đổi và cam kết, còn #10 chỉ tra trạng thái giao hàng; hai vấn đề có phạm vi khác nhau.

**Gợi ý loại bỏ:** “trợ lý quản lý toàn công ty” và “tự động hóa toàn bộ kinh doanh” vì quá rộng, khó xác định một bước nghẽn và không vừa sức phân tích trong buổi lab.

---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)

### Bảng chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 | Chuẩn hóa và nhập đơn từ email/tin nhắn (#1) | Lặp lại 20 lần/ngày; tiêu tốn 120 phút/ngày; có bước nhập liệu cụ thể và tiêu chí đúng/sai về mã hàng, số lượng | Khách có chấp nhận biểu mẫu chuẩn không; bao nhiêu đơn có mô tả hàng không rõ; thời gian người kiểm có làm mất phần tiết kiệm không |
| 2 | Đối chiếu thanh toán với hóa đơn (#3) | Mất 150 phút/tuần; có dữ liệu cấu trúc; so sánh rõ phương án dùng Rule với hỗ trợ xử lý ngoại lệ | Khoản trả gộp hoặc trả một phần chiếm bao nhiêu; có mã định danh ổn định để ghép tự động không |
| 3 | Tìm lại lịch sử trao đổi với khách (#4) | 12 yêu cầu/ngày; tìm lịch sử chiếm 36 phút/ngày; ảnh hưởng trực tiếp chất lượng phản hồi | Dữ liệu các kênh có truy cập được không; cùng tên khách có thể bị nhầm giữa nhiều đơn hay không |

**Lý do chưa ưu tiên các candidate còn lại:** báo giá và tồn kho phụ thuộc việc làm sạch dữ liệu gốc; ghi chú họp, bàn giao kho và theo dõi khiếu nại có thể cải thiện bằng template hoặc phân công; so sánh nhà cung cấp xuất hiện ít hơn; tra trạng thái giao hàng có phạm vi hẹp và có thể giải bằng một bảng thống nhất. Đây là lựa chọn sơ bộ của phần cá nhân, chưa phải kết luận chung của nhóm.

### Problem Card #1 — Chuẩn hóa và nhập đơn từ email/tin nhắn

| Trường | Nội dung |
|---|---|
| Job Story | Khi nhận đơn đặt hàng qua email hoặc tin nhắn, tôi muốn chuyển yêu cầu của khách thành danh sách mặt hàng và số lượng chính xác, để tạo đơn bán hàng mà không phải nhập lại nhiều lần. |
| Actor | Nhân viên vận hành kinh doanh phụ trách tạo đơn, phối hợp sales xác nhận thông tin và chuyển đơn cho kho. |
| Thời điểm / bối cảnh | Trong giờ làm việc, khi nhận đơn từ khách doanh nghiệp qua email hoặc Zalo; một đơn tiêu chuẩn có 1–5 dòng hàng và đủ thông tin để xử lý. |
| Quy trình hiện tại (3–7 bước) | Mở yêu cầu → đọc mặt hàng và số lượng → đối chiếu danh mục và giá → nhập các trường vào bảng đơn → kiểm tra lại với yêu cầu gốc → chuyển đơn đã kiểm cho kho. |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 4, nhập lại mã hàng, số lượng, đơn giá và thông tin khách: 2 phút/đơn, chiếm 1/3 tổng thời gian. Việc chuyển qua lại giữa yêu cầu gốc và bảng đơn dễ tạo lỗi nhập liệu. |
| Impact (nếu không giải thì sao) | 20 đơn × 6 phút = 120 phút/ngày; trong tuần 5 ngày là 600 phút, tương đương 10 giờ. 3/100 đơn phải sửa sau khi tạo do sai mã hoặc số lượng, gây thêm công việc cho sales và kho. Thời gian sửa không cộng vào baseline 120 phút. |
| Success metric (baseline → target) | Trung bình 6 → tối đa 3 phút/đơn tiêu chuẩn; tương đương 120 → tối đa 60 phút/ngày ở cùng mức 20 đơn. Tỉ lệ đơn phải sửa giảm từ 3/100 xuống tối đa 1/100. Cách đo: ghi thời điểm bắt đầu/kết thúc từng đơn và lỗi sau tạo trong pilot 5 ngày, 100 đơn; thời gian người duyệt được tính vào tổng. |
| Phương án không dùng AI | Biểu mẫu đặt hàng có trường bắt buộc; danh mục mã hàng chuẩn; danh sách chọn thay nhập tay; công thức tra giá; checklist kiểm trước khi chuyển kho. |
| Giả thuyết về AI (nếu có) | Nếu khách vẫn gửi văn bản tự do, AI có thể trích tên hàng, số lượng và thông tin giao hàng thành bản nháp. Rule đối chiếu mã và giá; người phụ trách xác nhận các trường chưa rõ. AI không tự suy đoán mã, đổi giá hoặc gửi lệnh xuất kho. |
| Cảm nhận nhanh | Thử No AI/Rule trước. Workflow phù hợp nếu đầu vào văn bản tự do vẫn chiếm tỉ trọng đáng kể; chưa có lý do dùng Agent. |

Quy trình nháp hiện tại — **6 phút/đơn, 120 phút/ngày**:

```text
[1. Mở yêu cầu: 0,5 phút]
→ [2. Đọc mặt hàng và số lượng: 1 phút]
→ [3. Đối chiếu danh mục và giá: 1 phút]
→ [4. Nhập thông tin vào bảng đơn: 2 phút] ← BOTTLENECK
→ [5. Kiểm lại với yêu cầu gốc: 1 phút]
→ [6. Chuyển đơn cho kho: 0,5 phút]

Tổng: 0,5 + 1 + 1 + 2 + 1 + 0,5 = 6 phút/đơn.
20 đơn/ngày × 6 phút = 120 phút/ngày.
```

**Giới hạn phạm vi:** chỉ xét đơn đủ thông tin, 1–5 dòng hàng. Đơn thiếu thông tin, khách yêu cầu giá đặc biệt hoặc có tên hàng không xác định được được chuyển sang hàng chờ xác nhận và theo dõi riêng; không tính thời gian chờ như thời gian thao tác.

### Problem Card #2 — Đối chiếu thanh toán với hóa đơn

| Trường | Nội dung |
|---|---|
| Job Story | Khi đến kỳ đối chiếu công nợ hằng tuần, tôi muốn ghép đúng khoản thanh toán với hóa đơn, để xác định khách nào còn nợ và tránh nhắc thanh toán nhầm. |
| Actor | Nhân viên kế toán công nợ; nhân viên vận hành kinh doanh hỗ trợ xác minh đơn và khách hàng. |
| Thời điểm / bối cảnh | Cuối tuần, trước khi gửi bảng công nợ cho sales; mỗi đợt gồm 60 hóa đơn và 45 giao dịch thanh toán. |
| Quy trình hiện tại (3–7 bước) | Xuất danh sách hóa đơn → chuẩn hóa giao dịch thanh toán → ghép giao dịch với hóa đơn → xử lý khoản chưa khớp → cập nhật số dư → kiểm tra và chia sẻ bảng công nợ. |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 3, ghép giao dịch với hóa đơn: 50 phút/tuần. Nội dung chuyển khoản không thống nhất; một khách có thể có nhiều hóa đơn, trả gộp hoặc trả một phần. |
| Impact (nếu không giải thì sao) | 150 phút/tuần, tương đương 10 giờ trong chu kỳ 4 tuần. 8/45 giao dịch thiếu mã hóa đơn, cần bước xác minh riêng; số dư chưa chốt có thể khiến sales nhắc nợ sai. |
| Success metric (baseline → target) | Tổng thời gian 150 → tối đa 75 phút/đợt ở quy mô tương đương 60 hóa đơn và 45 giao dịch. Mọi kết quả ghép được kế toán xác nhận trước cập nhật; số giao dịch gán nhầm sau xác nhận phải bằng 0. Cách đo: ghi giờ từng bước trong 4 kỳ tuần, đếm số trường hợp ghép sai và so tổng tiền trước/sau. |
| Phương án không dùng AI | Chuẩn hóa mã khách/mã hóa đơn; yêu cầu nội dung thanh toán theo mẫu; dùng công thức ghép mã, kiểm số tiền và bảng ngoại lệ. Khoản trả gộp hoặc một phần do kế toán xử lý. |
| Giả thuyết về AI (nếu có) | Có thể hỗ trợ đọc nội dung chuyển khoản không theo mẫu để đề xuất khách hoặc hóa đơn liên quan. Không tự ghi nhận công nợ, tự tính lại số tiền hoặc tự gửi nhắc nợ; người phụ trách xác minh mọi gợi ý. |
| Cảm nhận nhanh | Rule cho phần đối chiếu có mã rõ ràng. Chỉ cân nhắc thêm Workflow sau khi biết quy mô và bản chất của nhóm ngoại lệ. |

Quy trình nháp hiện tại — **150 phút/tuần**:

```text
[1. Xuất danh sách hóa đơn: 20 phút]
→ [2. Chuẩn hóa giao dịch thanh toán: 25 phút]
→ [3. Ghép giao dịch với hóa đơn: 50 phút] ← BOTTLENECK
→ [4. Xử lý khoản chưa khớp: 30 phút]
→ [5. Cập nhật số dư công nợ: 15 phút]
→ [6. Kiểm tra và chia sẻ: 10 phút]

Tổng: 20 + 25 + 50 + 30 + 15 + 10 = 150 phút/tuần.
```

**Giới hạn phạm vi:** chuẩn bị bảng đối chiếu nội bộ, không thay đổi sổ kế toán hay thực hiện giao dịch ngân hàng. Nếu chưa xác định được khoản thanh toán thuộc hóa đơn nào, giữ trạng thái chưa xác minh thay vì tự ghép theo số tiền gần giống.

### Problem Card #3 — Tìm lịch sử trao đổi trước khi phản hồi khách

| Trường | Nội dung |
|---|---|
| Job Story | Khi khách liên hệ lại về một đơn hàng, tôi muốn nắm được lịch sử trao đổi và cam kết trước đó, để phản hồi đúng mà không bắt khách kể lại từ đầu. |
| Actor | Nhân viên chăm sóc khách hàng hoặc sales tiếp nhận yêu cầu khi người xử lý trước không trực tiếp có mặt. |
| Thời điểm / bối cảnh | Khi khách hỏi lại về đơn, cam kết đổi hàng hoặc lịch xử lý đã thống nhất; thông tin nằm trong email, trao đổi Zalo và bảng đơn. |
| Quy trình hiện tại (3–7 bước) | Xác định khách và mã đơn → mở hồ sơ đơn → tìm lịch sử trao đổi → xác nhận cam kết mới nhất → soạn phản hồi → kiểm tra và gửi. |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 3, tìm và đọc lại lịch sử: 3 phút/yêu cầu, chiếm 37,5% tổng thời gian. Một số trường hợp phải đối chiếu ít nhất hai nguồn để biết cam kết nào còn hiệu lực. |
| Impact (nếu không giải thì sao) | 12 yêu cầu × 8 phút = 96 phút/ngày; riêng tìm lịch sử là 12 × 3 = 36 phút/ngày. Thông tin thiếu hoặc cũ có thể khiến nhân viên trả lời khác với cam kết trước. |
| Success metric (baseline → target) | Tổng thời gian 8 → tối đa 4 phút/yêu cầu; riêng tìm lịch sử 3 → tối đa 1 phút. Với 12 yêu cầu/ngày, thời gian tổng giảm từ 96 xuống tối đa 48 phút. Mọi cam kết nêu trong phản hồi phải truy về nguồn và thời điểm. Đo trên 60 yêu cầu trong 5 ngày, ghi giờ, nguồn đã dùng và số phản hồi phải đính chính. |
| Phương án không dùng AI | Mã khách và mã đơn thống nhất; nhật ký chăm sóc tập trung; sau mỗi trao đổi ghi cam kết, người phụ trách và thời điểm; dùng liên kết tới tin nhắn hoặc email nguồn. |
| Giả thuyết về AI (nếu có) | AI có thể tổng hợp lịch sử đã được cấp quyền thành bản nháp có trích nguồn. Nhân viên kiểm cam kết mới nhất trước khi trả lời; không để hệ thống tự hứa đổi hàng, hoàn tiền hoặc tự gửi phản hồi. |
| Cảm nhận nhanh | No AI nếu nhật ký tập trung đã đủ. Workflow có bước tìm nguồn và tóm tắt nếu cần đọc nhiều trao đổi dài; Agent chưa cần thiết vì các bước xử lý đã rõ. |

Quy trình nháp hiện tại — **8 phút/yêu cầu, 96 phút/ngày**:

```text
[1. Xác định khách và mã đơn: 1 phút]
→ [2. Mở hồ sơ đơn: 1 phút]
→ [3. Tìm và đọc lịch sử trao đổi: 3 phút] ← BOTTLENECK
→ [4. Xác nhận cam kết mới nhất: 1 phút]
→ [5. Soạn phản hồi: 1 phút]
→ [6. Kiểm tra và gửi: 1 phút]

Tổng: 1 + 1 + 3 + 1 + 1 + 1 = 8 phút/yêu cầu.
12 yêu cầu/ngày × 8 phút = 96 phút/ngày.
```

**Giới hạn phạm vi:** chỉ xử lý lịch sử thuộc khách và đơn đã xác định, trong nguồn nhân viên có quyền xem. Yêu cầu chỉ hỏi trạng thái giao hàng thuộc candidate #10, không gộp vào mẫu 12 yêu cầu/ngày của card này.

### Card muốn pitch nhất

- **Card số:** #1 — Chuẩn hóa và nhập đơn từ email/tin nhắn.
- **Vì sao:** tác vụ lặp lại mỗi ngày, mất 10 giờ/tuần ở quy mô 20 đơn/ngày; có thể thử trên một nhóm đơn nhỏ và đo cả tốc độ lẫn lỗi. Phạm vi không đòi thay đổi toàn bộ hệ thống của công ty.
- **Câu hỏi muốn nhóm phản biện:** “Nếu chuẩn hóa biểu mẫu đặt hàng và dùng danh sách chọn mã hàng đã giảm được phần lớn thời gian nhập, còn bước nào thực sự cần AI?”
- **Giả định cần kiểm chứng tiếp:** mức chấp nhận biểu mẫu của khách, tỉ trọng đơn văn bản tự do, tỉ lệ đơn ngoài phạm vi và thời gian nhân viên phải kiểm/sửa bản nháp.

### AI đã phản biện card thế nào

Bảng dưới ghi kết quả phản biện và chỉnh sửa bản phân tích tình huống, không ghi nhận một cuộc pitch nhóm đã diễn ra.

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
| Card #1 chưa giới hạn số dòng hàng nên so sánh thời gian giữa các đơn có thể không công bằng | Đồng ý trong bản phân tích | Giới hạn đơn tiêu chuẩn 1–5 dòng, đủ thông tin; theo dõi đơn ngoại lệ riêng. |
| Chỉ đặt mục tiêu xử lý nhanh có thể làm tăng lỗi mã hàng hoặc số lượng | Đồng ý trong bản phân tích | Thêm mục tiêu tối đa 1 đơn phải sửa trên 100 đơn; tính cả thời gian người duyệt vào tổng. |
| Biểu mẫu và công thức tra cứu có thể đã đủ, chưa có lý do chọn AI ngay | Đồng ý trong bản phân tích | Đưa No AI/Rule thành phương án thử trước; chỉ cân nhắc Workflow cho đầu vào văn bản tự do. |
| Card #2 có khoản trả gộp và trả một phần, ghép theo số tiền sẽ dễ sai | Đồng ý trong bản phân tích | Tách nhóm ngoại lệ; giữ kế toán xác nhận; không cho cập nhật công nợ tự động. |
| Card #3 có thể trộn khách trùng tên hoặc dùng cam kết cũ | Đồng ý trong bản phân tích | Yêu cầu định danh bằng mã khách/mã đơn, gắn nguồn và thời điểm; nhân viên kiểm trước khi gửi. |

---

## 4. Tôi đã tham gia phần nào (CP3 → CP7)

**Vai trò chính:** phụ trách CP3 — hội tụ nhóm; hỗ trợ Trương Văn Thông ở CP6. Ba card doanh nghiệp ở mục 3 là candidate cá nhân; phần nhóm chọn **candidate #7 của Đức Anh — Tra cứu và đối chiếu yêu cầu đầu buổi lab**. Số thứ tự candidate trong báo cáo nhóm khác số thứ tự bảng scan cá nhân.

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | Đưa 3 card cá nhân về nhập đơn hàng, đối chiếu công nợ và tra lịch sử khách hàng vào danh sách tổng hợp; phụ trách nối 3 card của mỗi thành viên thành bảng 12 candidate. | Ba card của tôi tương ứng #4–#6 tại [bảng pitch nhóm](../team/group_report.md#21-pitch); có actor và bước nghẽn để so sánh với các hướng khác. |
| Phản biện bài của bạn khác | Chuẩn bị câu hỏi cho candidate #7: “Điểm nghẽn do tài liệu phân tán hay chưa đọc đúng thứ tự? Nếu dùng bảng đầu việc thủ công thì thời gian và số yêu cầu bỏ sót thay đổi thế nào?” Với #1, đặt vấn đề giữ cùng bộ ca và tính cả thời gian người rà khi so sánh. | Các câu hỏi được ghi là **câu hỏi chuẩn bị cho pitch**, hướng phân tích về nguyên nhân, baseline và phương án đơn giản. Báo cáo chưa ghi nhận câu nào đã được hỏi trực tiếp bởi tôi. |
| Nhận phản biện | Câu hỏi gắn với card nhập đơn của tôi tại bảng 2.1: “Bước nhập chỉ chiếm 2/6 phút thì đạt mục tiêu 3 phút/đơn bằng cách nào?” Bảng nhóm chưa ghi ai thực sự hỏi hoặc thời điểm nhận, nên chưa xem đây là nhật ký phản biện trực tiếp. | Khi rà card, cần tính cả các bước đọc, đối chiếu và kiểm tra; không quy toàn bộ mức giảm tổng thời gian cho riêng nhập liệu. Giữ mục tiêu 3 phút/đơn ở trạng thái giả thuyết thử nghiệm, chưa khẳng định đã đạt. |
| Gom cluster / cây OST | Tổng hợp 4 cluster: chất lượng mô hình, vận hành doanh nghiệp, công việc học tập và hoạt động cá nhân; xây OST cho candidate #7. | [Mục 2.2–2.3](../team/group_report.md#22-cluster-và-chọn-top-3) phân biệt pain dò chéo tài liệu với solution như chatbot hoặc checklist tự động; các nhánh OST đều hướng vào nhu cầu. |
| Chọn candidate problem | Tổng hợp shortlist #7, #8, #1 và bảng điểm 7 tiêu chí; ghi lý do chọn/loại. | [Mục 2.4](../team/group_report.md#24-chấm-điểm-shortlist-15) đề xuất chọn #7 với 33/35 điểm, so với #8 là 32/35 và #1 là 26/35. Không dùng số phút lớn nhất làm tiêu chí duy nhất. |
| Kiểm chứng / research | Đối chiếu nội dung tổng hợp với 2 snapshot phỏng vấn do Đức Anh thực hiện và kết luận research CP4; xem tác động của bằng chứng đến phạm vi nhóm đã chọn. | [Snapshot #1](../assets/cp4-interview-snapshot-1.md) và [#2](../assets/cp4-interview-snapshot-2.md) cho thấy học viên đọc README rồi tiếp tục dò chéo khi làm CP1–CP2. Vai trò phỏng vấn chính thuộc Đức Anh; đóng góp của tôi ở đây là rà và sử dụng kết quả cho lập luận nhóm. |
| Quy trình nhóm | Rà sự liên kết giữa candidate CP3 và quy trình trước/sau do Hường phụ trách ở CP5, đặc biệt bước đối chiếu, người duyệt và phương án quay về. | Phân biệt mốc mô hình 20 phút/người, bước đối chiếu 7 phút ước lượng và thời gian tự thuật 15–20 phút. Tính cả chuẩn bị, kiểm tra và sửa lỗi khi so tổng công sức. |
| Problem Statement | Hỗ trợ Thông rà v1 với v0: actor, phạm vi CP1–CP2, metric, boundary và điểm can thiệp. | [Mục 7 báo cáo nhóm](../team/group_report.md#7-problem-statement-v1--tiêu-chí-đánh-giá-cp6) ghi đủ 9 trường, không có điểm can thiệp AI trong pilot và có bảng giải thích thay đổi so với v0. |
| Mức can thiệp AI | Hỗ trợ rà so sánh No AI / Rule / Workflow / Agent và lý do chọn mức đơn giản nhất. | [Mục 6](../team/group_report.md#6-mức-can-thiệp-ai-cp6) chọn No AI cho pilot; phần Rule/Workflow trong CP5 được giữ là phương án thiết kế để xem xét tiếp khi có bằng chứng. |
| Quyết định | Hỗ trợ rà mức độ 4 rủi ro, điều kiện Go, kế hoạch thử và ngưỡng dừng; đối chiếu với TEAM.md. | [Mục 8](../team/group_report.md#8-quyết-định-cp6) chỉ Go cho pilot nhỏ: trung vị ≤8 phút/người, tổng ≤40 người-phút/nhóm 4 người và 0 lỗi nghiêm trọng. Chưa có kết quả pilot để tuyên bố hiệu quả. |

**Bằng chứng đóng góp:** [phần Nguyễn Đắc Thể trong TEAM.md](../../TEAM.md#nguyendacthe-2a202603529), mục 2 của báo cáo nhóm và vai trò hỗ trợ ở mục 6–8. Cột câu hỏi trên giữ đúng trạng thái chuẩn bị trong tài liệu nguồn, không gán thêm người hỏi hoặc sự kiện thảo luận chưa được ghi nhận.

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Nội dung được điều chỉnh / cách kiểm lại |
|---|---|---|---|---|
| CP2 Chọn top 3 Problem Cards | Nhờ AI phân tích 10 candidate tôi đã nghĩ ra, so sánh và đề xuất 3 vấn đề quan trọng nhất để phát triển thành card | So sánh actor, bottleneck, impact, khả năng đo và phạm vi; làm rõ lý do ưu tiên nhập đơn, đối chiếu công nợ và tra lịch sử khách hàng | Xếp hạng chỉ dựa trên mô tả đầu vào, chưa xác nhận pain ở doanh nghiệp. Mục tiêu nhập đơn từ 6 xuống 3 phút cần xét cả quy trình, không chỉ bước nhập 2 phút | Đối chiếu lý do chọn với từng card; giữ phương án không dùng AI và yêu cầu đo toàn bộ thời gian, công kiểm tra cùng tỉ lệ phải sửa |
| CP3 Tổng hợp bảng candidate nhóm | Nhờ AI đọc 4 báo cáo cá nhân, lấy 3 card quan trọng mỗi thành viên đã chọn và gộp vào bảng candidate trong báo cáo nhóm cho nhanh; tiếp tục hỗ trợ tổ chức bản tổng hợp | Giảm thao tác sao chép, rút gọn Job Story và trình bày nhất quán 12 dòng, đúng người đề xuất, actor và bottleneck | Tổng hợp nhanh vẫn có thể làm mất ý khi rút gọn; câu hỏi chuẩn bị không chứng minh đã có buổi pitch hoặc người hỏi cụ thể | Rà bảng theo báo cáo từng người, giữ đúng 3 card/người; không để AI chọn lại card thay thành viên và không gán câu hỏi chuẩn bị thành phản biện đã xảy ra |
| CP7 Reflection | Nhờ AI hỗ trợ soạn và diễn đạt phần reflection cho các câu 6.1–6.6 trên 200 từ, dựa trên báo cáo nhóm, TEAM.md và phần việc CP3, hỗ trợ CP6 | Sắp xếp nội dung theo từng câu hỏi, liên kết đóng góp với bài học và bảo đảm độ dài yêu cầu | AI không biết đầy đủ trải nghiệm cá nhân; dễ viết chung chung hoặc suy diễn cảm xúc, câu hỏi và sự kiện chưa được ghi nhận | Rà lại từng ý theo trải nghiệm thực tế và bằng chứng trong bài nhóm; chỉnh cách diễn đạt cho phù hợp, loại chi tiết chưa xác nhận; không coi đủ số từ là đã phản ánh đúng trải nghiệm |

---

## 6. Reflection (CP7)

Bản diễn đạt dưới đây được tổng hợp từ công việc CP3, phần hỗ trợ CP6, nội dung TEAM.md và báo cáo nhóm; cách dùng AI đã ghi tại mục 5. Các câu 6.1–6.6 tập trung vào thay đổi trong lập luận và sản phẩm có thể đối chiếu, không bổ sung sự kiện ngoài tài liệu nguồn.

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**

Từ các card của Hường, Đức Anh và Thông, tôi thấy cùng một yêu cầu “giảm thời gian” có thể liên quan đến các công việc rất khác: chấm kết quả mô hình, dò quy định bài lab hoặc đọc tài liệu tiếng Anh. Khi tổng hợp 12 candidate, điều cần so sánh là actor, quy trình, bằng chứng và khả năng kiểm chứng trong thời gian lab. Ba card doanh nghiệp của tôi có quy trình cụ thể nhưng số liệu là tình huống minh họa; chúng không mạnh hơn một vấn đề có thể quan sát ngay chỉ vì con số tác động lớn. Candidate #7 của Đức Anh có tài liệu đầu vào và người dùng cùng bối cảnh để tiếp cận, nên phù hợp hơn cho bước đào sâu. Tôi cũng hiểu rằng phần cá nhân có thể khác đề tài cuối của nhóm; đóng góp của mình còn nằm ở việc tổng hợp và giúp lựa chọn có căn cứ.

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**

Trong các phương án được ghi lại, có hướng dùng chatbot, Agent hoặc Workflow để tổng hợp tài liệu. Nếu đưa các tên giải pháp đó vào tầng opportunity, nhóm sẽ chốt công nghệ trước khi biết pain chính nằm ở đâu. Khi xây OST cho #7, tôi tách việc “phải dò chéo nhiều file để biết đủ yêu cầu” khỏi cách giải như checklist hay chatbot. Kết quả CP4 làm phạm vi rõ hơn: người học đọc README để nắm khung rồi tiếp tục tra điều kiện khi làm từng CP. Vì vậy, CP6 chọn thử bảng tham chiếu No AI trước. Hướng chuyển này cho thấy cần chứng minh giá trị của cách tổ chức thông tin trước khi thêm phần tạo nội dung bằng mô hình.

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

Một thay đổi cụ thể trong cách đánh giá card là không chỉ nhìn tổng thời gian và target. Card nhập đơn của tôi đặt mục tiêu từ 6 xuống 3 phút, nhưng riêng bước nhập chỉ chiếm 2 phút. Câu hỏi chuẩn bị phản biện ở mục 2.1 báo cáo nhóm chỉ ra rằng giảm bước nhập chưa đủ để giải thích toàn bộ mục tiêu; còn phải xét bước đọc, tra danh mục và kiểm tra lại. Vì thế, khi rà lập luận, tôi nhìn target như giả thuyết cần thử, yêu cầu tính cả công duyệt và lỗi sau tạo đơn. Báo cáo nhóm chưa ghi ai thực sự đã đặt câu hỏi này trong buổi pitch, nên tôi không gán một cuộc trao đổi trực tiếp cho thành viên nào. Bài học ở đây là mọi mức giảm kỳ vọng phải nối được với các bước thực sự thay đổi.

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

Điểm đáng chú ý trong hai snapshot do Đức Anh thực hiện là người học không đọc liền toàn bộ tài liệu rồi mới làm bài. Họ đọc README khoảng 5–6 phút, sau đó tiếp tục mở các file quy định khi làm CP1–CP2. Chi tiết này làm cách mô tả problem chuyển từ “đọc tài liệu lâu đầu buổi” sang “dò chéo và lo thiếu điều kiện trong lúc làm”. Tôi còn thấy thời gian 15–20 phút được ghi chưa hoàn toàn thống nhất giữa câu trả lời và câu trích dẫn, nên chưa thể coi đó là phép đo độc lập hoặc cộng thêm thời gian đọc README một cách máy móc. Research cũng gợi hướng tổ chức bảng tham chiếu, khiến việc dùng AI trở thành một giả thuyết phải chứng minh thêm.

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

Điểm khó nhất là giữ actor, phạm vi, bottleneck và metric cùng nói về một công việc. Bằng chứng CP4 hỏi về CP1–CP2 thì v1 không nên tuyên bố giải quyết toàn bộ CP0–CP7. Mốc 7 phút của bước đối chiếu là phân bổ ước lượng, còn 15–20 phút là tự thuật; hai loại số này cần ghi rõ. Khi hỗ trợ Thông rà CP6, tôi đối chiếu mục tiêu trung vị ≤8 phút/người với tổng ≤40 người-phút cho nhóm 4 người, đồng thời giữ tiêu chí 0 lỗi nghiêm trọng. Nếu bảng khiến người dùng đọc nhanh nhưng mất thêm nhiều công chuẩn bị hoặc bỏ sót quy định thì chưa đạt. Boundary và cách quay về nguồn cần rõ ngay cả khi phương án được chọn không dùng AI.

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

Tôi sẽ chuẩn bị bảng so sánh ngắn theo 7 tiêu chí sớm hơn, kiểm tra nguồn của baseline trước khi xếp hạng và tách rõ ví dụ minh họa khỏi dữ liệu thật. Tôi cũng sẽ ghi nhật ký câu hỏi ngay khi thảo luận: ai hỏi, hỏi gì, trả lời thế nào và điều gì thay đổi, để không phải suy từ các câu hỏi chuẩn bị sang một sự kiện chưa được ghi nhận. Với problem đã chọn, tôi sẽ yêu cầu bấm giờ cùng phạm vi CP1–CP2, tính cả người soạn và người duyệt, rồi thử bảng No AI trước. Câu tôi muốn phản biện mạnh hơn là: “Nếu bảng thủ công đã đủ, vì sao cần AI; nếu chưa đủ, chính xác bước nào còn nghẽn?” Sau đó mới xem xét mức phức tạp hơn dựa trên dữ liệu pilot.

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.

Vấn đề nhóm chọn là học viên K5-L3A phải dò chéo nhiều tài liệu để biết đủ nhiệm vụ, vị trí điền và điều kiện của CP1–CP2. Quy trình hiện tại là đọc README, tìm checkpoint, đọc worksheet, đối chiếu Rubric/Rules rồi rà đầu việc; bottleneck là bước đối chiếu lặp lại. Hai snapshot ghi thời gian tự thuật 15–20 phút/người, còn target pilot là trung vị không quá 8 phút/người, tổng công sức nhóm 4 người không quá 40 người-phút và không có lỗi nghiêm trọng. Boundary yêu cầu bảng có nguồn, phiên bản và người duyệt, không thay đề gốc hay làm bài/nộp thay học viên. Nhóm chọn No AI vì chưa có bằng chứng Rule hoặc Workflow mang thêm giá trị so với bảng tham chiếu thủ công. Quyết định là Go cho pilot nhỏ với ít nhất 3 học viên ngoài nhóm, chưa phải triển khai rộng. Nếu vượt ngưỡng thời gian, tổng công sức hoặc có một lỗi nghiêm trọng thì dừng chia sẻ bản đã xác nhận, quay về nguồn và chỉ thử lại sau khi sửa có kiểm tra.

---

## 7. Tài liệu tham khảo

- [Báo cáo nhóm — nguồn chính cho phần hội tụ, kiểm chứng, v0/v1 và quyết định](../team/group_report.md).
- [TEAM.md — vai trò phụ trách CP3 và hỗ trợ CP6 của Nguyễn Đắc Thể](../../TEAM.md#nguyendacthe-2a202603529).
- [Interview Snapshot #1 — do Vũ Đức Anh thực hiện](../assets/cp4-interview-snapshot-1.md).
- [Interview Snapshot #2 — do Vũ Đức Anh thực hiện](../assets/cp4-interview-snapshot-2.md).
- [CHECKPOINTS.md — sản phẩm CP0–CP7 và cách tự kiểm](../../CHECKPOINTS.md).
- [docs/01-worksheet.md — phương pháp làm từng checkpoint](../../docs/01-worksheet.md).
- [docs/02-deliverable-example.md — tham khảo cấu trúc và cách lập luận](../../docs/02-deliverable-example.md).
- [RUBRIC.md — yêu cầu nhật ký phản biện, reflection và hiểu bài, C3–C5](../../RUBRIC.md).
- [RULES.md — nguyên tắc problem first, bằng chứng, sử dụng AI và dữ liệu](../../RULES.md).
