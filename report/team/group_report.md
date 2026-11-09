# Báo cáo nhóm — Day 02 Discovery & Problem Framing

> Bản chung của nhóm, viết trên repo do nhóm trưởng fork. Không copy file này sang repo cá nhân.
> Template chi tiết và prompt mẫu: [docs/01-worksheet.md](../../docs/01-worksheet.md). Bài mẫu: [docs/02-deliverable-example.md](../../docs/02-deliverable-example.md).

## 1. Thông tin nhóm

- Tên nhóm: VibeCode
- Thành viên: xem `TEAM.md`
- Candidate problem được chọn (1 câu): Học viên K5-L3A mất thời gian tra cứu và đối chiếu yêu cầu đầu buổi lab vì nhiệm vụ, vị trí điền và tiêu chí chấm nằm ở nhiều tài liệu.
- Quyết định cuối: Go / Not Yet / No-Go

---

## 2. Hội tụ nhóm (CP3)

### 2.1. Pitch

Tổng hợp **12 candidate**, gồm đúng **3 Problem Cards trong CP2 của mỗi thành viên**, theo thứ tự Hường → Thể → Đức Anh → Thông. Job Story được rút gọn, giữ nguyên vấn đề, actor và bottleneck của báo cáo cá nhân.

| # | Người đưa ra | Candidate (Job Story ngắn) | Actor | Bottleneck | Câu hỏi phản biện chuẩn bị cho pitch |
|---:|---|---|---|---|---|
| 1 | Đinh Thị Hường — Card #1 | **Kiểm thử model/prompt trước khi triển khai.** Khi thay đổi prompt hoặc model/RAG, tôi muốn đánh giá kết quả trên bộ dữ liệu chuẩn, để biết chất lượng và mức độ bịa thông tin thay đổi thế nào trước khi đưa lên production. | AI Engineer, QA Tester, Product Manager | Bước 3–4: copy từng câu hỏi và đọc, chấm output thủ công; khoảng **120–180 phút/đợt kiểm thử**. | Nếu giữ cùng một bộ ca và tính cả thời gian người rà, mức tiết kiệm còn bao nhiêu? Dùng tiêu chí nào để phát hiện trường hợp mô hình chấm sai? |
| 2 | Đinh Thị Hường — Card #2 | **Truy vết ngữ cảnh khi mô hình trả lời sai.** Khi CS/PM báo lỗi trên production, tôi muốn tìm lại prompt, tài liệu truy xuất và thông tin phiên, để giải thích nguyên nhân cho bộ phận kinh doanh. | AI Engineer, Customer Support, Product Manager | Bước 3–4: truy vấn log thô và đọc, tách JSON; **20–30 phút/sự vụ**. | Log hiện có đủ mã phiên, prompt và tài liệu truy xuất không? Nếu trình bày log rõ hơn bằng dashboard thì còn bước nào cần AI? |
| 3 | Đinh Thị Hường — Card #3 | **Quản lý và so sánh phiên bản prompt.** Khi thử nhiều phiên bản prompt, tôi muốn lưu được phiên bản và so sánh đầu ra, để chọn bản tốt nhất mà không mất dấu các lần thử. | AI Engineer, Prompt Engineer | Bước 3–4: so sánh output bằng mắt và lưu trữ phân mảnh; **20–30 phút/vòng thử nghiệm**. | Khó khăn chính là mất phiên bản hay đánh giá chất lượng đầu ra? Lưu metadata bằng Git và bảng kết quả đã đủ chưa? |
| 4 | Nguyễn Đắc Thể — Card #1 | **Chuẩn hóa và nhập đơn từ email/tin nhắn.** Khi nhận đơn đặt hàng, tôi muốn chuyển yêu cầu thành mã hàng và số lượng chính xác, để tạo đơn mà không phải nhập lại nhiều lần. | Nhân viên vận hành kinh doanh, sales, kho | Bước 4: nhập lại mã hàng, số lượng, giá và thông tin khách; **2 phút/đơn**, trong tổng 6 phút/đơn. | Nếu biểu mẫu và danh sách chọn mã hàng đã giảm nhập tay, còn cần AI ở đâu? Bước nhập chỉ chiếm 2/6 phút thì đạt mục tiêu 3 phút/đơn bằng cách nào? |
| 5 | Nguyễn Đắc Thể — Card #2 | **Đối chiếu thanh toán với hóa đơn.** Khi đối chiếu công nợ hằng tuần, tôi muốn ghép đúng khoản thanh toán với hóa đơn, để xác định số còn nợ và tránh nhắc thanh toán nhầm. | Kế toán công nợ; nhân viên vận hành kinh doanh hỗ trợ xác minh | Bước 3: ghép giao dịch với hóa đơn; **50 phút/tuần**, trong tổng 150 phút/tuần; khó ở nội dung chuyển khoản không thống nhất, trả gộp hoặc trả một phần. | Khoản trả gộp hoặc trả một phần được xác nhận thế nào? Nếu thiếu mã hóa đơn, ai kiểm trước khi cập nhật công nợ? |
| 6 | Nguyễn Đắc Thể — Card #3 | **Tìm lịch sử trao đổi trước khi phản hồi khách.** Khi khách liên hệ lại về đơn hàng, tôi muốn nắm lịch sử và cam kết trước đó, để phản hồi đúng mà không yêu cầu khách kể lại từ đầu. | Nhân viên chăm sóc khách hàng hoặc sales tiếp nhận yêu cầu | Bước 3: tìm và đọc lịch sử trao đổi; **3 phút/yêu cầu**, trong tổng 8 phút/yêu cầu; có trường hợp phải đối chiếu nhiều nguồn. | Khi các nguồn có cam kết khác nhau, làm sao xác định bản còn hiệu lực? Người xử lý có quyền truy cập đầy đủ lịch sử của đúng khách và đơn không? |
| 7 | Vũ Đức Anh — Card #1 | **Tra cứu và đối chiếu yêu cầu đầu buổi lab.** Khi bắt đầu buổi lab, tôi muốn nắm đủ đầu ra, quy tắc chấm điểm và hướng dẫn, để tránh chuyển qua lại nhiều nguồn và bỏ sót yêu cầu. | Học viên K5-L3A, làm cá nhân và nhóm 3–4 người | Bước 4: dò chéo CHECKPOINTS.md, RUBRIC.md và worksheet; **10 phút/buổi**, trong quy trình 25 phút đầu buổi. | Điểm nghẽn do tài liệu phân tán hay chưa đọc đúng thứ tự? Nếu dùng bảng đầu việc thủ công thì thời gian và số yêu cầu bỏ sót thay đổi thế nào? |
| 8 | Vũ Đức Anh — Card #2 | **Kiểm tra quy chuẩn bài nộp trên GitHub.** Khi chuẩn bị nộp bài nhóm, tôi muốn kiểm tra tên repo, file cá nhân và các mục bắt buộc, để tránh mất điểm do lỗi hình thức. | Nhóm trưởng và thành viên nhóm VibeCode | Bước 4: rà thủ công 4 báo cáo cá nhân, group_report.md và TEAM.md; **10 phút/lần**, trong quy trình nháp 18 phút. | Tên file, mục bắt buộc và link có thể kiểm bằng Rule đến đâu? Làm sao phân biệt lỗi thật với cảnh báo sai và tách hình thức khỏi chất lượng nội dung? |
| 9 | Vũ Đức Anh — Card #3 | **Đọc hiểu hướng dẫn, bài mẫu và framework.** Khi đọc tài liệu đầu buổi, tôi muốn nắm các ý cốt lõi và ví dụ quan trọng, để hiểu bài và bắt đầu thực hành đúng tiến độ. | Học viên K5-L3A | Bước 3: đọc bài mẫu và đối chiếu worksheet; **15 phút**, trong tổng 35 phút đọc hiểu so với 15 phút được phân bổ cho CP0. | Giảm thời gian đọc có làm giảm độ hiểu không? Dùng câu hỏi nào để kiểm tra học viên hiểu đúng, và việc đọc chọn lọc theo checkpoint đã đủ chưa? |
| 10 | Trương Văn Thông — Card #1 | **Đọc tài liệu tiếng Anh để tổng hợp kiến thức.** Khi học từ tài liệu tiếng Anh, tôi muốn tóm tắt công thức và kiến thức cần thiết, để nắm nội dung và chia sẻ với nhóm. | Sinh viên đọc tài liệu môn học; thành viên nhóm dùng bản tổng hợp | Đọc hiểu và chọn lọc ý chính; **tổng 5–8 giờ**, chưa tách thời gian từng bước và chưa xác định rõ phạm vi tài liệu. | Mốc 5–8 giờ ứng với một tài liệu, chương hay môn học? Ai đối chiếu công thức và thuật ngữ để bảo đảm bản tóm tắt không sai? |
| 11 | Trương Văn Thông — Card #2 | **Kiểm tra thời khóa biểu trước khi lên lớp.** Khi chuẩn bị đi học, tôi muốn xem nhanh lịch trong ngày, để biết giờ và phòng học mà không mất nhiều thời gian kiểm tra. | Sinh viên | **Chưa xác định bước nghẽn cụ thể**; tổng thời gian kiểm tra **5–10 phút/ngày**, chưa đo riêng từng thao tác. | Trong 5–10 phút kiểm lịch, bước nào mất nhiều thời gian nhất? Nếu lịch ít thay đổi, một lịch lưu sẵn và thông báo chính thức đã đủ chưa? |
| 12 | Trương Văn Thông — Card #3 | **Nhận diện và xử lý cuộc gọi rác/lừa đảo.** Khi đang học hoặc làm việc, tôi muốn nhận biết và bỏ qua cuộc gọi rác, để giảm gián đoạn mà không bỏ lỡ cuộc gọi hợp lệ. | Cá nhân nhận cuộc gọi; người cùng nhóm, đồng nghiệp hoặc khách hàng có thể bị ảnh hưởng | Nhận diện và xử lý cuộc gọi; **hơn 1 phút/cuộc**; chưa có tần suất để tính tổng thời gian gián đoạn. | Mỗi tuần có bao nhiêu cuộc gọi rác và tổng thời gian gián đoạn là bao nhiêu? Đo và xử lý việc chặn nhầm cuộc gọi hợp lệ thế nào? |

### 2.2. Cluster và chọn top 3

#### Gom nhóm candidate

| Cluster | Các candidate | Pattern chung |
|---|---|---|
| A — Kiểm tra và truy vết chất lượng mô hình | #1 Kiểm thử model/prompt; #2 Truy vết lỗi production; #3 So sánh phiên bản prompt | Phải đọc, đối chiếu và lưu lại đầu ra/ngữ cảnh để đánh giá thay đổi hoặc xác định nguyên nhân lỗi. |
| B — Xử lý thông tin trong vận hành doanh nghiệp | #4 Nhập đơn hàng; #5 Đối chiếu công nợ; #6 Tra lịch sử khách hàng | Dữ liệu nằm ở nhiều nguồn, cần chuẩn hóa hoặc đối chiếu trước khi tạo đơn, chốt số dư hay phản hồi khách. |
| C — Tra cứu, đọc hiểu và kiểm tra bài học | #7 Đối chiếu yêu cầu lab; #8 Kiểm tra bài nộp; #9 Đọc hướng dẫn và bài mẫu; #10 Tổng hợp tài liệu tiếng Anh | Người học phải chuyển thông tin từ tài liệu thành hiểu biết, đầu việc hoặc bằng chứng đáp ứng yêu cầu. |
| D — Quản lý lịch và gián đoạn cá nhân | #11 Kiểm tra thời khóa biểu; #12 Xử lý cuộc gọi rác | Cần nhận biết đúng thông tin để hành động kịp thời và giảm thao tác hoặc gián đoạn không cần thiết. |

#### Ba candidate tốt nhất để đưa vào shortlist

| Ưu tiên | Candidate | Vì sao nằm trong top 3 | Phạm vi đề xuất | Cần kiểm chứng tiếp |
|---:|---|---|---|---|
| **1** | **#7 — Tra cứu và đối chiếu yêu cầu đầu buổi lab (Đức Anh)** | Dữ liệu có ngay trong repo, dễ tìm người cùng bối cảnh ngoài nhóm; quy trình và đầu ra có thể đối chiếu với đề. | Một buổi lab; tạo đúng bảng đầu việc, vị trí điền và tiêu chí cần đáp ứng. | Quan sát học viên làm checklist; đo thời gian dò chéo và số yêu cầu thiếu/sai; thử bảng tổng hợp không AI để xem mức cải thiện. |
| **2** | **#8 — Kiểm tra quy chuẩn bài nộp GitHub (Đức Anh)** | Phạm vi kiểm tra cụ thể, có thể xây tập lỗi đã biết và đo phát hiện đúng/sai; dễ thử phương án Rule. | Tên và sự tồn tại của file, mục bắt buộc, link nội bộ; chưa chấm chất lượng lập luận. | Xác nhận lỗi thực sự từng gặp; dùng bản sao repo có lỗi biết trước để so thời gian, số lỗi bỏ sót và số cảnh báo sai giữa kiểm tay với checklist/Rule. |
| **3** | **#1 — Kiểm thử model/prompt trước triển khai (Hường)** | Bottleneck chấm thủ công rõ, có khả năng tạo giá trị ở tác vụ lặp lại; so sánh được Rule và Workflow trên cùng đầu vào. | Một tác vụ và một bộ ca cố định; so sánh thời gian cùng độ đúng của đánh giá; người phụ trách vẫn quyết định triển khai. | Xác nhận quyền dùng bộ ca, đáp án và tiêu chí chấm; so với người chấm trên cùng số ca, tính cả thời gian rà lại và chi phí. |

**Kết luận sàng lọc:** đưa **#7, #8 và #1** sang bước OST và chấm điểm shortlist. #7 được ưu tiên phân tích trước vì khả năng tiếp cận dữ liệu và người dùng tốt nhất trong bối cảnh lớp học. Đây là shortlist đề xuất từ 12 báo cáo candidate, chưa phải kết quả phỏng vấn hay quyết định Go. Hai candidate #7 và #8 phục vụ hai thời điểm khác nhau — chuẩn bị trước khi làm và kiểm sản phẩm trước khi nộp — nên được giữ riêng để so sánh.

### 2.3. Opportunity Solution Tree rút gọn

Cây tập trung vào **candidate #7 — Tra cứu và đối chiếu yêu cầu đầu buổi lab**, thuộc cluster C và được chọn theo bảng điểm ở mục 2.4. Các cluster còn lại là những hướng đã cân nhắc, không ép các vấn đề khác actor vào cùng cây.

**Outcome đề xuất:** giảm thời gian học viên K5-L3A xác định đầy đủ yêu cầu trước khi làm bài từ **25 xuống tối đa 15 phút/buổi**, đồng thời checklist cá nhân/nhóm **không thiếu hoặc gán sai yêu cầu bắt buộc**. Mốc 25 phút lấy từ báo cáo CP2 của Đức Anh; mục tiêu 15 phút là đề xuất để thử, chưa phải kết quả đạt được. Cách đo là ghi thời gian từ khi mở đề đến khi hoàn thành checklist, rồi đối chiếu checklist với yêu cầu gốc trên cùng một đề.

```text
OUTCOME: Xác định đủ, đúng yêu cầu bài lab trong ≤ 15 phút
         thay vì 25 phút, không thiếu hoặc gán sai yêu cầu bắt buộc
│
├── Opportunity A: Phải tìm và đối chiếu thông tin của cùng một
│   checkpoint ở nhiều tài liệu
│   ├── Nhiệm vụ và vị trí điền nằm tách với cách làm chi tiết
│   └── Tiêu chí chấm và điều kiện bị trừ điểm nằm ở tài liệu khác
│
├── Opportunity B: Chưa xác định nhanh được trách nhiệm và đầu ra
│   của từng phần cá nhân/nhóm
│   ├── Dễ nhầm việc tự scan với bước nhóm chọn một candidate
│   └── Chưa nối được từng yêu cầu với file/mục cần hoàn thành
│
└── Opportunity C: Khó biết checklist chuẩn bị đã đủ và đúng chưa
    ├── Dễ bỏ qua một điều kiện nhỏ khi chuyển giữa các tài liệu
    └── Cần quay lại nguồn để phân biệt yêu cầu bắt buộc với ví dụ
```

Các nhánh trên là **giả thuyết về nhu cầu và bước nghẽn cần kiểm chứng ở CP4**. Nhánh A gắn trực tiếp với bước dò chéo 10 phút được nêu trong card; nhánh B và C cụ thể hóa điều có thể khiến checklist thiếu hoặc sai. Mục tiêu đầu buổi không bao gồm đọc hiểu toàn bộ framework (#9) hay rà sản phẩm đã làm trước khi nộp (#8).

**Vì sao dùng mục tiêu 15 phút thay vì dưới 7 phút trong card ban đầu:** quy trình hiện tại là 25 phút, riêng bước dò chéo chiếm 10 phút. Chỉ cải thiện bước này chưa đủ để khẳng định có thể xuống dưới 7 phút; cần kiểm tra thêm thời gian các bước còn lại. Mốc 15 phút là giả thuyết thử nghiệm ban đầu, sẽ điều chỉnh sau khi quan sát quy trình thực tế.

**Các ý bị loại khỏi tầng opportunity vì là giải pháp:**

- Một chatbot trả lời mọi câu hỏi về đề: tên giải pháp, chưa mô tả nhu cầu hay nguyên nhân phải hỏi lại.
- Một bảng checklist tự động: cách tổ chức đầu ra; opportunity tương ứng là chưa xác định đủ đầu việc và vị trí điền.
- Một Agent đọc repo và điền báo cáo: áp đặt công nghệ và mở rộng sang làm bài; vượt phạm vi xác định yêu cầu.

Các phương án checklist thủ công, tổ chức lại tài liệu, Rule hoặc Workflow được so sánh sau khi xác nhận pain; chưa chọn công nghệ ở cây OST.

### 2.4. Chấm điểm shortlist (1–5)

Chấm sơ bộ theo nội dung 4 báo cáo cá nhân và khả năng thực hiện trong buổi lab. **1 = yếu hoặc còn thiếu nhiều thông tin; 3 = đáp ứng một phần; 5 = rõ và phù hợp.** Bảy tiêu chí có trọng số ngang nhau, tổng tối đa 35. Điểm dưới đây là đánh giá trong bản tổng hợp, không phải số liệu khảo sát hay kết quả bỏ phiếu đã diễn ra.

| Candidate | Actor rõ | Quy trình rõ | Pain có bằng chứng | Impact đo được | Vừa sức lab | So sánh được No AI/Rule/Workflow/Agent | Nhóm hiểu domain | Tổng |
|---|---:|---:|---:|---:|---:|---:|---:|---:|
| **#7 — Tra cứu và đối chiếu yêu cầu đầu buổi lab** | 5 | 5 | 3 | 5 | 5 | 5 | 5 | **33** |
| **#8 — Kiểm tra quy chuẩn bài nộp GitHub** | 5 | 5 | 3 | 4 | 5 | 5 | 5 | **32** |
| **#1 — Kiểm thử model/prompt trước triển khai** | 5 | 4 | 2 | 4 | 3 | 5 | 3 | **26** |

**Căn cứ cho điểm:**

| Candidate | Căn cứ và điểm còn hạn chế |
|---|---|
| **#7 — 33/35** | Actor là học viên trong bối cảnh nhóm đang trải nghiệm; có quy trình 5 bước, baseline 25 phút và bước dò chéo 10 phút theo báo cáo cá nhân. Có thể đo thời gian và độ đầy đủ của checklist, tiếp cận tài liệu ngay trong repo, mời học viên nhóm khác kiểm chứng. Điểm bằng chứng chỉ 3 vì chưa có log thời gian và phỏng vấn ngoài nhóm; dữ liệu trong card chưa đủ chứng minh mức phổ biến. |
| **#8 — 32/35** | Actor và quy trình 5 bước rõ; có nguồn quy định để đối chiếu và có thể dùng bản sao repo có lỗi biết trước. Điểm impact là 4 vì đo được thời gian rà, nhưng chưa có thống kê lỗi thực tế để lượng hóa lợi ích tránh sai sót. Điểm bằng chứng 3 vì chưa có kết quả quan sát độc lập. Điểm so sánh mức can thiệp vẫn là 5: chỉ ra Rule đủ dùng cũng là lập luận tốt, không bị trừ vì ít cần AI. |
| **#1 — 26/35** | Actor rõ, có các bước copy và chấm thủ công; có thể so sánh chấm tay, Rule và Workflow. Quy trình 4 vì thời gian trong mô tả, sơ đồ và baseline cần thống nhất; impact 4 vì mục tiêu thay đổi cả thời gian lẫn số ca, cần chuẩn hóa về cùng bộ ca. Bằng chứng 2 vì chưa có bộ ca, đáp án hoặc nhật ký kiểm thử đính kèm. Vừa sức lab 3 và hiểu domain 3 vì còn cần thống nhất tiêu chí chấm, quyền dùng dữ liệu và năng lực của cả nhóm, không chỉ một thành viên. |

**Candidate được chọn:** **#7 — Tra cứu và đối chiếu yêu cầu đầu buổi lab.**

Job Story: *Khi bắt đầu một buổi lab, học viên K5-L3A muốn xác định đầy đủ đầu việc, vị trí cần điền và tiêu chí phải đáp ứng, để bắt đầu thực hành đúng phạm vi mà không bỏ sót yêu cầu bắt buộc.*

**Vì sao chọn:**

- Có actor và bối cảnh cụ thể, nhóm có thể tiếp cận người dùng ngoài nhóm ngay tại lớp.
- Đầu vào đã có trong repo, không phụ thuộc quyền truy cập hệ thống doanh nghiệp hoặc dữ liệu khách hàng.
- Bottleneck là bước đối chiếu yêu cầu, có thể quan sát và đo riêng với các bước đọc khác.
- Đầu ra là checklist có thể kiểm đúng/sai bằng nguồn gốc; đo được cả thời gian lẫn chất lượng.
- Có thể thử phương án đơn giản như bảng tổng hợp thủ công trước khi quyết định có cần AI.

**Vì sao không chọn hai candidate còn lại trong vòng này:**

- **#8 — Kiểm tra quy chuẩn bài nộp:** đứng thứ hai và vẫn có giá trị, nhưng tập trung vào cuối quy trình khi bài đã làm xong. #7 xử lý bước xác định đầu việc ngay từ đầu; #8 cần thêm dữ liệu lỗi thật và phạm vi kiểm tra hình thức rõ để đo lợi ích. Giữ làm hướng dự phòng, không đưa thêm vào phạm vi #7.
- **#1 — Kiểm thử model/prompt:** pain có tiềm năng lớn, nhưng cần bộ ca, đáp án, tiêu chí chấm và cách đối chiếu với người chấm trước khi kiểm chứng đáng tin cậy. Chưa phù hợp bằng #7 với điều kiện dữ liệu hiện có và thời gian lab. Giữ cho vòng nghiên cứu tiếp khi có bộ ca phù hợp.

**Xử lý bất đồng (nếu có):** chưa có ghi nhận bất đồng thực tế. Khi thảo luận, thành viên đề xuất thay lựa chọn cần chỉ ra dữ kiện làm thay đổi một hoặc nhiều tiêu chí; nhóm cập nhật điểm và lý do. Nếu hai candidate bằng điểm, ưu tiên hướng tiếp cận được người dùng thật, có baseline kiểm lại được và ít phụ thuộc bên ngoài hơn. Không coi bảng chấm sơ bộ là biên bản đồng thuận đã diễn ra.

**Chuyển sang CP4:** kiểm tra bước dò chéo có thực sự là bottleneck, nguyên nhân do thông tin phân tán hay thói quen đọc, và bảng tổng hợp không AI có đủ giải quyết hay không. Đây là lựa chọn candidate để đào sâu, chưa phải quyết định Go hoặc lựa chọn mức can thiệp cuối cùng.

---

## 3. Kiểm chứng + research giải pháp đã có (CP4)

### 3.1. Assumption Map

| # | Giả định | Loại (Value / Usability / Feasibility / Viability) | Quan trọng (1–5) | Đã có bằng chứng (1–5) | Kiểm chứng trước? |
|---:|---|---|---:|---:|---|
| 1 | Học viên ở các nhóm khác trong lớp K5-L3A cũng mất từ 15–25 phút đầu buổi để mở nhiều tài liệu và tra cứu yêu cầu trước khi bắt tay vào làm bài. | Value | 5 | 2 | ✅ |
| 2 | Bước gây mất thời gian và dễ bỏ sót nhất là **bước dò chéo qua lại giữa `CHECKPOINTS.md`, `RUBRIC.md` và `01-worksheet.md`** (do thông tin của cùng một CP nằm tách biệt ở 3 nơi), chứ không chỉ do đọc chậm. | Value | 5 | 2 | ✅ |
| 3 | Chỉ cần một bảng tổng hợp cố định không dùng AI (*One-page Cheatsheet* gom Nhiệm vụ + File cần điền + Tiêu chí Rubric + Lỗi trừ điểm cho từng CP) là chưa đủ giải quyết hoàn toàn, hoặc ngược lại: bảng cố định đã giải quyết được 70–80% nỗi đau. | Value / Usability | 5 | 1 | ✅ |
| 4 | Học viên muốn một bản tổng hợp hỗ trợ đối chiếu kèm trích dẫn về file gốc (**augment**) hơn là giao hẳn cho công cụ tự tóm tắt mà không kiểm tra lại (**automate**), vì sợ sót điều kiện trừ điểm trong `RUBRIC.md`. | Usability | 4 | 2 | ✅ |
| 5 | Toàn bộ tài liệu đầu vào của buổi lab (`README.md`, `RULES.md`, `CHECKPOINTS.md`, `RUBRIC.md`, `SUBMISSION.md`, `docs/01-worksheet.md`) đều ở định dạng Markdown có cấu trúc heading/bảng chuẩn, có thể gom tự động bằng Rule/script hoặc đọc trực tiếp trong IDE/repo. | Feasibility | 4 | 5 | — |
| 6 | Quy định trong `RULES.md` cho phép dùng công cụ hỗ trợ tổng hợp và tra cứu yêu cầu tài liệu, miễn là không dùng AI làm thay phần bắt buộc tự thực hiện (Pitch CP3, Phỏng vấn CP4, Reflection CP7). | Viability | 4 | 5 | — |

Giả định nhóm kiểm chứng trong buổi này: **Giả định #1, #2, #3 và #4** (nhóm giả định có mức độ Quan trọng cao 4–5 nhưng Đã có bằng chứng thấp 1–2), thông qua phỏng vấn nhanh theo *The Mom Test* với học viên các nhóm khác trong lớp K5-L3A.

### 3.2. Kiểm chứng

Cách đã dùng: **Phỏng vấn nhanh theo *The Mom Test*** với học viên ở nhóm khác trong lớp K5-L3A (kết hợp quan sát thực tế thao tác mở tài liệu đầu buổi lab).

**Bộ câu hỏi phỏng vấn đã sử dụng (tuân thủ 3 luật *The Mom Test* — hỏi về hành vi đã xảy ra trong buổi sáng, không hỏi ý kiến giả định hay đề cập giải pháp):**
1. *"Lúc mới mở repo bài lab sáng nay, bạn đã đọc những file nào trước để biết CP1, CP2 phải làm gì và điền vào đâu?"*
2. *"Từ lúc mở đề đến lúc nắm rõ yêu cầu để bắt đầu làm bài, bạn mất khoảng bao nhiêu phút? Bước nào làm bạn mất thời gian nhất?"*
3. *"Hiện tại bạn đang làm cách nào để đối chiếu và nhớ các điều kiện chấm điểm/trừ điểm trong `RUBRIC.md` và `RULES.md` trong lúc làm bài?"*
4. *"Lúc làm các phần đầu sáng nay, bạn có bị bỏ sót hay phải quay lại sửa chi tiết nào vì lúc đọc lần đầu chưa để ý không?"*

**Interview Snapshot #1** *(file chi tiết: [report/assets/cp4-interview-snapshot-1.md](../assets/cp4-interview-snapshot-1.md))*:

| Trường | Nội dung |
|---|---|
| Người được hỏi (vai trò, không ghi tên thật) | Học viên lớp K5-L3A (thành viên một nhóm khác trong cùng buổi lab Day 02). |
| Câu nói đáng nhớ nhất (nguyên văn) | *"Lúc đầu mình đọc file `README.md` mất tầm 5–6 phút để nắm khung, nhưng lúc bắt tay vào làm vẫn phải mở qua mở lại giữa `README.md`, `RUBRIC.md` với `RULES.md` suốt khoảng 15–20 phút vì nếu không duyệt và đọc kỹ lại thì rất dễ bị sót các yêu cầu nhỏ."* |
| Lần gần nhất gặp vấn đề này: chuyện gì đã xảy ra? | Ngay đầu buổi lab Day 02 sáng nay: học viên mở repo của nhóm, đọc `README.md` trước (khoảng 5–6 phút) để hiểu luồng chung, sau đó khi bắt đầu làm CP1–CP2 thì phải liên tục mở thêm `RUBRIC.md`, `RULES.md` và `CHECKPOINTS.md` để kiểm tra xem mỗi mục yêu cầu điều kiện gì và cấm gì. |
| Hiện đang xử lý bằng cách nào (workaround)? | Không có bảng gom sẵn; xử lý thủ công bằng cách **mở sẵn nhiều tab/file cùng lúc và chuyển qua chuyển lại (alt-tab / mở qua mở lại nhiều lần)** giữa `README.md`, `RUBRIC.md`, `RULES.md` và file báo cáo đang gõ để tự dò lại từng mục. |
| Mất bao lâu, bao lần? | Riêng bước đọc và phân tích `README.md` ban đầu mất **5–6 phút**; tổng thời gian đọc và dò chéo qua lại với `RUBRIC.md`, `RULES.md` để nắm đủ yêu cầu mất khoảng **15–20 phút** (lặp lại việc mở qua mở lại nhiều lần ở mỗi checkpoint). |
| Insight / opportunity rút ra | Học viên không đọc hết một mạch 25 phút rồi mới làm, mà đọc `README.md` 5–6 phút rồi **vừa làm vừa phải mở qua mở lại nhiều lần** với `RUBRIC.md` và `RULES.md` (tổng 15–20 phút). Nỗi đau lớn nhất không chỉ là thời gian đọc ban đầu mà là **chi phí chuyển ngữ cảnh (context switching) liên tục và nỗi lo bỏ sót điều kiện trừ điểm nếu không đọc đi đọc lại**. |

Tổng hợp:

| Nguồn | Số người / số mẫu | Tín hiệu xác nhận | Tín hiệu phản bác |
|---|---:|---|---|
| Phỏng vấn trực tiếp (The Mom Test) & quan sát tại lớp K5-L3A | 1 buổi phỏng vấn sâu + đối chiếu thực tế 4 thành viên nhóm | Xác nhận giả định #1 và #2: Học viên thực sự mất **15–20 phút** cho việc đọc `README.md` và dò chéo qua lại với `RUBRIC.md`, `RULES.md`; workaround hiện tại hoàn toàn là mở qua mở lại thủ công và thực tế **đã xảy ra việc bỏ sót chi tiết nhỏ** nếu không rà lại nhiều lần. | **Tín hiệu phản bác một phần giả định ban đầu:** Học viên không ngồi đọc liền 25 phút từ đầu mới bắt đầu làm, mà chỉ dành **5–6 phút** đọc `README.md` trước rồi chuyển sang vừa làm vừa mở lại `RUBRIC.md` / `RULES.md`. Ngoài ra, `README.md` đã làm khá tốt vai trò định hướng 5 phút đầu; điểm nghẽn thật sự dồn vào lúc **đối chiếu điều kiện chấm/phạt điểm trong `RUBRIC.md` và `RULES.md` cho từng checkpoint**. |

**Nhóm đã sửa problem thế nào sau kiểm chứng:**

1. **Điều chỉnh lại mô tả quy trình và Baseline thời gian sát thực tế hành vi:** Thay vì giả định học viên ngồi đọc một mạch 25 phút đầu giờ rồi mới làm bài, nhóm cập nhật lại: học viên mất **5–6 phút đầu** đọc `README.md` và mất thêm **10–15 phút tiếp theo (tổng 15–25 phút, trung bình ~20 phút)** do phải **mở qua mở lại nhiều lần** giữa `README.md`, `CHECKPOINTS.md`, `RUBRIC.md` và `RULES.md` để không bị sót điều kiện.
2. **Thu hẹp chính xác phạm vi Bottleneck:** Không cần làm lại phần giới thiệu chung (vì `README.md` chỉ mất 5–6 phút là nắm được), mà tập trung giải quyết đúng bước **"đối chiếu điều kiện chấm điểm (`RUBRIC.md`), quy định dùng công cụ (`RULES.md`) và vị trí điền (`CHECKPOINTS.md`) theo từng CP"** để học viên không phải mở qua mở lại nhiều file và không bị sót yêu cầu nhỏ.
3. **Định hình giải pháp kết hợp từ Kiểm chứng + Research:** Vì học viên rất sợ bỏ sót điều kiện trừ điểm nhỏ (như cấm từ khóa ở CP1, bắt buộc có phản biện ở CP2, cấm dùng AI ở CP3/CP4 phỏng vấn), một bản tóm tắt chung chung của AI là **không an toàn**. Giải pháp đúng phải là một **Bảng đối chiếu 1 trang (One-page Cheatsheet) theo từng CP** kết hợp giữa **Rule/trích xuất nguyên văn điều kiện Rubric & Rules** và **Workflow tóm tắt ngắn hướng dẫn worksheet có trích dẫn dòng**, kèm bước con người duyệt lại.

### 3.3. Research giải pháp đã có

| Công cụ / case / pattern | Link | Giải bước nào trong quy trình? | Điểm mạnh | Khoảng trống / rủi ro | Bài học cho nhóm |
|---|---|---|---|---|---|
| **Google NotebookLM** (Source-grounded Briefing Doc & Study Guide) | https://notebooklm.google/ | **Bước 2, 3, 4, 5:** Tải bộ 6–7 file `.md` của buổi lab lên một notebook để tạo *Briefing Doc / Study Guide* và tra cứu chéo yêu cầu từng CP kèm trích dẫn nguồn (inline citations) trỏ thẳng về đoạn gốc. | Chỉ trả lời dựa trên tài liệu nguồn được tải lên (source-grounded), hạn chế bịa thông tin ngoài đề; có trích dẫn số thứ tự nguồn để bấm đối chiếu ngay với `RUBRIC.md` và `CHECKPOINTS.md`. | Phải tải thủ công từng file `.md` lên mỗi đầu buổi lab; bản tóm tắt mặc định chưa chia sẵn theo đúng bảng 4 cột (*CP — File cần điền — Tiêu chí Rubric — Điều kiện trừ điểm*) nếu không nhập prompt cấu trúc rõ ràng; vẫn có thể tóm tắt lướt qua các quy tắc phạt điểm nhỏ ở cuối file. | Không cần tự xây hệ thống RAG từ đầu; nếu dùng AI hỗ trợ tổng hợp quy định thì **bắt buộc phải có trích dẫn nguồn (citation)** trỏ về file gốc để học viên kiểm tra. |
| **GitHub Copilot Chat — Repository Context** (Hỏi đáp trực tiếp trên ngữ cảnh repo) | https://docs.github.com/en/copilot/using-github-copilot/asking-github-copilot-questions-in-github | **Bước 3, 4, 5:** Đọc trực tiếp toàn bộ các file `.md` ngay trong repo bài lab đã fork (`README.md`, `CHECKPOINTS.md`, `RUBRIC.md`, `docs/01-worksheet.md`) để lập bảng đối chiếu yêu cầu và vị trí điền cho từng CP. | Tích hợp sẵn ngay trên GitHub và IDE, đọc trực tiếp cấu trúc thư mục và tên file thật (`report/individual/MSSV_HoTen.md`, `report/team/group_report.md`) mà không tốn bước copy/upload file. | Nếu từng thành viên hỏi tự do (ad-hoc chat) thì kết quả không đồng nhất; mô hình dễ gộp nhầm yêu cầu giữa các CP hoặc bỏ sót điều kiện định lượng (như tối thiểu 200 từ ở CP7, sai tên file trừ 5 điểm) nếu không có khung trích xuất cố định. | Thay vì để mỗi người chat tự do, cần một **Workflow/Prompt chuẩn hóa đầu ra** cố định theo từng CP kết hợp bước con người rà lại các con số phạt điểm. |
| **Diátaxis Documentation Framework** (Chuẩn quốc tế tổ chức tài liệu kỹ thuật) | https://diataxis.fr/ | **Bước 2, 3, 4 (Góc nhìn No AI):** Giải thích nguyên nhân gốc rễ gây nghẽn khi tài liệu tách rời thành 4 dạng: *Tutorials/How-to* (`01-worksheet.md`), *Reference* (`CHECKPOINTS.md`, `RUBRIC.md`, `RULES.md`) và *Example* (`02-deliverable-example.md`). | Chỉ ra cách giải quyết **No AI**: thiết kế một bảng tham chiếu nhanh 1 trang (*One-page Cheatsheet / Quick Reference*) đặt ở đầu buổi để nối trực tiếp từng `CP` với `File cần điền` và `Tiêu chí Rubric` mà không cần AI. | Đề bài gốc của khóa học do ban tổ chức thiết kế sẵn nên nhóm học viên không sửa trực tiếp cấu trúc repo gốc trước giờ mở đề được; vẫn cần 1 thành viên hoặc 1 script gom lại ở đầu buổi. | Phần **nối cấu trúc (CP nào → điền mục nào → chấm điểm ở dòng nào)** thực chất là bài toán tổ chức thông tin cố định; một bảng Cheatsheet 1 trang đã giải quyết được phần lớn mà không sợ AI bịa số liệu. |
| **Unified / Remark Markdown AST** (Rule/Script tách và gom bảng Markdown theo heading) | https://github.com/remarkjs/remark | **Bước 3, 4 (Góc nhìn Rule):** Dùng script/Rule đọc cú pháp Markdown (heading `## CP0..CP7` và các dòng bảng tương ứng trong `CHECKPOINTS.md`, `RUBRIC.md`, `RULES.md`) để ghép thành 1 file tổng hợp tự động theo mã `CP`. | Chính xác 100% về mặt chữ và con số (không bao giờ làm tròn sai điểm hay sót chữ trong Rubric), chạy dưới 1 giây cho mọi repo lab có cấu trúc tương tự. | Chỉ ghép được nguyên văn các đoạn/bảng có từ khóa `CP1..CP7`, chưa tự tóm tắt ngắn gọn phần giải thích dài trong `docs/01-worksheet.md` nếu cấu trúc heading giữa các buổi lab thay đổi. | **Rule/Script** giữ vai trò trích xuất nguyên văn bảng điểm và quy định từ `RUBRIC.md` / `CHECKPOINTS.md`; **AI (trong Workflow)** chỉ nên hỗ trợ tóm tắt phần hướng dẫn dài trong `01-worksheet.md`. |

**Kết luận từ Research (làm thay đổi góc nhìn của nhóm):**

```text
1. Không cần (và không nên) tự xây dựng một AI Agent hay hệ thống chatbot riêng.
2. Phần đối chiếu "CP nào → điền file/mục nào → tiêu chí Rubric & điểm trừ" cần độ chính xác tuyệt đối 100%, nên giải quyết tốt nhất bằng Bảng Cheatsheet cố định + Rule/trích xuất nguyên văn (không để AI tự viết lại điểm số).
3. Các công cụ đọc repo có sẵn (NotebookLM, Copilot/IDE Assistant với prompt chuẩn) đã làm tốt việc tóm tắt hướng dẫn dài trong 01-worksheet.md, miễn là đi theo một Workflow bán thủ công:
   [Gom bảng CP + Rubric nguyên văn (Rule/Template)] → [Tóm tắt lưu ý chính từ worksheet kèm trích dẫn dòng (AI)] → [1 thành viên rà lại trong 3 phút & ghim cho cả nhóm dùng chung (Con người)].
```

---

## 4. Quy trình trước/sau (CP5)

### 4.1. Quy trình hiện tại

Sơ đồ (ASCII, Mermaid hoặc link ảnh trong `report/assets/`):

```text

```

| Bước | Actor | Input | Output | Thời gian / tần suất | Ghi chú |
|---:|---|---|---|---|---|
| 1 | | | | | |
| 2 | | | | | |
| 3 | | | | | |
| 4 | | | | | |
| 5 | | | | | |

**Bottleneck chính:**

### 4.2. Quy trình tương lai

Ghi rõ bước nào **Rule**, bước nào **AI**, bước nào **con người**, **boundary** ở đâu, **phương án quay về** khi AI sai.

```text

```

### 4.3. Before / after

| Chỉ số | Trước | Sau (kỳ vọng) | Ghi chú |
|---|---:|---:|---|
| Số bước | | | |
| Tổng thời gian | | | |
| Số bước thủ công | | | |
| Bottleneck chính | | | |
| Rủi ro mới phát sinh | | | |

---

## 5. Problem Statement v0 (CP5)

| Trường | Nội dung |
|---|---|
| **Actor** | |
| **Quy trình** | |
| **Bottleneck** | |
| **Impact** | |
| **Success Metric** (baseline → target, cách đo) | |
| **Boundary** (AI không được làm gì; khi nào cần con người kiểm tra — HITL) | |

Phản biện nhận được (từ AI hoặc nhóm khác) và nhóm có đồng ý không:

-

---

## 6. Mức can thiệp AI (CP6)

### 6.1. Ma trận độ mơ hồ × độ phức tạp

Bài của nhóm nằm ở ô:

Vì sao:

### 6.2. So sánh 4 mức

| Mức | Phương án cho bài của nhóm | Đủ khi nào | Rủi ro | Chọn? |
|---|---|---|---|---|
| **No AI** (sửa quy trình) | | | | |
| **Rule** | | | | |
| **Workflow** | | | | |
| **Agent** | | | | |

**Mức chọn:**

**Vì sao không chọn mức đơn giản hơn:**

### 6.3. AI Canvas rút gọn

| Thành phần | Nội dung |
|---|---|
| **Prediction** — AI dự đoán / tạo ra gì? | |
| **Judgment** — con người cân nhắc, quyết định gì? | |
| **Action** — hành động cuối cùng là gì, ai làm? | |
| **Outcome** — đo kết quả bằng gì? | |
| **Input** — AI cần dữ liệu đầu vào gì mỗi lần chạy? Có sẵn không? | |
| **Feedback** — lấy phản hồi ở đâu để cải thiện? | |

### 6.4. Hai câu hỏi của Google PAIR

- Người dùng muốn **được hỗ trợ (augment)** hay **giao hẳn việc (automate)**? Bằng chứng:
- AI sai kiểu nào tệ hơn, **báo nhầm** hay **bỏ sót**? Vì sao, và thiết kế đã xử lý thế nào:

---

## 7. Problem Statement v1 + tiêu chí đánh giá (CP6)

| Trường | Nội dung |
|---|---|
| **Actor** | |
| **Quy trình** | |
| **Bottleneck** | |
| **Impact** | |
| **Success Metric** (baseline → target, cách đo) | |
| **Boundary** | |
| **AI intervention point** | |
| **Mức chọn** | No AI / Rule / Workflow / Agent |
| **Rủi ro & người kiểm tra** | |

**Thay đổi so với v0 và lý do:**

| Trường | v0 | v1 | Vì sao đổi |
|---|---|---|---|
| | | | |

**Tiêu chí đánh giá đầu ra của AI (3–5 tiêu chí):**

| # | Tiêu chí | Đạt khi | Không đạt khi |
|---:|---|---|---|
| 1 | | | |
| 2 | | | |
| 3 | | | |

---

## 8. Quyết định (CP6)

### 8.1. Bốn rủi ro

| Rủi ro | Câu hỏi | Mức độ rủi ro (Thấp = an toàn / TB / Cao = nguy hiểm) | Lý do / bằng chứng |
|---|---|---|---|
| **Value** | Người dùng có thật sự cần và sẽ dùng không? | | |
| **Usability** | Người dùng có dùng được, có hiểu và sửa được đầu ra của AI không? | | |
| **Feasibility** | Có đủ dữ liệu, công cụ, kỹ năng để làm không? | | |
| **Viability** | Có hợp chi phí, pháp lý, quy định tổ chức không? Ai vận hành? | | |

### 8.2. Kết luận

**Quyết định:** Go / Not Yet / No-Go

**Lý do:**

**Nếu Go — pilot nhỏ nhất:**

**Nếu Not Yet — cần kiểm chứng gì trước:**

**Nếu No-Go — nên làm gì thay AI:**

**Ngưỡng dừng** (nếu sau … mà … thì quay về …):

---

## 9. Hạn chế và hướng tiếp theo

-

## 10. Tài liệu tham khảo

-
