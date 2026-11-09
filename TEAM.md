# Team

> Điền file này trên repo chung do nhóm trưởng fork. Nhóm điền phần **Thông tin nhóm** và **Thành viên**. Mỗi người tự điền phần của mình trong **Cá nhân**. Không copy file này sang repo khác.

## Thông tin nhóm

- Tên nhóm: VibeCode
- Candidate problem nhóm chọn (1 câu): Học viên K5-L3A mất thời gian tra cứu và đối chiếu yêu cầu đầu buổi lab vì nhiệm vụ, vị trí điền và tiêu chí chấm nằm ở nhiều tài liệu.
- Quyết định cuối (Go / Not Yet / No-Go):

## Thành viên

| STT | Họ và tên      | MSSV        | Vai trò trong nhóm                                                            | Tài khoản GitHub |
| --: | -------------- | ----------- | ----------------------------------------------------------------------------- | ---------------- |
|   1 | Nguyễn Đắc Thể | 2A202603529 | Phụ trách CP3 — Hội tụ nhóm                                                   | NguyenDacThe     |
|   2 | Vũ Đức Anh     | 2A202603573 | Phụ trách CP4 — Kiểm chứng (phỏng vấn) & Research giải pháp đã có; hỗ trợ CP3 | DucAnhVu         |
|   3 |                |             |                                                                               |                  |
|   4 |                |             |                                                                               |                  |

Không ghi email hay số điện thoại vào bảng này, vì repo có thể để public.

Gợi ý vai trò (một người có thể giữ nhiều vai): điều phối thời gian, ghi chép, người phản biện chính, phụ trách kiểm chứng (phỏng vấn/survey), phụ trách research, vẽ quy trình, viết Problem Statement.

## Phân công theo checkpoint

| Checkpoint                                 | Người chính    | Người hỗ trợ     | Sản phẩm                                                                                          |
| ------------------------------------------ | -------------- | ---------------- | ------------------------------------------------------------------------------------------------- |
| CP3 — Hội tụ nhóm                          | Nguyễn Đắc Thể | Vũ Đức Anh       | Tổng hợp 12 candidate, cluster, shortlist 3 candidate, cây OST, bảng chấm điểm và lý do chọn/loại |
| CP4 — Kiểm chứng                           | Vũ Đức Anh     | Đinh Thị Hường   | Assumption map, phỏng vấn Mom Test, Interview Snapshot (`cp4-interview-snapshot-1.md`)            |
| CP4 — Research                             | Vũ Đức Anh     | Trương Văn Thông | Bảng research 4 giải pháp/pattern có link kiểm chứng và kết luận sửa problem                      |
| CP5 — Quy trình trước/sau                  |                |                  | Quy trình + bảng before/after                                                                     |
| CP5 — Problem Statement v0                 |                |                  | Problem Statement v0                                                                              |
| CP6 — Mức can thiệp + Problem Statement v1 |                |                  | Ma trận, AI Canvas, eval, Problem Statement v1                                                    |
| CP6 — Quyết định                           |                |                  | 4 rủi ro + Go/Not Yet/No-Go                                                                       |

## Cá nhân

Mỗi thành viên thêm một mục theo mẫu dưới đây, tiêu đề là `HoVaTen-MSSV`.

### NguyenDacThe-2A202603529

**Phần việc phụ trách:**

- CP3 — Hội tụ nhóm; tổng hợp và hoàn thiện mục 2 của báo cáo nhóm.

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Phụ trách tổng hợp 12 candidate từ 3 Problem Cards của mỗi thành viên, kèm actor và bottleneck.
- Chuẩn bị câu hỏi phản biện cho các candidate; gom cluster và lập shortlist 3 candidate.
- Hoàn thiện cây Opportunity Solution Tree, bảng chấm điểm theo 7 tiêu chí và lý do chọn/loại candidate.
- Tổng hợp lựa chọn candidate #7 — Tra cứu và đối chiếu yêu cầu đầu buổi lab để chuyển sang bước kiểm chứng.

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- [Mục 2.1 — Tổng hợp candidate và câu hỏi chuẩn bị phản biện](report/team/group_report.md#21-pitch).
- [Mục 2.2 — Cluster và chọn top 3](report/team/group_report.md#22-cluster-và-chọn-top-3).
- [Mục 2.3 — Opportunity Solution Tree](report/team/group_report.md#23-opportunity-solution-tree-rút-gọn).
- [Mục 2.4 — Chấm điểm shortlist và lựa chọn candidate](report/team/group_report.md#24-chấm-điểm-shortlist-15).

**Điều mình học được từ phần nhóm:**

-

### VuDucAnh-2A202603573

**Phần việc phụ trách:**

- Đề xuất Candidate #7 (bài toán được nhóm chọn ở CP3) và hỗ trợ hội tụ nhóm ở CP3.
- Phụ trách chính CP4 — Kiểm chứng (Assumption Map, phỏng vấn theo _The Mom Test_, tổng hợp tín hiệu xác nhận/phản bác) và Research giải pháp đã có (Mục 3 trong `group_report.md`).

**Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- Xây dựng bảng Assumption Map gồm 6 giả định phân loại theo Value, Usability, Feasibility, Viability và xác định 4 giả định ưu tiên kiểm chứng.
- Thiết kế bộ 4 câu hỏi phỏng vấn tuân thủ _The Mom Test_, trực tiếp phỏng vấn học viên nhóm khác trong lớp K5-L3A, lập bảng Interview Snapshot #1 và phân tích tín hiệu xác nhận / phản bác để điều chỉnh phạm vi bottleneck của nhóm.
- Thực hiện Research 4 công cụ/pattern thực tế (Google NotebookLM, GitHub Copilot Repository Context, Diátaxis Documentation Framework, Unified/Remark Markdown AST) kèm kiểm tra link sống và rút ra kết luận chuyển hướng từ "tự xây công cụ AI" sang quy trình bán thủ công kết hợp bảng Cheatsheet/Rule và công cụ có sẵn.

**Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- [Mục 3.1 — Assumption Map](report/team/group_report.md#31-assumption-map).
- [Mục 3.2 — Kiểm chứng và điều chỉnh problem](report/team/group_report.md#32-kiểm-chứng).
- [Mục 3.3 — Research giải pháp đã có](report/team/group_report.md#33-research-giải-pháp-đã-có).
- File ghi chú phỏng vấn chi tiết: [report/assets/cp4-interview-snapshot-1.md](report/assets/cp4-interview-snapshot-1.md).

**Điều mình học được từ phần nhóm:**

- Khi đưa problem cá nhân ra nhóm phản biện và đi phỏng vấn người thật ở nhóm khác, mình nhận ra giả định ban đầu ("ai cũng ngồi đọc một mạch 25 phút đầu giờ") chưa sát thực tế bằng việc học viên chỉ đọc `README.md` 5–6 phút rồi mất 15–20 phút mở qua mở lại giữa `RUBRIC.md` và `RULES.md` vì sợ sót yêu cầu nhỏ. Nhờ kiểm chứng và research, nhóm tránh được bẫy tự xây chatbot/Agent thừa thãi.

### HoVaTen-MSSV

**Phần việc phụ trách:**

- **Đóng góp cụ thể** (mình đã làm gì, ra sản phẩm gì):

- **Bằng chứng** (phần nào trong `group_report.md`, file nào trong `report/assets/`, commit nào):

- **Điều mình học được từ phần nhóm:**

-
