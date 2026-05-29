
# 03: Individual Reflection

## Bảng dùng AI trong quá trình làm bài

| Phase | Tôi dùng AI để làm gì? | AI hữu ích ở đâu? | AI sai/hơi hớt ở đâu? | Tôi sửa gì bằng nhận định của mình? |
|---|---|---|---|---|
| Scan | Gợi ý nhiều pain point liên quan đến giao tiếp giữa AI Engineer và stakeholder/PM/BE/FE. | Giúp mở rộng danh sách vấn đề nhanh, không bị kẹt ở 1-2 ý tưởng ban đầu. | Một số ý AI đưa ra còn chung chung, giống “AI có thể làm mọi thứ”, chưa có dấu hiệu thật hoặc metric rõ. | Tôi chọn lại các problem có actor cụ thể, có tần suất lặp lại, có dấu hiệu đo được như 45 phút/update, 25 phút/ticket, 70 phút/paper. |
| Problem Card | Nhờ AI biến các problem thành problem card có actor, context, workflow, bottleneck, impact, success metric. | AI giúp cấu trúc hóa suy nghĩ và làm rõ từng phần của problem card. | AI dễ viết impact hơi phóng đại hoặc đoạn nào cũng nghe quan trọng như nhau. | Tôi giữ lại 3 problem có workflow rõ nhất và sửa metric cho gần với tình huống thực tế của AI Engineer. |
| Workflow | Dùng AI để tách current workflow và future workflow theo từng bước, có thời gian ước lượng. | AI rất hữu ích khi biến một pain mơ hồ thành chuỗi bước cụ thể, nhìn được bottleneck nằm ở đâu. | AI có xu hướng làm future workflow quá đẹp, coi như AI làm được ngay và gần như không tốn thời gian. | Tôi thêm human boundary: engineer phải review, verify claims, edit narrative trước khi gửi hoặc post ticket. |
| Research | Dùng AI để nghĩ cách kiểm tra pain và gợi ý non-AI alternative. | AI giúp tôi nghĩ thêm về cách validate: đo thời gian, số câu hỏi clarify, số vòng comment. | AI chưa thấy được context riêng của team, nên research note ban đầu còn giống lý thuyết. | Tôi điều chỉnh lại thành các proxy metric thực tế hơn: thời gian viết, số câu hỏi clarify, discussion sau khi share paper. |
| Problem Statement | Nhờ AI draft problem statement ngắn gọn từ các problem card. | AI giúp rút gọn câu chữ và đưa problem về dạng “ai gặp đau, khi nào, vì sao quan trọng”. | AI hay viết theo hướng solution-first, chèn sẵn ý “AI sẽ giải quyết bằng...” vào problem statement. | Tôi tách riêng problem và solution hypothesis, giữ problem statement tập trung vào pain, actor, context, impact. |
| Rule / Workflow / Agent | Dùng AI để nghĩ nên xem bài này là Rule, Workflow hay Agent. | AI giúp so sánh nhanh giữa các kiểu giải pháp và thấy workflow phù hợp hơn vì bài có nhiều bước lặp lại. | AI có lúc muốn đẩy thành agent tự động, trong khi rủi ro sai metric/sai context khá cao. | Tôi chọn hướng Workflow: AI draft và cấu trúc hóa, còn con người chịu trách nhiệm xác minh và gửi thông tin cuối. |
| Decision | Dùng AI để so sánh 3 problem top và gợi ý nên ưu tiên vấn đề nào. | AI giúp nhìn lại problem nào có impact, tần suất và khả năng đo success metric tốt hơn. | AI đánh giá hơi đều, chưa cảm được problem nào phù hợp với phạm vi deliverable ngay lúc đó. | Tôi ưu tiên problem “viết update kỹ thuật cho stakeholder non-tech” vì workflow rõ, bottleneck cụ thể và liên quan trực tiếp đến giao tiếp với stakeholder. |
| Reflection | Dùng AI để nhắc lại quá trình làm bài và tạo khung trả lời reflection. | AI giúp tôi không bỏ sót các phase và câu hỏi mở. | Nếu để nguyên, reflection sẽ nghe rất đẹp nhưng không cá nhân, không nói rõ mình đã thay đổi suy nghĩ ở đâu. | Tôi thêm nhận định cá nhân: nhóm cần tránh solution-first, cần challenge metric/actor/context mạnh hơn, và phần judgment không nên giao hết cho AI. |

## Reflection câu hỏi mở

### Tôi học được gì khi nghe top 3 problems của các bạn khác?

Tôi học được rằng một problem tốt không chỉ là “nghe có vẻ hay” mà phải có actor rõ, có dấu hiệu thật, có tần suất lặp lại và có cách đo impact. Khi nghe top 3 problems của các bạn khác, tôi thấy nhiều vấn đề ban đầu rất rộng, nhưng sau khi bị hỏi “ai đang đau?”, “đau ở bước nào?”, “có đo được không?” thì problem mới bắt đầu sắc hơn.

Điều này làm tôi nhìn lại bài của mình. Ban đầu tôi cũng dễ bị cuốn vào các ý lớn như “AI hỗ trợ giao tiếp” hay “AI tóm tắt paper”, nhưng sau đó tôi phải kéo nó về các tình huống cụ thể hơn: AI Engineer mất 45 phút viết update, 70 phút tóm tắt paper, hoặc 25 phút viết ticket bug.

### Nhóm có lúc nào bị solution-first không?

Có. Nhóm có lúc nhảy rất nhanh sang ý tưởng “dùng AI để generate update”, “dùng AI để tóm tắt paper”, “dùng AI để viết ticket” trước khi nói rõ pain thật sự nằm ở đâu. Lúc đó solution nghe hợp lý, nhưng problem statement vẫn chưa chắc.

Sau khi bị challenge, tôi nhận ra cần quay lại workflow hiện tại và tìm bottleneck cụ thể. Ví dụ, vấn đề không phải chỉ là “viết update lâu”, mà là bước dịch metric kỹ thuật sang business narrative cho stakeholder non-tech vừa tốn thời gian vừa hay bị hỏi lại.

### Tôi có thay đổi ý kiến sau khi bị challenge không?

Có. Ban đầu tôi nghĩ problem tóm tắt research paper khá hấp dẫn vì AI có thể đọc và tóm tắt nhanh. Nhưng sau khi xem lại, tôi thấy problem này khó đo quality hơn, vì “tóm tắt không lạc hướng” và “có depth” không dễ đánh giá trong phạm vi ngắn.

Tôi nghiêng nhiều hơn về problem update kỹ thuật cho stakeholder non-tech, vì nó có workflow rõ, metric thời gian rõ, và success metric cũng cụ thể hơn: giảm từ 45 phút xuống dưới 15 phút mà không tăng số câu hỏi clarify.

### Tôi đóng góp gì thật sự vào artifact cuối?

Đóng góp chính của tôi là đưa các problem về đúng bối cảnh AI Engineer làm việc với nhiều stakeholder khác nhau. Tôi viết problem scan, chọn top 3, mô tả actor, current workflow, bottleneck, impact, success metric, non-AI alternative và AI hypothesis cho từng problem.

Tôi cũng có đóng góp ở phần giữ ranh giới con người trong workflow. Trong artifact, AI không được xem là người tự động quyết định nội dung cuối, mà chỉ hỗ trợ draft, cấu trúc hóa và dịch ngôn ngữ. Engineer vẫn phải review, verify số liệu, thêm judgment và chịu trách nhiệm trước khi gửi.

### Điều khó nhất khi viết Problem Statement là gì?

Điều khó nhất là không để problem statement biến thành solution statement. Khi đã nghĩ đến AI, tôi rất dễ viết theo kiểu “cần một AI tool để...” thay vì mô tả đúng nỗi đau hiện tại của người dùng.

Khó thứ hai là cân bằng giữa cụ thể và không quá hẹp. Nếu viết quá rộng thì problem mơ hồ, khó validate. Nếu viết quá hẹp thì giống một task nhỏ, không còn nhiều giá trị để thiết kế workflow. Tôi phải sửa nhiều lần để câu problem có đủ actor, context, pain, bottleneck và impact.

### Nếu làm lại, tôi sẽ challenge nhóm mạnh hơn ở điểm nào?

Nếu làm lại, tôi sẽ challenge nhóm mạnh hơn ở phần evidence và success metric. Mỗi khi có một problem nghe hay, tôi sẽ hỏi sớm hơn: “Dấu hiệu thật là gì?”, “Mất bao nhiêu thời gian?”, “Lặp lại bao lâu một lần?”, “Nếu giải quyết xong thì đo bằng gì?”

Tôi cũng sẽ challenge mạnh hơn khi nhóm bắt đầu solution-first. Trước khi chọn AI workflow hay agent, cần chứng minh problem đang xảy ra trong workflow hiện tại, bottleneck nằm ở bước nào, và non-AI alternative vì sao chưa đủ. Điều này giúp artifact cuối bớt giống một ý tưởng sản phẩm và giống một problem statement có cơ sở hơn.

