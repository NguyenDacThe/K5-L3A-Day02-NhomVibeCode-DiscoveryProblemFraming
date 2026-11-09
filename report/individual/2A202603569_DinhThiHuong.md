# Báo cáo cá nhân — 2A202603569_DinhThiHuong

> Đổi tên file theo quy tắc `MSSV_HoTen.md`, ví dụ `20241234_NguyenVanAn.md` (MSSV trước, dấu `_`, họ tên viết liền không dấu). Sửa cả dòng tiêu đề phía trên cho khớp.
> Template chi tiết và prompt mẫu cho từng mục: [docs/01-worksheet.md](../../docs/01-worksheet.md).
> Mỗi thành viên một file trong `report/individual/` trên repo nhóm: copy template này thành file mới, điền, rồi commit bằng tài khoản GitHub của bạn. Không viết hộ người khác.

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

### Card muốn pitch nhất

- Card số: Card #1 (Tự động benchmark và đánh giá LLM/Prompt trên tập golden dataset)
- Vì sao: Đây là bài toán sống còn với bất kỳ sản phẩm AI nào trước khi đưa ra người dùng. Hiện tại việc đánh giá đa số làm bằng mắt và cảm tính nên tốc độ ra mắt tính năng rất chậm. Bài toán này có ranh giới rõ ràng, dễ đo lường bằng con số cụ thể, và nhóm có thể tận dụng nhiều thư viện mã nguồn mở có sẵn để dựng giải pháp hoàn chỉnh trong các checkpoint sau.
- Câu hỏi muốn nhóm phản biện:
  1. Chi phí gọi API mô hình để thẩm định tự động (LLM-as-a-judge) có bị đội lên quá cao khi tập test case mở rộng lên 500-1000 câu không?
  2. Trong trường hợp mô hình đánh giá và mô hình được đánh giá cùng gặp một loại ảo giác (bias chung), làm thế nào để phát hiện ra sai sót mà không cần người can thiệp?

---

### AI đã phản biện card thế nào

| Điểm yếu AI chỉ ra | Đồng ý? | Đã sửa gì |
|---|---|---|
| Card #1 ban đầu định hướng làm Agent tự động toàn bộ là quá phức tạp, dễ gây trễ và khó kiểm soát chi phí. | Đồng ý | Hạ cấp độ giải pháp từ Agent xuống Workflow tự động hóa: Dùng script chạy hàng loạt kết hợp LLM-as-a-judge theo rubric cố định. |
| Baseline của Card #1 chỉ kiểm thử trên 50 câu test case là quá ít, không đủ đại diện cho các trường hợp biên (edge cases) ngoài thực tế. | Đồng ý | Đã cập nhật lại Target trong mục Success Metric: nâng quy mô bộ test tự động lên trên 200 câu và thêm kịch bản sinh dữ liệu thử nghiệm biên. |
| Card #2 chưa làm rõ vai trò của bên phi kỹ thuật (CS/PM), nếu chỉ giải quyết cho kỹ sư thì chưa tối ưu hết chuỗi giá trị. | Đồng ý | Đã bổ sung phương án Không dùng AI: xây dựng dashboard tra cứu tự phục vụ để CS có thể tự xem ngữ cảnh lỗi mà không cần tag kỹ sư. |
## 4. Tôi đã tham gia phần nào (CP3 → CP7)

| Hoạt động | Tôi đã làm gì? | Kết quả / ảnh hưởng tới bài nhóm |
|---|---|---|
| Pitch Problem Card | | |
| Phản biện bài của bạn khác | Câu hỏi tôi đã đặt: | |
| Nhận phản biện | Câu hỏi tôi nhận được: | Tôi đã sửa gì: |
| Gom cluster / cây OST | | |
| Chọn candidate problem | | |
| Kiểm chứng / research | | |
| Quy trình nhóm | | |
| Problem Statement | | |
| Mức can thiệp AI | | |
| Quyết định | | |

---

## 5. Dùng AI

| Checkpoint | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai hoặc hời hợt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| CP1 Scan | | | | |
| CP2 Problem Card | | | | |
| CP4 Research | | | | |
| CP5 Quy trình | | | | |
| CP5–6 Problem Statement | | | | |
| CP6 Mức can thiệp / quyết định | | | | |

---

## 6. Reflection (CP7)

Trả lời bằng trải nghiệm thật của bạn, tối thiểu 200 từ cho các câu 6.1–6.6 (không tính 6.7, câu này được chấm riêng ở tiêu chí C5). **Không dùng AI để viết thay.**

**6.1. Tôi học được gì khi nghe top 3 problems của các bạn khác?**

**6.2. Nhóm có lúc nào bị "solution-first" (nghĩ giải pháp trước khi hiểu vấn đề) không? Lúc đó nhóm nhận ra và xử lý thế nào?**

**6.3. Tôi có đổi ý sau khi bị phản biện không? Kể một lần cụ thể.**

**6.4. Kết quả kiểm chứng (phỏng vấn/survey/research) có làm tôi bất ngờ không? Điều gì?**

**6.5. Điều khó nhất khi viết Problem Statement là gì?**

**6.6. Nếu làm lại, tôi sẽ đổi gì? Tôi sẽ phản biện nhóm mạnh hơn ở điểm nào?**

**6.7. Hiểu bài:** giải thích bằng 5–8 câu, không nhìn tài liệu, chuỗi *problem → quy trình → metric → boundary → mức can thiệp AI → quyết định* của bài nhóm mình.

---

## 7. Tài liệu tham khảo

-
