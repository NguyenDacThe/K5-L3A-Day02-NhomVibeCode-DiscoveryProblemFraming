# Báo cáo cá nhân — 2A202603569_DinhThiHuong


## 1. Thông tin học viên

- Họ tên: Đinh Thị Hường
- MSSV: 2A202603569
- Email trường (không bắt buộc, repo có thể để public):
- Tên nhóm: VibeCode
- Link repo nhóm: https://github.com/NguyenDacThe/K5-L3A-Day02-NhomVibeCode-DiscoveryProblemFraming.git
---

## 2. Scan problem (CP1)


| # | Lăng kính | Job Story: Khi... tôi muốn... để... | Ai chịu ảnh hưởng? | Dấu hiệu thật (thời gian, tần suất, số người, bằng chứng) |
|---|---|---|---|---|
| 1 | Cần đọc, tổng hợp nhiều thông tin | Khi bắt đầu một bài toán/feature AI mới, tôi muốn nhanh chóng nắm được SOTA và trade-off giữa các mô hình từ các bài báo/kho tài liệu kỹ thuật, để chọn kiến trúc/thư viện phù hợp mà không mất cả tuần đọc chay. | AI Engineer, Tech Lead, R&D team. | • Mất 8–15 tiếng/tuần chỉ để đọc lướt 5–10 papers/repo github.<br>• Tần suất: 2–3 lần/tháng khi có spike/task nghiên cứu mới.<br>• Bằng chứng: Hàng chục tab GooGle/Chat/GitHub bookmark dở dang. |
| 2 | Tốn thời gian / Lặp lại | Khi tinh chỉnh prompt hoặc cập nhật model/RAG, tôi muốn tự động chạy bộ test benchmark (eval) trên tập golden dataset, để biết chính xác độ chính xác/hallucination tăng hay giảm trước khi deploy lên production. | AI Engineer, QA, Product Manager. | • Mất 2–4 tiếng mỗi lần release chỉ để bấm test tay từng case và soi output.<br>• Tần suất: 2–3 lần/tuần.<br>• Bằng chứng: File Excel/Google Sheet test cases cả trăm dòng chấm điểm thủ công (pass/fail). |
| 3 | Pain từ người khác / Lặp lại | Khi bot/mô hình trả lời sai trên production và team CS/PM báo lỗi, tôi muốn nhanh chóng trace lại ngữ cảnh (input prompt, retrieved docs, latency, token cost), để giải thích lý do lỗi cho team kinh doanh mà không phải đào log thô (raw JSON). | AI Engineer, Customer Support, PM. | • Bị tag 3–5 lần/ngày trên phần mềm chat hỏi "sao con AI nó lại nói thế này?".<br>• Mất 20–30 phút/ticket để query DB tìm đúng trace log. |
| 4 | Tốn thời gian / Cần đọc nhiều thông tin | Khi cần chuẩn bị dataset cho bài toán NLP/LLM mới, tôi muốn sinh nhanh dữ liệu giả lập (synthetic data) đa dạng ngữ cảnh và edge-cases, để có dữ liệu train/eval ban đầu mà không phải chờ tuần lễ gán nhãn thủ công. | AI Engineer, Data Annotator. | • Mất 2–3 ngày viết script gọi API hoặc tự gõ tay các mẫu câu test.<br>• Tần suất: Mỗi khi làm bài toán mới hoặc thêm intent/entity mới. |
| 5 | Lặp lại / Tốn thời gian | Khi làm sạch dữ liệu text/metadata được crawl về hoặc do người dùng nhập, tôi muốn tự động phát hiện dữ liệu rác, trùng lặp, format sai hoặc nhãn bị nhiễu (mislabeled data), để đảm bảo chất lượng mô hình mà không cần inspect bằng mắt từng batch. | AI Engineer, Data Scientist. | • Chiếm 30–40% tổng thời gian một sprint làm data/model.<br>• Tần suất: Lặp lại mỗi lần ingest batch dữ liệu mới.<br>• Bằng chứng: Notebook lọc regex, dropna, groupby thủ công dài lê thê. |
| 6 | Lặp lại / Pain từ người khác | Khi code xong một AI pipeline hoặc service FastAPI, tôi muốn tự động cập nhật Model Card, tài liệu API, tham số đầu vào/đầu ra và hướng dẫn gọi API, để team Backend/Frontend tích hợp được ngay mà không cần chat hỏi riêng từng field. | AI Engineer, Backend Dev, Frontend Dev. | • Mất 2–3 tiếng sau mỗi sprint để viết tài liệu Notion/Confluence.<br>• Dev phía client vẫn hỏi 3–4 câu/ngày vì tài liệu không đồng bộ với code thật. |
| 7 | Lặp lại / Tốn thời gian | Khi thử nghiệm nhiều phiên bản prompt khác nhau (system prompt, temperature, few-shot examples), tôi muốn quản lý version và so sánh output cạnh nhau (side-by-side diff), để biết phiên bản nào tối ưu nhất mà không bị thất lạc code. | AI Engineer, Prompt Engineer. | • File code lưu các biến: prompt_v1, prompt_v2_final, prompt_v2_test.<br>• Tần suất: Diễn ra hàng ngày trong giai đoạn tuning.<br>• Bằng chứng: Dễ ghi đè prompt tốt cũ mà không nhớ mình đã đổi từ ngữ nào. |
| 8 | Pain từ người khác / Cần đọc nhiều thông tin | Khi Product Owner đưa PRD/yêu cầu nghiệp vụ mơ hồ ("làm sao để AI hiểu giọng văn thân thiện, từ chối khéo các câu hỏi nhạy cảm"), tôi muốn chuyển đổi thành danh sách test scenarios và boundary conditions cụ thể, để chốt acceptance criteria rõ ràng. | AI Engineer, PM, Business Analyst. | • Mất 2–3 buổi họp (mỗi buổi 1 tiếng) tranh cãi về việc "thế nào là AI trả lời đạt".<br>• Rủi ro làm xong bị reject vì "chưa đúng kỳ vọng mơ hồ ban đầu". |
| 9 | Cần đọc, tổng hợp nhiều thông tin / Lặp lại | Khi review Pull Request của đồng nghiệp có chứa Jupyter Notebook (.ipynb), tôi muốn xem được diff code logic sạch sẽ và output kiểm thử, để review nhanh chất lượng code thay vì phải nhìn file JSON diff rối mắt. | AI Engineer, Lead Engineer. | • Mất 30–45 phút/PR chỉ để scroll qua các cell metadata, base64 images thừa.<br>• Tần suất: 3–5 PRs/tuần.<br>• Bằng chứng: Nhiều người approve bừa PR notebook vì diff quá khó đọc trên GitHub/GitLab. |
| 10 | Tốn thời gian / Lặp lại | Khi triển khai hệ thống RAG, tôi muốn tự động đo lường và tối ưu hóa chunk size, chiến lược embedding và độ tương đồng retrieval, để tìm ra config tối ưu mà không phải thử-sai (trial-and-error) thủ công từng tham số. | AI Engineer. | • Mất 3–5 ngày chỉ để test các kích thước chunk (256, 512, 1024) và top-k.<br>• Đánh giá chất lượng dựa trên cảm tính thay vì số liệu đo lường cụ thể. |

---

## 3. Top 3 Problem Cards + quy trình nháp (CP2)


### Bảng chọn top 3

| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|---:|---|---|---|
| 1 | Vấn đề 2: Chạy benchmark và kiểm thử (eval) LLM/Prompt tự động trên tập golden dataset trước khi deploy | Đây là bước nghẽn lớn nhất gây chậm trễ release và dễ lọt lỗi hallucination ra ngoài; bài toán có đầu vào/đầu ra rõ ràng, đo lường được ngay. | Chưa chắc chắn về độ tin cậy tuyệt đối của phương pháp AI chấm điểm AI (LLM-as-a-judge) so với con người. |
| 2 | Vấn đề 3: Trace log và truy vết ngữ cảnh lỗi khi bot trả lời sai trên production cho team CS/PM | Giảm xung đột trực tiếp giữa kỹ sư và các bộ phận phi kỹ thuật; loại bỏ thao tác đào bới log JSON thủ công gây đứt mạch làm việc. | Chưa rõ cấu hình hệ thống log hiện tại có lưu đủ metadata (retrieved context, token, prompt version) hay không. |
| 3 | Vấn đề 7: Quản lý version prompt và kiểm tra so sánh kết quả side-by-side | Diễn ra hàng ngày trong giai đoạn tuning; dễ làm mất dấu prompt tốt nếu chỉ lưu biến linh tinh trong file code hoặc notepad. | Liệu đồng nghiệp có chịu tuân thủ quy trình dùng công cụ quản lý mới hay vẫn quen tay sửa code trực tiếp. |

---

### Problem Card #1

| Trường | Nội dung |
|---|---|
| Job Story | Khi tinh chỉnh prompt hoặc cập nhật model/RAG, tôi muốn tự động chạy bộ test benchmark (eval) trên tập golden dataset, để biết chính xác độ chính xác/hallucination tăng hay giảm trước khi deploy lên production. |
| Actor | AI Engineer, QA Tester, Product Manager |
| Thời điểm / bối cảnh | Trước mỗi lần chuẩn bị merge code hoặc deploy phiên bản prompt/mô hình mới (tần suất 2–3 lần/tuần) |
| Quy trình hiện tại (3–7 bước) | 1. AI Engineer sửa prompt trong code hoặc playground.<br>2. Mở file Google Sheet chứa 50–100 câu hỏi golden dataset.<br>3. Copy lần lượt từng câu hỏi dán vào chatbot để lấy output.<br>4. Đọc bằng mắt từng output, so sánh với đáp án chuẩn (ground truth).<br>5. Đánh dấu cột Đạt/Không đạt trên sheet và tính nhẩm tỷ lệ chính xác.<br>6. Nếu tỷ lệ đạt trên 80% thì gửi link sheet cho PM duyệt rồi release. |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 3 và Bước 4 (Copy-paste và đọc thẩm định thủ công bằng mắt từng câu), mất khoảng 120–180 phút mỗi lần test |
| Impact (nếu không giải thì sao) | Kỹ sư mỏi mắt chấm sót lỗi; tần suất release bị chậm; dễ lọt câu trả lời sai/hallucination lên production gây mất uy tín sản phẩm |
| Success metric (baseline → target) | Thời gian kiểm thử mỗi đợt: từ 150 phút giảm xuống dưới 10 phút. Số lượng test case chạy được: từ 50 câu tăng lên hơn 200 câu |
| Phương án không dùng AI | Viết script Python đọc CSV test cases, gọi API hàng loạt, so sánh kết quả bằng exact match, regex hoặc assert cấu trúc schema JSON |
| Giả thuyết về AI (nếu có) | Dùng mô hình LLM nhỏ, rẻ (như GPT-4o-mini hoặc Claude Haiku) đóng vai trò thẩm định (LLM-as-a-judge) chấm điểm độ liên quan (relevance) và độ trung thực (faithfulness) theo rubric định sẵn |
| Cảm nhận nhanh | Workflow (Kết hợp Script tự động hóa + LLM-as-a-judge) |

Quy trình nháp hiện tại:

```text
[Sửa Prompt trong Code]
          │
          ▼
[Mở Google Sheet test cases] ──(50 câu hỏi)
          │
          ▼
[Copy từng câu vào Web UI / Postman] ──(Tốn 45 phút)
          │
          ▼
[Đọc bằng mắt để chấm Đạt / Hỏng] ──(Tốn 90 phút, dễ hoa mắt)
          │
          ▼
[Tính tổng tỷ lệ pass trên Sheet]
          │
          ▼
[Gửi PM duyệt thủ công] ──> [Deploy Production]
```

---

### Problem Card #2

| Trường | Nội dung |
|---|---|
| Job Story | Khi bot/mô hình trả lời sai trên production và team CS/PM báo lỗi, tôi muốn nhanh chóng trace lại ngữ cảnh (input prompt, retrieved docs, latency, token cost), để giải thích lý do lỗi cho team kinh doanh mà không phải đào log thô (raw JSON). |
| Actor | AI Engineer, Customer Support (CS), Product Manager (PM) |
| Thời điểm / bối cảnh | Khi khách hàng phàn nàn và CS tạo ticket báo lỗi trên Slack/Jira (tần suất 3–5 lần/ngày) |
| Quy trình hiện tại (3–7 bước) | 1. CS chụp ảnh màn hình câu trả lời sai của bot gửi vào nhóm Slack kỹ thuật.<br>2. AI Engineer hỏi xin mã phiên chat (session_id) hoặc mốc thời gian chính xác.<br>3. AI Engineer đăng nhập vào CloudWatch hoặc Elasticsearch query log thô.<br>4. Đọc chuỗi JSON dài hàng trăm dòng để bóc tách prompt gốc, tài liệu RAG lấy về và câu trả lời mô hình sinh ra.<br>5. Xác định lỗi do khâu tìm kiếm tài liệu (retrieval) hay do mô hình tự bịa (hallucination).<br>6. Soạn tin nhắn giải thích nguyên nhân bằng ngôn ngữ phi kỹ thuật gửi lại cho CS. |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 3 và Bước 4 (Truy vấn log thô và đọc tách JSON thủ công), mất 20–30 phút cho mỗi sự vụ |
| Impact (nếu không giải thì sao) | Kỹ sư liên tục bị đứt mạch làm việc (context switching); phản hồi khiếu nại của khách hàng chậm trễ; không thống kê được lỗi nào lặp lại nhiều nhất |
| Success metric (baseline → target) | Thời gian tìm ra nguyên nhân mỗi ticket: từ 25 phút giảm xuống dưới 3 phút. Tỷ lệ ticket xác định được ngay nguyên nhân gốc: từ 20% lên 85% |
| Phương án không dùng AI | Dựng dashboard trực quan (Grafana/Kibana) liên kết theo session_id, tự format các trường JSON thành giao diện đọc rõ ràng cho CS tự tra cứu |
| Giả thuyết về AI (nếu có) | Tự động phân tích đoạn trace log bị gắn cờ lỗi bằng LLM để tóm tắt 2 dòng: nguyên nhân lỗi là gì và gợi ý câu trả lời sửa lại cho CS |
| Cảm nhận nhanh | Workflow (Dashboard tập trung log + Rule trích xuất dữ liệu) |

Quy trình nháp hiện tại:

```text
[Khách hàng phàn nàn] ──> [CS chụp màn hình gửi Slack]
                                    │
                                    ▼
                 [AI Engineer xin session_id / timestamp]
                                    │
                                    ▼
                 [Đăng nhập CloudWatch / DB query JSON thô] ──(Tốn 15 phút)
                                    │
                                    ▼
                 [Tự đọc raw JSON bóc tách prompt & docs] ──(Tốn 15 phút)
                                    │
                                    ▼
                 [Viết giải thích gửi lại Slack cho CS]
```

---

### Problem Card #3

| Trường | Nội dung |
|---|---|
| Job Story | Khi thử nghiệm nhiều phiên bản prompt khác nhau (system prompt, temperature, few-shot examples), tôi muốn quản lý version và so sánh output cạnh nhau (side-by-side diff), để biết phiên bản nào tối ưu nhất mà không bị thất lạc code. |
| Actor | AI Engineer, Prompt Engineer |
| Thời điểm / bối cảnh | Trong giai đoạn nghiên cứu, tối ưu hóa câu lệnh cho tính năng mới (diễn ra hàng ngày) |
| Quy trình hiện tại (3–7 bước) | 1. Kỹ sư nhân bản biến prompt trong code (prompt_v1, prompt_v2) hoặc sửa trực tiếp trong file text.<br>2. Chạy thử nghiệm trên terminal hoặc Jupyter Notebook để lấy kết quả của version mới.<br>3. Mở song song hai cửa sổ hoặc copy output ra Notepad để so sánh bằng mắt.<br>4. Đánh giá xem câu từ có mượt hơn không, có tuân thủ cấu trúc đầu ra hay không.<br>5. Nếu kết quả tốt thì commit code lên Git, nếu xấu hơn thì bấm undo (Ctrl+Z) hoặc xóa biến nháp. |
| Bottleneck (bước nào, mất bao nhiêu phút) | Bước 3 và Bước 4 (So sánh output thủ công bằng mắt và lưu trữ phân mảnh), mất 20–30 phút cho mỗi vòng lặp thử nghiệm |
| Impact (nếu không giải thì sao) | Dễ ghi đè mất phiên bản prompt tốt cũ; không nhớ được tham số nào (temperature, top_p) mang lại output tốt nhất; lãng phí chi phí token khi phải test đi test lại |
| Success metric (baseline → target) | Thời gian so sánh hai phiên bản: từ 25 phút giảm xuống dưới 2 phút. Tỷ lệ các lần thử nghiệm được lưu vết đầy đủ metadata: từ 10% lên 100% |
| Phương án không dùng AI | Dùng file cấu hình YAML/JSON kết hợp tính năng Git Diff tiêu chuẩn, hoặc một web UI nội bộ hiển thị 2 cột song song |
| Giả thuyết về AI (nếu có) | AI tự động highlight các điểm khác biệt về ngữ nghĩa giữa 2 output và tóm tắt prompt mới cải thiện được điều gì so với bản cũ |
| Cảm nhận nhanh | Rule / Workflow (Giao diện Playground lưu versioning) |

Quy trình nháp hiện tại:

```text
[Nhân bản biến prompt_v1 -> prompt_v2 trong code]
                         │
                         ▼
             [Chạy script lấy kết quả]
                         │
                         ▼
        [Copy output ra Notepad / Google Docs]
                         │
                         ▼
       [Nhìn bằng mắt so sánh giữa hai màn hình] ──(Tốn 20 phút)
                         │
                         ▼
  [Nếu ưng: Commit Git]  │  [Nếu không ưng: Bấm Ctrl+Z xóa code]
```

---

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
| Card #1 ban đầu định hướng làm Agent tự động toàn bộ là quá phức tạp, dễ gây trễ và khó kiểm soát chi phí. | Đồng ý | Hạ cấp độ giải pháp từ Agent xuống Workflow tự động hóa: Dùng script chạy hàng loạt kết hợp LLM-as-a-judge theo rubric cố định. |
| Baseline của Card #1 chỉ kiểm thử trên 50 câu test case là quá ít, không đủ đại diện cho các trường hợp biên (edge cases) ngoài thực tế. | Đồng ý | Đã cập nhật lại Target trong mục Success Metric: nâng quy mô bộ test tự động lên trên 200 câu và thêm kịch bản sinh dữ liệu thử nghiệm biên. |
| Card #2 chưa làm rõ vai trò của bên phi kỹ thuật (CS/PM), nếu chỉ giải quyết cho kỹ sư thì chưa tối ưu hết chuỗi giá trị. | Đồng ý | Đã bổ sung phương án Không dùng AI: xây dựng dashboard tra cứu tự phục vụ để CS có thể tự xem ngữ cảnh lỗi mà không cần tag kỹ sư. |
## 4. Tôi đã tham gia phần nào (CP3 → CP7)

**Vai trò chính:** phụ trách CP5 — quy trình trước/sau và Problem Statement v0; hỗ trợ CP4 theo [phân công nhóm](../../TEAM.md#phân-công-theo-checkpoint). Vũ Đức Anh hỗ trợ phần quy trình CP5. CP6 do Trương Văn Thông phụ trách, Nguyễn Đắc Thể hỗ trợ.

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | Chuẩn bị 3 card về kiểm thử model/prompt, truy vết lỗi và quản lý phiên bản prompt ở CP2. | Ba card được tổng hợp thành candidate #1–#3 trong báo cáo nhóm; candidate #1 vào shortlist. |
| Phản biện bài của bạn khác | Câu hỏi đối chiếu cho candidate #7 của Đức Anh: “Điểm nghẽn do tài liệu phân tán hay chưa đọc đúng thứ tự? Nếu dùng bảng đầu việc thủ công thì thời gian và số yêu cầu bỏ sót thay đổi thế nào?” Với candidate #4 của Thể: “Bước nhập chỉ chiếm 2/6 phút thì đạt mục tiêu 3 phút/đơn bằng cách nào?” | Câu hỏi #7 định hướng kiểm tra nguyên nhân nghẽn và thử No AI; phù hợp với kết luận pilot bảng tham chiếu ở CP6. Câu hỏi #4 yêu cầu đối chiếu mức tiết kiệm kỳ vọng với thời gian thực tế của bước nhập. Nguồn: [bảng 12 candidate, mục 2.1](../team/group_report.md#21-pitch); bảng ghi câu hỏi chuẩn bị, chưa xác định ai đã hỏi trực tiếp. |
| Nhận phản biện | Các câu hỏi dành cho card của tôi trong [bảng 12 candidate](../team/group_report.md#21-pitch): **#1:** “Nếu giữ cùng một bộ ca và tính cả thời gian người rà, mức tiết kiệm còn bao nhiêu? Dùng tiêu chí nào để phát hiện trường hợp mô hình chấm sai?” **#2:** “Log hiện có đủ mã phiên, prompt và tài liệu truy xuất không? Nếu trình bày log rõ hơn bằng dashboard thì còn bước nào cần AI?” **#3:** “Khó khăn chính là mất phiên bản hay đánh giá chất lượng đầu ra? Lưu metadata bằng Git và bảng kết quả đã đủ chưa?” | Điểm cần làm rõ: #1 đo trên cùng bộ ca và tính cả công người rà; #2 xác nhận dữ liệu log trước khi chọn cách xử lý; #3 tách lưu phiên bản khỏi đánh giá chất lượng, thử Git/bảng kết quả trước. Đây là các điểm cần rà từ câu hỏi chuẩn bị; chưa gán người hỏi hoặc khẳng định đã sửa card sau pitch. |
| Gom cluster / cây OST | Đối chiếu các card cá nhân với bảng cluster và cây OST do Nguyễn Đắc Thể tổng hợp. | [Mục 2.2](../team/group_report.md#22-cluster-và-chọn-top-3) xếp các card của tôi vào cluster A; [mục 2.3](../team/group_report.md#23-opportunity-solution-tree-rút-gọn) phân biệt pain dò chéo tài liệu với giải pháp. |
| Chọn candidate problem | Ba card cá nhân là đầu vào để so sánh; phần CP5 của tôi tiếp nối candidate #7 đã được nhóm chọn. | Bài nhóm chọn bài toán tra cứu yêu cầu lab; không tiếp tục triển khai bài toán eval cá nhân trong phạm vi lab này. |
| Kiểm chứng / research | Hỗ trợ CP4 theo phân công TEAM.md; dùng 2 snapshot và kết luận research của Đức Anh làm đầu vào CP5. Không ghi mình là người trực tiếp phỏng vấn. | [Mục 3.2](../team/group_report.md#32-kiểm-chứng) và hai snapshot hỗ trợ xác định phạm vi CP1–CP2; số 15–20 phút vẫn là tự thuật, chưa bấm giờ. |
| Quy trình nhóm | Phụ trách tổng hợp quy trình trước/sau ở CP5; mô tả actor, input, output, thời gian, handoff, bottleneck và fallback. | [Mục 4.1](../team/group_report.md#41-quy-trình-hiện-tại), [4.2](../team/group_report.md#42-quy-trình-tương-lai) và [4.3](../team/group_report.md#43-before--after) mô tả đủ các bước, HITL/fallback và bảng so sánh; tính cả công chuẩn bị, duyệt, sửa lỗi, giữ thời gian từng bước là ước lượng. |
| Problem Statement | Phụ trách tổng hợp v0 theo 6 trường và các điểm cần rà về baseline, metric, boundary. | [Mục 5 — v0](../team/group_report.md#5-problem-statement-v0-cp5) tạo đầu vào cho [mục 7 — v1](../team/group_report.md#7-problem-statement-v1--tiêu-chí-đánh-giá-cp6); baseline tự thuật 15–20 phút tách khỏi target pilot chưa đo. |
| Mức can thiệp AI | Đóng góp quy trình và phân tích chi phí kiểm duyệt ở CP5; CP6 do Thông phụ trách, Thể hỗ trợ. | [Mục 6.2](../team/group_report.md#62-so-sánh-4-mức) chọn No AI cho pilot; v1 không có điểm can thiệp AI. Phương án Rule/Workflow ở CP5 chỉ để so sánh, chưa triển khai. |
| Quyết định | Cung cấp metric, boundary và phương án quay về trong CP5 làm đầu vào đánh giá của nhóm. | [Mục 8.2](../team/group_report.md#82-kết-luận) đề xuất Go cho pilot ≥3 học viên ngoài nhóm; dừng nếu trung vị >8 phút/người, tổng công sức >40 người-phút/nhóm 4 người hoặc có 1 lỗi nghiêm trọng. Quyết định còn chờ nhóm xác nhận trước khi thực hiện. |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | Chưa có nhật ký đủ để xác nhận mức hỗ trợ ở CP1. | Không bổ sung nội dung dùng AI khi chưa có ghi chép. | Không có ghi nhận cụ thể. | Giữ các vấn đề đã có; các con số là mô tả cá nhân, không bổ sung bằng chứng giả. |
| CP2 Problem Card | Phản biện phạm vi và phương án trong các card theo bảng cuối mục 3. | Nêu vấn đề độ phức tạp của Agent, độ tin cậy khi chấm và cách CS tra cứu. | Tăng số ca lên hơn 200 không tự chứng minh tập ca đại diện; chỉ đổi target chưa giải quyết chất lượng eval. | Cần bổ sung nhóm ca thường gặp/ca biên và so kết quả với người chấm; đây là việc tiếp theo, chưa có kết quả thực nghiệm. |
| CP4 Research | Dùng kết quả research có sẵn trong báo cáo nhóm để đối chiếu quy trình CP5. | So sánh hướng bảng thủ công, Rule và Workflow. | Một số claim trong research như script chính xác 100% hoặc chạy dưới 1 giây chưa có phép đo của nhóm. | Không dùng các claim đó làm kết quả kiểm chứng; vẫn yêu cầu người rà nguồn và ghi thời gian thực tế. |
| CP5 Quy trình | Hỗ trợ tổng hợp, trình bày và phản biện quy trình từ worksheet và CP4. | Tách Rule/AI/con người, công chuẩn bị chung, boundary và fallback. | Mốc 15–20 phút chưa thống nhất cách ghi; thời gian duyệt 3 phút và target 8 phút chưa đo. | Bản CP5 phân biệt tự thuật, ước lượng và target; cần bấm giờ lại trước khi kết luận hiệu quả. |
| CP5–6 Problem Statement | Hỗ trợ soạn và phản biện v0; đối chiếu với v1 trong báo cáo nhóm mới nhất. | Chỉ ra baseline chưa vững, mẫu nhỏ, chi phí người duyệt và việc chưa chứng minh cần AI. | Đầu ra nháp không thay thế việc nhóm tự xác nhận nội dung hoặc bằng chứng pilot. | V1 của nhóm chọn No AI, giới hạn CP1–CP2 và ghi tiêu chí đo; không coi đây là kết quả đã đạt. |
| CP6 Mức can thiệp / quyết định | Đối chiếu báo cáo cá nhân với kết luận CP6 đã được Thông và Thể tổng hợp. | Làm rõ Go chỉ áp dụng cho pilot, cùng ngưỡng dừng và cách quay về nguồn. | Dễ nhầm No AI của giải pháp với việc không dùng AI hỗ trợ làm báo cáo. | Nhật ký này vẫn ghi việc hỗ trợ soạn/phản biện; giải pháp pilot được chọn không có điểm can thiệp AI. |

---

## 6. Reflection (CP7)


**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**

Từ bảng tổng hợp candidate, điều tôi rút ra là vấn đề có tác động lớn chưa chắc phù hợp nhất để làm trong một buổi lab. Card kiểm thử model/prompt của tôi có bước chấm thủ công tốn thời gian, nhưng còn phụ thuộc bộ ca, đáp án và độ tin cậy của người chấm. Bài toán tra cứu yêu cầu lab có nguồn ngay trong repo và tiếp cận được người cùng bối cảnh, nên thuận lợi hơn cho việc kiểm chứng. Điều này giúp tôi hiểu vì sao nhóm ưu tiên một vấn đề có thể kiểm chứng ngay trong lớp.

**6.2. Nhóm có lúc nào bị "solution-first" không? Lúc đó nhóm nhận ra và xử lý thế nào?**

Phần quy trình tương lai ở CP5 có phương án dùng Rule gom yêu cầu và AI tóm tắt hướng dẫn. Tuy nhiên, hai cuộc phỏng vấn mới cho thấy học viên phải dò chéo tài liệu, chưa cho thấy họ cần AI để giải quyết việc đó. CP6 vì thế chọn thử bảng tham chiếu No AI trước. Từ điểm này, tôi rút ra rằng phải kiểm tra cách tổ chức thông tin đơn giản đã đủ chưa, rồi mới cân nhắc thêm công cụ.

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

Một thay đổi đã ghi trong CP2 là thu hẹp phương án kiểm thử từ Agent sang Workflow gồm script chạy ca thử, bước chấm theo rubric và người duyệt. Câu hỏi dành cho candidate #1 trong bảng nhóm còn chỉ ra một điểm cần rà: nếu giữ cùng bộ ca và tính cả thời gian người kiểm tra thì mức tiết kiệm thực sự là bao nhiêu? Khi tổng hợp CP5, tôi dùng cùng cách xem xét đó để tính cả công chuẩn bị và duyệt bảng. Mục tiêu nhanh hơn chỉ có ý nghĩa khi so cùng phạm vi công việc.

**6.4. Kết quả kiểm chứng có làm tôi bất ngờ không? Điều gì?**

Điểm đáng chú ý trong hai snapshot là học viên chỉ đọc README khoảng 5–6 phút rồi vẫn phải quay lại đối chiếu Rubric và Rules trong lúc làm. Vấn đề vì thế không chỉ là đọc hiểu đầu buổi mà còn là tìm đúng điều kiện ở từng mục. Hai người cùng nêu khoảng 15–20 phút hỗ trợ nhận diện hành vi, nhưng cách ghi thời gian chưa đủ rõ để coi là phép đo chính xác.

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

Trong phần CP5 tôi phụ trách, điểm khó là mô tả rõ vấn đề mà chưa chốt sẵn giải pháp. Chẳng hạn, “phải dò chéo nhiều file để biết đủ yêu cầu” là bước nghẽn; “cần bảng tổng hợp bằng AI” đã là một phương án xử lý. Phần metric cũng cần tách khoảng 15–20 phút do người được hỏi tự ước lượng, 7 phút mô hình hóa cho bước nghẽn và target muốn thử. Boundary phải chỉ ra ai duyệt, kiểm nội dung gì và khi nào quay về nguồn gốc.

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

Tôi sẽ đề xuất thống nhất phạm vi đo ngay trước phỏng vấn: tổng thời gian đọc–đối chiếu CP1–CP2 hay riêng thời gian chuyển qua lại tài liệu. Tôi cũng sẽ ghi rõ từng câu hỏi phản biện, người hỏi và thay đổi sau đó để tránh thiếu bằng chứng đóng góp cá nhân. Khi so giải pháp, cần thử bảng thủ công trước, đo cả công chuẩn bị, sửa lỗi và quay về nguồn rồi mới cân nhắc Rule hoặc Workflow.

**6.7. Hiểu bài — bản giải thích tham khảo để tự luyện, chưa phải kiểm tra không nhìn tài liệu:**

Bài toán của nhóm là học viên K5-L3A phải dò chéo nhiều file để xác định đủ nhiệm vụ, vị trí điền và điều kiện chấm khi làm CP1–CP2. Quy trình hiện tại đi từ đọc README, tìm checkpoint, đọc worksheet đến đối chiếu Rubric/Rules và lập đầu việc. Bottleneck nằm ở bước đối chiếu; khoảng 15–20 phút là số tự thuật cho lượt đọc–tra cứu, còn 7 phút riêng bước nghẽn là ước lượng. Pilot đặt mục tiêu trung vị không quá 8 phút/người và tổng công sức nhóm 4 người không quá 40 người-phút, tính cả chuẩn bị và duyệt. Bảng phải có nguồn, phiên bản và người kiểm tra; thiếu hoặc mâu thuẫn thì quay về tài liệu gốc. Nhóm chọn No AI vì chưa chứng minh Rule hay AI cần thiết hơn bảng tham chiếu thủ công. Quyết định là Go cho pilot ít nhất 3 học viên ngoài nhóm; vượt ngưỡng thời gian/công sức hoặc xuất hiện lỗi nghiêm trọng thì dừng và sửa trước khi thử lại.

---

## 7. Tài liệu tham khảo

- [Worksheet — CP5](../../docs/01-worksheet.md#cp5--quy-trình-trướcsau--problem-statement-v0-45--define).
- [Yêu cầu checkpoint](../../CHECKPOINTS.md).
- [Rubric — C8 và C9](../../RUBRIC.md).
- [Quy định dùng AI](../../RULES.md#2-ai-và-công-cụ).
- [TEAM.md — phân công và bằng chứng đóng góp](../../TEAM.md#dinhthihuong-2a202603569).
- [Bảng 12 candidate và câu hỏi chuẩn bị phản biện](../team/group_report.md#21-pitch).
- [Báo cáo nhóm — CP4, CP5 và kết luận CP6](../team/group_report.md).
- [Problem Statement v1 và tiêu chí đánh giá](../team/group_report.md#7-problem-statement-v1--tiêu-chí-đánh-giá-cp6).
- [Quyết định, pilot và ngưỡng dừng](../team/group_report.md#82-kết-luận).
- [Interview Snapshot #1 — Vũ Đức Anh](../assets/cp4-interview-snapshot-1.md).
- [Interview Snapshot #2 — Vũ Đức Anh](../assets/cp4-interview-snapshot-2.md).
