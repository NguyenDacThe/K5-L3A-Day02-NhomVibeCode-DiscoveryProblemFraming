# Team

> Điền file này trên repo chung do nhóm trưởng fork. Nhóm điền phần **Thông tin nhóm** và **Thành viên**. Mỗi người tự điền phần của mình trong **Cá nhân**. Không copy file này sang repo khác.

## Thông tin nhóm

- Tên nhóm: VibeCode
- Candidate problem nhóm chọn (1 câu): Học viên K5-L3A mất thời gian tra cứu và đối chiếu yêu cầu đầu buổi lab vì nhiệm vụ, vị trí điền và tiêu chí chấm nằm ở nhiều tài liệu.
- Quyết định cuối (Go / Not Yet / No-Go): **Go — đề xuất pilot nhỏ có kiểm soát với bảng tham chiếu No AI cho CP1–CP2; chưa triển khai rộng.**

## Thành viên

| STT | Họ và tên      | MSSV        | Vai trò trong nhóm                                                            | Tài khoản GitHub |
| --: | -------------- | ----------- | ----------------------------------------------------------------------------- | ---------------- |
|   1 | Nguyễn Đắc Thể | 2A202603529 | Phụ trách CP3 — Hội tụ nhóm; hỗ trợ CP6 | NguyenDacThe |
|   2 | Vũ Đức Anh     | 2A202603573 | Phụ trách CP4 — Kiểm chứng (phỏng vấn) & Research giải pháp đã có; hỗ trợ CP3 | ducanh005         |
| 3 | Đinh Thị Hường | 2A202603569 | Phụ trách CP5 — quy trình trước/sau và tổng hợp Problem Statement v0 | dihnhuonq130104 |
| 4 | Trương Văn Thông | 2A202603560 | Phụ trách CP6 — mức can thiệp, Problem Statement v1, tiêu chí đánh giá và quyết định | thongthong2k41306-beep|

Không ghi email hay số điện thoại vào bảng này, vì repo có thể để public.

Gợi ý vai trò (một người có thể giữ nhiều vai): điều phối thời gian, ghi chép, người phản biện chính, phụ trách kiểm chứng (phỏng vấn/survey), phụ trách research, vẽ quy trình, viết Problem Statement.

## Phân công theo checkpoint

| Checkpoint                                 | Người chính    | Người hỗ trợ     | Sản phẩm                                                                                          |
| ------------------------------------------ | -------------- | ---------------- | ------------------------------------------------------------------------------------------------- |
| CP3 — Hội tụ nhóm                          | Nguyễn Đắc Thể | Vũ Đức Anh       | Tổng hợp 12 candidate, cluster, shortlist 3 candidate, cây OST, bảng chấm điểm và lý do chọn/loại |
| CP4 — Kiểm chứng                           | Vũ Đức Anh     | Đinh Thị Hường   | Assumption map, phỏng vấn Mom Test (2 học viên nhóm khác), Interview Snapshots (`cp4-interview-snapshot-1.md`, `cp4-interview-snapshot-2.md`) |
| CP4 — Research                             | Vũ Đức Anh     | Trương Văn Thông | Bảng research 4 giải pháp/pattern có link kiểm chứng và kết luận sửa problem                      |
| CP5 — Quy trình trước/sau | Đinh Thị Hường | Vũ Đức Anh | Mục 4: quy trình, before/after, HITL, boundary và fallback |
| CP5 — Problem Statement v0 | Đinh Thị Hường| | Mục 5: bản đề xuất v0 và phản biện AI |
| CP6 — Mức can thiệp + Problem Statement v1 | Trương Văn Thông | Nguyễn Đắc Thể | Mục 6–7: ma trận, so sánh 4 mức, lựa chọn No AI, giải thích AI Canvas/PAIR không áp dụng, Problem Statement v1 và 5 tiêu chí đánh giá |
| CP6 — Quyết định | Trương Văn Thông | Nguyễn Đắc Thể | Mục 8: đánh giá 4 rủi ro, Go cho pilot nhỏ, kế hoạch đo, ngưỡng dừng và phương án quay về |

## Cá nhân

Mỗi thành viên thêm một mục theo mẫu dưới đây, tiêu đề là `HoVaTen-MSSV`.

### NguyenDacThe-2A202603529

**Phần việc phụ trách:**

- CP3 — Hội tụ nhóm; tổng hợp và hoàn thiện mục 2 của báo cáo nhóm.
- Hỗ trợ Trương Văn Thông hoàn thiện CP6, rà soát sự nhất quán giữa CP4–CP5 và phần lựa chọn mức can thiệp, metric, rủi ro, quyết định.

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Phụ trách tổng hợp 12 candidate từ 3 Problem Cards của mỗi thành viên, kèm actor và bottleneck.
- Chuẩn bị câu hỏi phản biện cho các candidate; gom cluster và lập shortlist 3 candidate.
- Hoàn thiện cây Opportunity Solution Tree, bảng chấm điểm theo 7 tiêu chí và lý do chọn/loại candidate.
- Tổng hợp lựa chọn candidate #7 — Tra cứu và đối chiếu yêu cầu đầu buổi lab để chuyển sang bước kiểm chứng.
- Hỗ trợ rà soát nội dung CP6 và tổng hợp vào báo cáo chung: lựa chọn No AI cho pilot, phân biệt baseline tự thuật với target, kiểm tra tiêu chí đánh giá và ngưỡng dừng.

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- [Mục 2.1 — Tổng hợp candidate và câu hỏi chuẩn bị phản biện](report/team/group_report.md#21-pitch).
- [Mục 2.2 — Cluster và chọn top 3](report/team/group_report.md#22-cluster-và-chọn-top-3).
- [Mục 2.3 — Opportunity Solution Tree](report/team/group_report.md#23-opportunity-solution-tree-rút-gọn).
- [Mục 2.4 — Chấm điểm shortlist và lựa chọn candidate](report/team/group_report.md#24-chấm-điểm-shortlist-15).
- [Mục 6 — Hỗ trợ rà soát mức can thiệp](report/team/group_report.md#6-mức-can-thiệp-ai-cp6).
- [Mục 7 — Hỗ trợ rà soát v1 và tiêu chí đánh giá](report/team/group_report.md#7-problem-statement-v1--tiêu-chí-đánh-giá-cp6).
- [Mục 8 — Hỗ trợ rà soát quyết định và ngưỡng dừng](report/team/group_report.md#8-quyết-định-cp6).

**Điều mình học được từ phần nhóm:**

- Khi tổng hợp 12 candidate và chọn shortlist, mình học được rằng lựa chọn vấn đề cần dựa vào actor, quy trình, bằng chứng và khả năng kiểm chứng, thay vì chỉ chọn ý tưởng nghe hấp dẫn. Candidate #7 phù hợp để nhóm đào sâu vì có tài liệu sẵn và có thể tiếp cận học viên ngoài nhóm để hỏi về trải nghiệm thực tế.
- Khi xây cây OST, mình hiểu cách phân biệt opportunity với solution: việc phải dò chéo nhiều file để biết đủ yêu cầu là pain, còn chatbot hoặc checklist tự động là phương án giải quyết. Tách rõ hai phần giúp nhóm cân nhắc nhiều hướng trước khi chọn công nghệ.
- Khi hỗ trợ CP6, mình thấy cần phân biệt số liệu tự thuật, thời gian ước lượng và mục tiêu thử nghiệm. Khoảng 15–20 phút trong hai snapshot chưa phải kết quả bấm giờ; mục tiêu trung vị không quá 8 phút/người và tổng không quá 40 người-phút/nhóm cũng chưa phải hiệu quả đã đạt. Khi đo phải tính cả thời gian chuẩn bị, duyệt, sửa bảng và quay lại nguồn.
- Mình học được rằng có vấn đề thật không đồng nghĩa cần dùng AI. Nhóm có thể chọn bảng tham chiếu No AI để thử trước; chỉ xem xét Rule hoặc Workflow khi có bằng chứng phương án đơn giản chưa đủ. Quyết định Go cho pilot cần có người phụ trách, tiêu chí đạt/không đạt và ngưỡng dừng cụ thể.

### VuDucAnh-2A202603573

**Phần việc phụ trách:**

- Đề xuất Candidate #7 (bài toán được nhóm chọn ở CP3) và hỗ trợ hội tụ nhóm ở CP3.
- Phụ trách chính CP4 — Kiểm chứng (Assumption Map, phỏng vấn theo _The Mom Test_, tổng hợp tín hiệu xác nhận/phản bác) và Research giải pháp đã có (Mục 3 trong `group_report.md`).

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Xây dựng bảng Assumption Map gồm 6 giả định phân loại theo Value, Usability, Feasibility, Viability và xác định 4 giả định ưu tiên kiểm chứng.
- Thiết kế bộ 4 câu hỏi phỏng vấn tuân thủ _The Mom Test_, trực tiếp phỏng vấn 2 học viên nhóm khác trong lớp K5-L3A, lập bảng Interview Snapshot #1 và #2 và phân tích tín hiệu xác nhận / phản bác để điều chỉnh phạm vi bottleneck của nhóm.
- Thực hiện Research 4 công cụ/pattern thực tế (Google NotebookLM, GitHub Copilot Repository Context, Diátaxis Documentation Framework, Unified/Remark Markdown AST) kèm kiểm tra link sống và rút ra kết luận chuyển hướng từ "tự xây công cụ AI" sang quy trình bán thủ công kết hợp bảng Cheatsheet/Rule và công cụ có sẵn.

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- [Mục 3.1 — Assumption Map](report/team/group_report.md#31-assumption-map).
- [Mục 3.2 — Kiểm chứng và điều chỉnh problem](report/team/group_report.md#32-kiểm-chứng).
- [Mục 3.3 — Research giải pháp đã có](report/team/group_report.md#33-research-giải-pháp-đã-có).
- File ghi chú phỏng vấn chi tiết: [report/assets/cp4-interview-snapshot-1.md](report/assets/cp4-interview-snapshot-1.md), [report/assets/cp4-interview-snapshot-2.md](report/assets/cp4-interview-snapshot-2.md).

**Điều mình học được từ phần nhóm:**

- Khi đưa problem cá nhân ra nhóm phản biện và đi phỏng vấn người thật ở nhóm khác, mình nhận ra giả định ban đầu ("ai cũng ngồi đọc một mạch 25 phút đầu giờ") chưa sát thực tế bằng việc học viên chỉ đọc `README.md` 5–6 phút rồi mất 15–20 phút mở qua mở lại giữa `RUBRIC.md` và `RULES.md` vì sợ sót yêu cầu nhỏ. Nhờ kiểm chứng và research, nhóm tránh được bẫy tự xây chatbot/Agent thừa thãi.

### DinhThiHuong-2A202603569

**Phần việc phụ trách:**

- Phụ trách tổng hợp CP5 theo worksheet và kết quả kiểm chứng CP4.

**Đóng góp cụ thể:**

- Đối chiếu CP5 với [snapshot #1](report/assets/cp4-interview-snapshot-1.md) và [snapshot #2 của Đức Anh](report/assets/cp4-interview-snapshot-2.md); phân biệt số tự thuật, thời gian phân bổ ước lượng và mục tiêu pilot.
- Tổng hợp nội dung CP5 trên bản báo cáo nhóm từ nhánh `DucAnh` (commit `143e664`), đồng bộ asset và các file liên quan.
- Phần việc CP5 gồm quy trình trước/sau, actor/input/output, thời gian ước lượng, handoff, bước người kiểm tra, boundary, phương án quay về và bảng before/after.
- Tổng hợp Problem Statement v0 và các điểm cần rà về baseline, chi phí duyệt, mẫu kiểm chứng và nhu cầu AI để nhóm chốt.

**Bằng chứng:**

- [Báo cáo nhóm mục 4–5](report/team/group_report.md#4-quy-trình-trướcsau-cp5).
- [Báo cáo cá nhân mục 4–5](report/individual/2A202603569_DinhThiHuong.md#5-dùng-ai).

**Điều mình học được từ phần nhóm:**

- Qua phần CP5, mình thấy cần phân biệt rõ số liệu phỏng vấn, thời gian ước lượng và mục tiêu muốn đạt. Hai người được phỏng vấn đều nêu khoảng 15–20 phút, nhưng cách ghi chưa thống nhất đó là tổng thời gian hay riêng phần dò lại tài liệu, nên chưa thể coi đây là baseline đã đo chính xác.
- Khi so sánh quy trình trước/sau, phải tính cả thời gian chuẩn bị bảng chung, kiểm tra và sửa lỗi. Nếu chỉ tính thời gian học viên tra cứu thì dễ đánh giá quá cao mức tiết kiệm.
- Không phải cứ có nhiều tài liệu là cần dùng AI. Với các yêu cầu cố định như tên file, điểm số và quy định dùng công cụ, bảng tham chiếu hoặc Rule có thể đã đủ; nếu thêm AI thì vẫn cần người đối chiếu nguồn và có cách quay về khi đầu ra sai.

### TruongVanThong-2A202603560

**Phần việc phụ trách:**

- Phụ trách chính CP6 — mức can thiệp, Problem Statement v1, tiêu chí đánh giá và quyết định.
- Người hỗ trợ: Nguyễn Đắc Thể.

**Đóng góp cụ thể:**

- Tổng hợp dữ liệu CP4 và quy trình CP5 để xác định phạm vi CP1–CP2, đánh giá độ mơ hồ và độ phức tạp của bài toán.
- So sánh No AI / Rule / Workflow / Agent; lựa chọn pilot bảng tham chiếu thủ công có nguồn và người duyệt, giải thích vì sao chưa cần Rule/AI và vì sao không chọn Agent.
- Hoàn thiện mục AI Canvas và hai câu hỏi PAIR theo trường hợp No AI: không có đầu ra AI, đồng thời làm rõ việc con người đối chiếu, quyết định và phản hồi để sửa bảng.
- Viết Problem Statement v1 đủ 9 trường và bảng thay đổi so với v0; giữ rõ baseline tự thuật 15–20 phút/người và target pilot chưa được đo.
- Xây dựng 5 tiêu chí đánh giá bảng tham chiếu: đúng/đủ, truy về nguồn, thời gian tra cứu, tổng công sức và kiểm soát phiên bản/lỗi nghiêm trọng.
- Đánh giá Value / Usability / Feasibility / Viability; tổng hợp quyết định Go cho pilot nhỏ, kế hoạch thử với ít nhất 3 học viên ngoài nhóm và ngưỡng dừng.
- Ghi rõ bước tiếp theo là xác nhận quyết định, chuẩn bị bảng và đo pilot; chưa báo cáo pilot đã thực hiện hoặc hiệu quả đã đạt.

**Bằng chứng:**

- [Mục 6 — Mức can thiệp AI và lựa chọn No AI](report/team/group_report.md#6-mức-can-thiệp-ai-cp6).
- [Mục 7 — Problem Statement v1 và tiêu chí đánh giá](report/team/group_report.md#7-problem-statement-v1--tiêu-chí-đánh-giá-cp6).
- [Mục 8 — Bốn rủi ro, quyết định, pilot và ngưỡng dừng](report/team/group_report.md#8-quyết-định-cp6).
- [Mục 9 — Hạn chế và hướng tiếp theo](report/team/group_report.md#9-hạn-chế-và-hướng-tiếp-theo).
- Commit `c9a3d93` — `cp6`, trên nhánh `TruongVanThong`.

**Điểm rút ra từ phân tích CP6:**

- Pain dò chéo tài liệu chưa chứng minh nhu cầu AI; cần kiểm tra bảng No AI trước khi tăng mức can thiệp.
- Baseline tự thuật, thời gian phân bổ ước lượng và mục tiêu pilot phải được trình bày riêng. Tổng công sức phải tính cả thời gian chuẩn bị và duyệt bảng.
- Go cho pilot nhỏ là quyết định thử nghiệm có giới hạn, đi kèm tiêu chí đúng/sai và ngưỡng dừng; không đồng nghĩa được triển khai rộng.
