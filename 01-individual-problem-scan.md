# Case:  Giao tiếp với team / stakeholder
### 01: Individual Problem Scan
Scan rộng 

| #  | Lăng kính          | Problem quan sát được                                                                          | Ai đang đau?                   | Dấu hiệu thật                              |
|----|--------------------|------------------------------------------------------------------------------------------------|--------------------------------|--------------------------------------------|
| 1  | Pain từ người khác | Viết update kỹ thuật cho stakeholder non-tech mất nhiều thời gian vì phải dịch thuật ngữ AI/ML | AI Engineer, PM, EM            | ~45 phút/lần viết update, vẫn bị hỏi lại  |
| 2  | Lặp lại            | Mỗi sprint phải giải thích lại tại sao model thay đổi accuracy/metric cho team product         | AI Engineer, Product Manager   | Họp giải thích lặp lại 2-3 lần/sprint      |
| 3  | Tốn thời gian      | Viết ticket/issue mô tả bug AI đủ chi tiết để BE/FE hiểu và xử lý                              | AI Engineer, Backend, Frontend | 25 phút/ticket, vẫn thiếu context          |
| 4  | Lặp lại            | Chuẩn bị slide demo cho buổi review mỗi 2 tuần                                                 | AI Engineer                    | 1-2 giờ/buổi chuẩn bị                      |
| 5  | AI có thể tốt hơn  | Đọc research paper để tóm tắt cho team trong weekly                                            | AI Engineer, team              | 1-2 tiếng/paper, tóm tắt hay bị lạc hướng  |
| 6  | Pain từ người khác | PM viết requirement mơ hồ, AI Engineer không biết nên build gì                                 | AI Engineer, PM                | Clarification 3-4 lần/ticket               |
| 7  | Tốn thời gian      | Onboarding: tìm hiểu codebase AI cũ không có doc, hỏi khắp Slack                               | AI Engineer mới                | 1-2 tuần để hiểu 1 pipeline                |
| 8  | Lặp lại            | Review pull request của junior cần giải thích kỹ phần logic model                              | Senior AI Engineer, Junior     | 30-40 phút/PR, comment nhiều vòng          |
| 9  | AI có thể tốt hơn  | Viết documentation cho API/endpoint AI model sau khi deploy                                    | AI Engineer, BE, FE consumer   | Hay bị skip, hoặc doc không đủ dùng        |
| 10 | Pain từ người khác | Giải thích kết quả A/B test AI feature cho leadership không hiểu thống kê                      | AI Engineer, EM, CEO           | Meeting hỏi lại nhiều lần về ý nghĩa số    |

### Top 3
| Rank | Problem | Vì sao chọn | Điều còn chưa chắc |
|------|---------|-------------|--------------------|
| 1 | Viết update kỹ thuật cho stakeholder non-tech | Workflow rõ, mất nhiều thời gian (45 phút/lần), có metric tốt | Update "đủ rõ cho stakeholder" đo thế nào |
| 2 | Tóm tắt research paper cho weekly      | Có pain thật, lặp hằng tuần, AI có thể giúp đọc/kết nối với product context | Quality "tóm tắt không lạc hướng" khó đo định lượng |
| 3 | Viết ticket bug AI cho BE/FE | Nhiều người đau (AI Engineer + BE/FE), impact 2 chiều, lặp hằng ngày | Mỗi bug context khác nhau, khó chuẩn hóa template |

# Problem Card 1 - Update kỹ thuật cho stakeholder non-tech

**Problem 1 câu:** Sau mỗi sprint, AI Engineer mất khoảng 45 phút viết update kỹ thuật cho PM/EM/CEO, trong đó bước "dịch" metric model/agent sang ngôn ngữ business tốn nhất và vẫn thường bị hỏi lại.

**Actor:** AI Engineer mới ra trường, làm trong team AI Platform tại công ty công nghệ lớn (2.000+ người), chưa quen giao tiếp với stakeholder non-technical.

**Thời điểm / bối cảnh:** Cuối sprint (2 tuần/lần) hoặc sau milestone/demo. Deadline thường là sáng ngày leadership review meeting.

**Current workflow:**
1. Xem lại Jira/Notion sprint — tổng hợp thay đổi về model/agent
2. Ghi raw metrics: accuracy, latency, token cost, error rate
3. Viết phần "ý nghĩa business" — dịch số sang impact user/sản phẩm
4. Format, check grammar, thêm next steps
5. Gửi qua email / Slack / comment Confluence

**Bottleneck:** Bước 3 — viết business narrative từ raw metric mất khoảng 20 phút và hay bị blank page. Mỗi sprint context khác nhau, không có template cố định để dịch số → impact.

**Impact:** 45 phút/lần × 2 lần/tháng = ~90 phút/tháng/engineer. Team 3 AI Engineer: ~270 phút/tháng. Update mơ hồ khiến PM/EM ra quyết định thiếu context, tăng số meeting clarify sau đó.

**Success metric:** Giảm tổng thời gian từ 45 phút xuống dưới 15 phút, không tăng số câu hỏi clarify từ stakeholder sau khi đọc update.

**Non-AI alternative:** Template update cố định (What changed / Why it matters / Next steps) có thể giảm format effort, nhưng chưa giải quyết tốt phần dịch metric kỹ thuật sang business impact theo context sản phẩm.

**AI hypothesis:** AI hỗ trợ dịch raw metric sang business narrative dựa trên context sản phẩm. Engineer cung cấp data + context, AI draft, Engineer review/edit trước khi gửi.

**Quick gut:** Workflow.

## Draft current workflow
```
CURRENT STATE — 45 phút
[1 Xem lại Jira/Notion: 10']
→ [2 Ghi raw metrics: 5']
→ [3 Viết business narrative: 20']  <-- bottleneck
→ [4 Format + next steps: 7']
→ [5 Gửi: 3']
```

## Draft future workflow
```
FUTURE STATE — 12 phút
[1 Paste metrics + context vào prompt template: 3']
→ [2 AI cấu trúc data: What changed / Why / Next: ~0']
→ [3 AI draft business narrative theo audience: ~0']
→ [4 Engineer review + edit: 7']   <-- human boundary
→ [5 Engineer gửi: 2']
```
Fallback: AI draft sai số liệu hoặc narrative quá generic → Engineer cung cấp thêm context sản phẩm và prompt lại. Nếu vẫn tệ → Engineer tự viết từ template.

# Problem Card #2 — Tóm tắt research paper cho weekly sync

**Problem 1 câu:** Mỗi tuần AI Engineer mất khoảng 70 phút đọc 1-2 paper mới và viết tóm tắt cho team, trong đó bước kết nối paper với product đang build tốn nhất và hay bị lạc hướng.

**Actor:** AI Engineer trong team NLP/LLM tại công ty công nghệ lớn, chịu trách nhiệm chia sẻ paper mới trong weekly team sync (5 phút mỗi lần).

**Thời điểm / bối cảnh:** Cuối tuần hoặc tối trước weekly sync. Mỗi engineer trong team luân phiên share paper mỗi 2-3 tuần.

**Current workflow:**
1. Đọc full paper (abstract → method → results)
2. Ghi note các key contribution
3. Viết tóm tắt "applicable to our product"
4. Paste vào Notion / Slack channel team
**Bottleneck:** Bước 3 — kết nối contribution của paper sang "team mình có thể dùng cái này để làm gì" mất khoảng 25 phút. Phần này không có trong paper, phải tự suy, hay bị blank hoặc viết quá abstract.

**Impact:** 70 phút/tuần/engineer chỉ để chia sẻ 5 phút trong sync. Team 5 engineer luân phiên: ~350 phút/tháng. Tóm tắt lạc hướng làm team không thấy được giá trị thực tế, paper bị quên ngay sau buổi sync.

**Success metric:** Giảm tổng thời gian từ 70 phút xuống dưới 25 phút, không giảm số lượng câu hỏi/discussion từ team sau khi share (proxy cho việc tóm tắt vẫn đủ depth).

**Non-AI alternative:** Template tóm tắt cố định (Method / Key finding / How to apply) giảm format effort, nhưng chưa giải quyết được bước "applicable to our product" — phần này cần judgment về stack đang dùng.

**AI hypothesis:** AI giúp đọc paper và draft phần "application to our stack" dựa trên context sản phẩm engineer cung cấp. Engineer review, thêm judgment cá nhân, edit trước khi share.

**Quick gut:** Workflow.

## Draft current workflow
```
CURRENT STATE — 70 phút
[1 Đọc full paper: 30']
→ [2 Ghi note key contribution: 10']
→ [3 Viết "applicable to our product": 25']  <-- bottleneck
→ [4 Paste lên Notion/Slack: 5']
```

## Draft future workflow
```
FUTURE STATE — 22 phút
[1 Upload paper + context stack vào prompt: 3']
→ [2 AI extract Method / Key finding: ~0']
→ [3 AI draft "application to our stack" theo context: ~0']
→ [4 Engineer skim paper + verify AI claims: 12']
→ [5 Engineer edit + thêm judgment cá nhân: 5']  <-- human boundary
→ [6 Engineer share: 2']
```
Fallback: AI hiểu sai contribution hoặc application quá generic → Engineer cung cấp thêm bullet points về stack/OKR và prompt lại. Nếu vẫn tệ → Engineer tự viết từ note.

---

# Problem Card #3 — Viết ticket bug AI cho BE/FE

**Problem 1 câu:** Khi model/agent trả kết quả sai, AI Engineer mất khoảng 25 phút viết ticket mô tả bug nhưng vẫn phải clarify 2-3 vòng vì BE/FE không có background ML để hiểu phần expected behavior.

**Actor:** AI Engineer trong team Recommendation/Conversational AI tại công ty lớn, cộng tác hằng ngày với Backend và Frontend không có background ML.

**Thời điểm / bối cảnh:** Bất kỳ lúc nào trong sprint khi phát hiện bug liên quan đến output AI. Tần suất trung bình 1-2 ticket/ngày/engineer.

**Current workflow:**

1. Reproduce bug — chạy lại input/output
2. Ghi input, output thực tế, output expected
3. Viết phần "tại sao đây là lỗi" (dịch ML → system behavior)
4. Post ticket Jira + tag BE/FE

**Bottleneck:** Bước 3 — viết phần "expected behavior" và "tại sao đây là lỗi" theo ngôn ngữ hệ thống (không dùng "embedding", "logit", "prompt") để BE/FE debug được mất khoảng 15 phút. Mỗi bug context khác nhau, không có template fit all.

**Impact:** 25 phút/ticket × ~10 ticket/tuần = ~250 phút/tuần/engineer chỉ để viết ticket. Ticket thiếu context khiến BE/FE comment hỏi lại 2-3 vòng → AI Engineer bị interrupt, BE/FE bị block, sprint velocity giảm.

**Success metric:** Giảm thời gian viết từ 25 phút xuống dưới 10 phút, giảm số vòng comment clarify từ 2-3 xuống còn 1.

**Non-AI alternative:** Template ticket cố định (Steps to reproduce / Expected / Actual / Impact) giảm format effort, nhưng chưa giải quyết bước dịch thuật ngữ ML → ngôn ngữ system. Phần này phụ thuộc loại bug.

**AI hypothesis:** AI giúp dịch "expected behavior theo ngôn ngữ ML" → "expected behavior theo ngôn ngữ system" dựa trên context bug engineer cung cấp. Engineer review để chắc số liệu/reproduce step đúng.

**Quick gut:** Workflow.

## Draft current workflow
```
CURRENT STATE — 25 phút
[1 Reproduce bug: 5']
→ [2 Ghi input/output: 5']
→ [3 Viết expected behavior (ML→non-ML): 15']  <-- bottleneck
→ [4 Post Jira + tag: 5' lồng vào bước 3]
(tổng quan ~25')
```

## Draft future workflow
```
FUTURE STATE — 9 phút
[1 Engineer paste input/output + ngữ cảnh bug: 3']
→ [2 AI dịch expected behavior sang ngôn ngữ system: ~0']
→ [3 AI gợi ý steps to reproduce theo format BE/FE: ~0']
→ [4 Engineer verify số liệu + reproduce step: 4']  <-- human boundary
→ [5 Engineer post Jira + tag: 2']
```
Fallback: AI dịch sai nghĩa kỹ thuật hoặc bỏ sót edge case → Engineer thêm chú thích và prompt lại. Nếu vẫn tệ → Engineer tự viết từ template.


