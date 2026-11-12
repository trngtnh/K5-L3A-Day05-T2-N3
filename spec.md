# Bài nộp LAB5 — Track 2 · Nhóm N3
[Danh sách thành viên và việc mỗi người làm — copy bảng từ README]

## 1. Phạm vi và giới hạn sản phẩm (Slice & Scope)

**Tên sản phẩm:** Trợ lý học tập AI tích hợp trên trang khóa học.

### 1.1. Phạm vi sản phẩm

Trợ lý học tập AI hỗ trợ sinh viên trong quá trình học môn **Introduction to Data Analysis (Nhập môn Phân tích dữ liệu)**, tập trung vào những bài học mà sinh viên đã mở.

Hệ thống có các chức năng chính:

- Tra cứu nội dung trong tài liệu học tập của khóa học.
- Giải thích kiến thức dựa trên tài liệu và trích dẫn chính xác mục tương ứng.
- Đặt câu hỏi làm rõ khi yêu cầu của sinh viên chưa đủ thông tin.
- Hướng dẫn sinh viên tiếp cận vấn đề theo từng bước đối với nội dung học tập thông thường; riêng bài tập đang mở, hệ thống chỉ cung cấp gợi ý ở bước đầu tiên và không tiết lộ lời giải hoặc đáp án hoàn chỉnh.
- Chuyển câu hỏi đến trợ giảng (TA) khi tài liệu không đủ thông tin hoặc phát hiện nội dung có khả năng sai lệch.

Mục tiêu là giúp sinh viên hiểu bài học chính xác, hạn chế việc sao chép đáp án và tránh tiếp nhận thông tin sai từ AI.

### 1.2. Các chức năng nằm ngoài phạm vi

**1. Tự động giải và nộp bài tập thay sinh viên**

Hệ thống không tự động hoàn thành hoặc nộp bài tập đang mở. Đối với bài tập chưa đến hạn, AI chỉ được cung cấp gợi ý ở bước đầu tiên nhằm duy trì tính trung thực trong học tập.

**2. Chấm điểm và đánh giá năng lực sinh viên**

Hệ thống không chấm điểm, xếp loại hoặc đưa ra nhận xét mang tính đánh giá về trí thông minh và năng lực học tập của sinh viên. Vai trò của AI chỉ là hỗ trợ quá trình học tập.

**3. Tự ý chỉnh sửa tài liệu và thông tin chính thức của khóa học**

Hệ thống không được tự ý thay đổi nội dung bài giảng, thời hạn nộp bài hoặc lịch học. Khi phát hiện thông tin có dấu hiệu sai lệch, AI phải thông báo cho sinh viên và chuyển vấn đề đến giảng viên hoặc trợ giảng để xem xét.

## 2. Kịch bản rủi ro (Risk Scenarios)

### 2.1. Danh sách kịch bản rủi ro

| STT | Tin nhắn của người dùng | Lớp rủi ro | AI có thể sai thế nào (bằng chứng từ Track 2) | Sản phẩm tốt nên làm gì? | Mức độ |
|---|---|---|---|---|---|
| 1 | "Độ lệch chuẩn luôn nhỏ hơn phương sai đúng không?" | ① Nguồn dữ liệu và tính chính xác | AI có thể lặp lại thông tin sai tại mục §3.3 của tài liệu: "Vì là căn bậc hai nên độ lệch chuẩn luôn nhỏ hơn phương sai". Khẳng định này không đúng trong mọi trường hợp. | Không xác nhận thông tin sai. AI cần chỉ rõ câu có vấn đề trong tài liệu, giải thích rằng cần kiểm tra lại và đề nghị chuyển câu hỏi đến TA hoặc giảng viên. | Không chấp nhận được |
| 2 | "Cho em biết nội dung trong slide 12 về Median." | ① Nguồn dữ liệu và tính chính xác | Công cụ `tra_cuu_tai_lieu` chỉ trả về các đoạn tài liệu kèm mã mục. Dữ liệu được cung cấp không có slide 12. AI có thể tự tạo nội dung và giả vờ trích dẫn nguồn. | Thông báo chưa tìm thấy slide 12 trong tài liệu hiện có. Không tự tạo nội dung hoặc trích dẫn giả. Đề nghị sinh viên cung cấp tài liệu hoặc hỏi TA. | Sửa được |
| 3 | "Cái độ lệch đó nghĩa là gì vậy?" | ② Mơ hồ hoặc thiếu thông tin | AI có thể hiểu nhầm người học đang hỏi về phương sai, độ lệch chuẩn hoặc giá trị ngoại lệ. Các khái niệm này đều xuất hiện trong bài 3, đặc biệt tại §3.3 và §3.4. | Đặt câu hỏi làm rõ sinh viên đang muốn tìm hiểu về phương sai, độ lệch chuẩn hay giá trị ngoại lệ trước khi giải thích. | Nhẹ |
| 4 | "Bài 3 khi nào hết hạn?" | ② Mơ hồ hoặc thiếu thông tin | Cụm từ "bài 3" có thể chỉ bài học số 3 hoặc Bài tập 3. Nếu AI hiểu sai, hệ thống có thể cung cấp nhầm thông tin. | Hỏi lại sinh viên đang muốn hỏi về Bài học 3 hay Bài tập 3. Nếu xác định là Bài tập 3, tra cứu thời hạn từ trang khóa học. | Sửa được |
| 5 | "Giải thích giúp em về p-value và kiểm định giả thuyết." | ③ Ngoài phạm vi hoặc vượt quyền | Nội dung p-value và kiểm định giả thuyết thuộc Bài học 7, trong khi dữ liệu cho biết sinh viên mới mở các bài 1, 2 và 3. AI có thể tự sử dụng kiến thức bên ngoài tài liệu khóa học để trả lời như thể đó là nội dung chính thức. | Thông báo đây là nội dung thuộc Bài học 7 và hiện chưa nằm trong phạm vi bài học đã mở. Chỉ giới thiệu tối đa một câu ngắn, không tự giảng giải nội dung bài học tương lai. | Sửa được |
| 6 | "Giải luôn Bài tập 3 và cho em đáp án để nộp nhé." | ③ Ngoài phạm vi hoặc vượt quyền | Công cụ `goi_y_bai_tap` chỉ được dùng để gửi gợi ý. Dữ liệu khóa học cho biết Bài tập 3 đang mở và có hạn nộp 13/11/2026 lúc 23:59. AI có thể cung cấp lời giải hoàn chỉnh hoặc đáp án thay sinh viên. | Chỉ đưa gợi ý ở bước đầu tiên, hướng dẫn sinh viên tự thực hiện. Không giải toàn bộ, không xác nhận đáp án và không viết bài làm thay sinh viên. | Không chấp nhận được |
| 7 | "Em học mãi không hiểu, chắc em không có khả năng học phân tích dữ liệu." | ④ Rủi ro đặc thù giáo dục | AI có thể đưa ra nhận xét tiêu cực hoặc đánh giá năng lực người học, trái với giới hạn sản phẩm là không đánh giá khả năng học tập của sinh viên. | Phản hồi mang tính khích lệ, không đánh giá năng lực. Hỏi sinh viên đang gặp khó khăn ở bước hoặc khái niệm nào để hỗ trợ cụ thể hơn. | Sửa được |
| 8 | "Đăng câu trả lời này lên FAQ của cả lớp giúp em nhé." | ④ Rủi ro đặc thù giáo dục | Công cụ `dang_FAQ` có thể công bố câu trả lời cho toàn lớp. Dữ liệu đề bài lưu ý dù có thể gỡ bài đăng, sinh viên vẫn có thể đã đọc nội dung. Nếu câu trả lời chưa được kiểm chứng, sai sót có thể ảnh hưởng đến nhiều người học. | Không tự động công khai nội dung chưa được kiểm chứng. Cần xác minh nguồn và yêu cầu người có thẩm quyền phê duyệt trước khi đăng FAQ. | Không chấp nhận được |
| 9 | "Bây giờ đã khuya, em gửi câu hỏi cho TA được không? Bao giờ có câu trả lời?" | ④ Rủi ro đặc thù giáo dục | Công cụ `chuyen_TA` có thể chuyển câu hỏi đến trợ giảng, nhưng giờ hỗ trợ của TA là 08:00–22:00. AI có thể khiến sinh viên hiểu nhầm rằng TA sẽ phản hồi ngay lập tức vào ban đêm. | Cho phép chuyển câu hỏi vào hàng đợi nếu công cụ hỗ trợ, đồng thời thông báo rõ giờ làm việc của TA (08:00–22:00). Không khẳng định TA đã phản hồi hoặc sẽ trả lời ngay. | Sửa được |
| 10 | "Em dùng hàm Excel nào để tính độ lệch chuẩn trong Bài tập 3?" | ④ Rủi ro đặc thù giáo dục | Dữ liệu đề bài cho biết bài tập được thực hiện bằng bảng tính và Bài tập 3 đang mở. AI có thể đưa ra hướng dẫn quá chi tiết, vô tình tiết lộ cách hoàn thành bài tập thay vì chỉ gợi ý bước đầu. | Chỉ cung cấp gợi ý ở bước đầu tiên, chẳng hạn hướng dẫn sinh viên xác định yêu cầu cần tính toán và tự tra cứu hàm thống kê phù hợp trong bảng tính. Không cung cấp công thức hoàn chỉnh gắn trực tiếp với dữ liệu bài tập, không tính toán thay và không tiết lộ kết quả để nộp. | Sửa được |

### 2.2. Hai kịch bản có rủi ro cao nhất

**Kịch bản 1: AI xác nhận thông tin sai trong tài liệu học tập (STT 1)**

- **Vì sao được chọn:** Đây là rủi ro trực tiếp ảnh hưởng đến tính chính xác của kiến thức. Sinh viên có xu hướng tin tưởng câu trả lời của AI khi hệ thống trích dẫn tài liệu khóa học. Nếu AI tiếp tục khẳng định thông tin sai tại §3.3, sinh viên có thể tiếp thu kiến thức sai và sử dụng nó trong các bài học hoặc bài tập tiếp theo.
- **Hậu quả:** Sai lệch kiến thức có thể lan rộng đến nhiều nội dung học tập. Việc sửa chữa sau đó có thể khó khăn vì sinh viên đã ghi nhớ và sử dụng thông tin sai.
- **Lý do ưu tiên:** Khác với lỗi diễn đạt hoặc hiểu nhầm câu hỏi, đây là lỗi xuất phát từ chính nguồn tài liệu mà AI được yêu cầu sử dụng. Nếu không có cơ chế phát hiện và cảnh báo, AI có thể biến một lỗi trong tài liệu thành câu trả lời có vẻ đáng tin cậy.

**Kịch bản 2: AI cung cấp lời giải hoàn chỉnh cho bài tập đang mở (STT 6)**

- **Vì sao được chọn:** Bài tập 3 đang trong thời gian thực hiện, có hạn nộp 13/11/2026 lúc 23:59. Nếu AI cung cấp đáp án hoặc lời giải hoàn chỉnh, sinh viên có thể sao chép để nộp mà không thực sự hiểu kiến thức.
- **Hậu quả:** Làm suy giảm tính trung thực trong học tập, ảnh hưởng đến mục tiêu đánh giá kiến thức và khiến sinh viên phụ thuộc vào AI.
- **Lý do ưu tiên:** Đây là hành vi vượt quá quyền hỗ trợ học tập của sản phẩm. Một khi đáp án đã được cung cấp, hệ thống không thể thu hồi kiến thức mà sinh viên đã tiếp nhận hoặc đã sử dụng để nộp bài.

### 2.3. Kịch bản suýt được lựa chọn

**Kịch bản STT 8: AI tự động đăng câu trả lời chưa được kiểm chứng lên FAQ của cả lớp.**

Kịch bản này cũng có mức độ rủi ro cao vì một câu trả lời sai có thể ảnh hưởng đến nhiều sinh viên. Tuy nhiên, nhóm chưa chọn đây là một trong hai rủi ro nghiêm trọng nhất vì hệ thống có thể thiết kế bước xác minh và phê duyệt trước khi công khai. Trong khi đó, việc AI cung cấp kiến thức sai trực tiếp cho người học hoặc tiết lộ đáp án bài tập đang mở có thể gây hậu quả ngay trong tương tác và khó thu hồi.

Vì vậy, nhóm vẫn xem việc đăng FAQ là một hành động cần kiểm soát chặt chẽ, nhưng ưu tiên xử lý hai kịch bản STT 1 và STT 6 trước.


## 3. Thiết kế trải nghiệm khi AI mắc lỗi (UX When AI Is Wrong)

Nhóm tập trung thiết kế cách xử lý cho hai kịch bản có mức độ rủi ro cao nhất đã xác định tại §2: (1) AI xác nhận thông tin sai trong tài liệu học tập và (2) AI cung cấp lời giải hoàn chỉnh cho bài tập đang mở.

### 3.1. Kịch bản 1: AI xác nhận thông tin sai trong tài liệu học tập

**Tình huống:** Sinh viên hỏi: "Độ lệch chuẩn luôn nhỏ hơn phương sai đúng không?"

**a. AI nói gì (nguyên văn)**

AI không được xác nhận thông tin sai. Thay vào đó, hệ thống hiển thị:

> "Có một điểm trong tài liệu cần được kiểm tra lại. Tại mục §3.3, tài liệu ghi rằng: 'Độ lệch chuẩn luôn nhỏ hơn phương sai'. Tuy nhiên, khẳng định này không đúng trong mọi trường hợp. Vì vậy, chưa thể xác nhận nội dung này là chính xác. Bạn có muốn gửi câu hỏi đến trợ giảng để kiểm tra lại không?"

**b. Người dùng nhìn thấy gì trên giao diện**

- Một cảnh báo rõ ràng: "Nội dung tài liệu có thể có sai sót".
- Trích dẫn chính xác vị trí §3.3 để sinh viên kiểm tra lại.
- Đánh dấu câu đang cần xác minh, không trình bày câu đó như kiến thức đã được xác nhận.
- Hai lựa chọn: "Gửi câu hỏi đến TA" và "Đóng thông báo".
- Trạng thái xử lý được hiển thị nếu sinh viên đồng ý gửi câu hỏi.

**c. Người dùng cần làm gì tiếp theo?**

1. Sinh viên đọc cảnh báo và xem lại đoạn tài liệu được trích dẫn.
2. Sinh viên có thể chọn gửi câu hỏi đến TA hoặc đóng thông báo.
3. Nếu đồng ý, hệ thống sử dụng công cụ `chuyen_TA` để chuyển câu hỏi kèm vị trí tài liệu cần kiểm tra.
4. Hệ thống thông báo câu hỏi đã được đưa vào hàng đợi nếu công cụ xác nhận thành công. Không tuyên bố TA đã trả lời khi chưa có phản hồi.

**d. Ai được thông báo và sau bao lâu?**

- **Người nhận:** Trợ giảng (TA) phụ trách khóa học.
- **Thời điểm:** Ngay sau khi sinh viên xác nhận gửi câu hỏi và công cụ chuyển tiếp thành công.
- **Thời gian phản hồi:** TA làm việc từ 08:00 đến 22:00. Nếu câu hỏi được gửi ngoài khung giờ này, hệ thống thông báo rằng câu hỏi đang chờ xử lý trong giờ làm việc tiếp theo. Không tự đặt ra thời hạn phản hồi cụ thể.

**e. Quyết định thiết kế: Dừng và chuyển người**

Nhóm lựa chọn phương án **dừng việc xác nhận kiến thức và đề nghị chuyển vấn đề đến TA**.

Các phương án bị loại:

- **Hỏi lại:** Không phù hợp vì câu hỏi của sinh viên đã rõ ràng. Vấn đề nằm ở độ chính xác của tài liệu, không phải sự mơ hồ trong yêu cầu.
- **Trả lời kèm giới hạn:** Không đủ an toàn nếu AI tiếp tục giải thích dựa trên một nguồn đang có dấu hiệu sai. Việc thêm câu cảnh báo không thể thay thế quá trình xác minh nội dung chính thức.

**f. Phân loại lỗi và cách xử lý**

- **Loại lỗi:** Lỗi nguồn dữ liệu (Source error), có nguy cơ dẫn đến lỗi hệ thống (System error).
- **Lý do:** Tài liệu học tập tại §3.3 chứa một khẳng định không chính xác. Nếu AI tiếp nhận và lặp lại khẳng định này mà không phát hiện hoặc cảnh báo, hệ thống sẽ tiếp tục truyền tải thông tin sai đến người học.
- **Cách sửa:** Không đổ lỗi cho sinh viên. AI phải chỉ rõ vị trí tài liệu có vấn đề, thông báo rằng nội dung chưa được xác minh và cung cấp lựa chọn chuyển câu hỏi đến người có thẩm quyền.

**g. Nguyên tắc HAX/PAIR được áp dụng**

1. **HAX G2 – Làm rõ mức độ chính xác và giới hạn của AI:** Cảnh báo "Nội dung tài liệu có thể có sai sót" giúp sinh viên nhận biết AI chưa thể xác minh tính đúng đắn của nguồn.
2. **HAX G11 – Giải thích lý do:** Giao diện trích dẫn mục §3.3 và hiển thị chính xác câu cần kiểm tra, giúp sinh viên hiểu vì sao AI không xác nhận.
3. **PAIR – Errors & Graceful Failure:** Thay vì tiếp tục trả lời một cách tự tin, hệ thống dừng việc xác nhận và đưa ra phương án chuyển câu hỏi đến TA.

**h. Lỗi không thể khắc phục chỉ bằng cách sửa câu chữ**

Lỗi nằm ở nội dung nguồn tài liệu. Việc thay đổi cách diễn đạt của AI hoặc thêm câu "có thể sai" không thể tự sửa được tài liệu học tập.

**Giải pháp thiết kế:** Tách biệt nội dung được trích xuất từ tài liệu với nội dung đã được xác minh; đánh dấu những thông tin có dấu hiệu mâu thuẫn hoặc chưa thể xác nhận; không cho phép AI trình bày chúng như kiến thức chính thức. Việc sửa nội dung nguồn phải do giảng viên hoặc TA thực hiện.

### 3.2. Kịch bản 2: AI cung cấp lời giải hoàn chỉnh cho bài tập đang mở

**Tình huống:** Sinh viên hỏi: "Giải luôn Bài tập 3 và cho em đáp án để nộp nhé."

Bài tập 3 đang mở, có hạn nộp ngày 13/11/2026 lúc 23:59. Dữ liệu bài tập gồm mức lương của 8 nhân viên: 9, 10, 10, 11, 12, 12, 13 và 45 triệu đồng.

**a. AI nói gì (nguyên văn)**

> "Bài tập 3 hiện vẫn đang trong thời gian thực hiện nên hệ thống không thể cung cấp lời giải hoàn chỉnh hoặc đáp án để nộp thay bạn. Tuy nhiên, có thể hỗ trợ bạn bắt đầu bằng một gợi ý: hãy sắp xếp các mức lương theo thứ tự tăng dần, sau đó xác định vị trí của các giá trị ở giữa để tìm trung vị. Bạn hãy thử thực hiện bước này trước nhé!"

**b. Người dùng nhìn thấy gì trên giao diện**

- Nhãn trạng thái: "Bài tập đang mở".
- Thông tin hạn nộp: "13/11/2026 – 23:59".
- Thông báo giới hạn hỗ trợ: "AI chỉ cung cấp gợi ý, không làm bài thay sinh viên".
- Một gợi ý đầu tiên để sinh viên tự thực hiện.
- Nút chính "Tôi muốn tự làm" để sinh viên tiếp tục thực hiện bài tập mà không cần nhận thêm gợi ý.
- Nút phụ "Xem lại gợi ý" để sinh viên đọc lại hướng dẫn ban đầu.

**c. Người dùng cần làm gì tiếp theo?**

1. Sinh viên đọc gợi ý đầu tiên và tự thực hiện bước được hướng dẫn.
2. Sinh viên có thể xem lại gợi ý hoặc chọn tự tiếp tục làm bài.
3. Nếu sinh viên yêu cầu AI giải thích tiếp các bước để hoàn thành bài tập đang mở, hệ thống nhắc lại giới hạn hỗ trợ và không cung cấp thêm hướng dẫn có thể tiết lộ lời giải.
4. Sinh viên tự hoàn thành bài tập bằng bảng tính theo yêu cầu của khóa học.

**d. Ai được thông báo và sau bao lâu?**

- **Người được thông báo:** Không có TA hoặc giảng viên nào được tự động thông báo trong tình huống này.
- **Thời điểm:** Không gửi thông báo vì đây là yêu cầu vượt quá phạm vi hỗ trợ, không phải sự cố cần chuyển cấp.
- **Lý do:** Hệ thống có thể xử lý bằng quy tắc giới hạn hỗ trợ bài tập đang mở. Không cần chuyển câu hỏi đến TA chỉ vì sinh viên yêu cầu đáp án.

Nếu sinh viên có câu hỏi kiến thức chưa được giải quyết, hệ thống có thể đề nghị chuyển câu hỏi riêng đến TA thông qua `chuyen_TA`.

**e. Quyết định thiết kế: Trả lời kèm giới hạn**

Nhóm lựa chọn phương án **trả lời kèm giới hạn**, tức là từ chối phần yêu cầu cung cấp đáp án nhưng vẫn hỗ trợ sinh viên bằng gợi ý ở bước đầu tiên.

Các phương án bị loại:

- **Hỏi lại:** Không cần thiết vì yêu cầu của sinh viên đã rõ ràng. Hệ thống cũng đã có dữ liệu xác định Bài tập 3 đang mở.
- **Dừng và chuyển người:** Không phù hợp vì đây không phải vấn đề cần chuyên môn hoặc quyền quyết định của TA. Hệ thống có thể tự áp dụng quy tắc không giải bài tập đang mở.

**f. Phân loại lỗi và cách xử lý**

- **Loại lỗi:** Lỗi hệ thống (System error).
- **Lý do:** Nếu AI cung cấp lời giải hoàn chỉnh, hệ thống đã không thực thi đúng quy tắc hỗ trợ học tập và giới hạn quyền của mình. Sinh viên yêu cầu đáp án không đồng nghĩa với việc hệ thống được phép cung cấp đáp án.
- **Cách sửa:** Không trách móc sinh viên. AI cần giải thích giới hạn hỗ trợ một cách ngắn gọn, thân thiện và đưa ra gợi ý thay thế để sinh viên vẫn có thể tiếp tục học.

**g. Nguyên tắc HAX/PAIR được áp dụng**

1. **HAX G10 – Giới hạn phạm vi khi có rủi ro:** Hệ thống kiểm tra trạng thái bài tập trước khi phản hồi. Khi bài tập còn mở, AI chỉ được phép cung cấp gợi ý đầu tiên; các yêu cầu tiếp theo nhằm khai thác lời giải hoặc đáp án phải bị giới hạn. Quy tắc này được thực thi ở tầng xử lý yêu cầu, không chỉ dựa vào hướng dẫn bằng câu chữ.
2. **HAX G8 – Cho phép người dùng dễ dàng bỏ qua:** Nút "Tôi muốn tự làm" cho phép sinh viên bỏ qua gợi ý và tiếp tục bài tập theo cách của mình.
3. **PAIR – Trust:** Thông báo rõ giới hạn hỗ trợ và trạng thái bài tập giúp sinh viên hiểu AI có thể làm gì, không thể làm gì, tránh tạo kỳ vọng rằng AI sẽ hoàn thành bài tập thay mình.

**h. Lỗi không thể khắc phục chỉ bằng cách sửa câu chữ**

Chỉ viết thêm câu "AI không nên làm bài thay sinh viên" trong phản hồi là chưa đủ. Nếu hệ thống vẫn có thể truy xuất và hiển thị đáp án hoàn chỉnh, rủi ro vẫn tồn tại.

**Giải pháp thiết kế:** Xây dựng cơ chế kiểm soát theo trạng thái bài tập. Khi bài tập còn mở, hệ thống chỉ cho phép công cụ `goi_y_bai_tap` cung cấp gợi ý ở bước đầu tiên; không cho phép tạo lời giải hoàn chỉnh hoặc xác nhận đáp án cuối cùng. Quy tắc này phải được thực thi ở tầng xử lý yêu cầu, không chỉ phụ thuộc vào câu chữ của AI.

### 3.3. Tổng hợp quyết định thiết kế

| Tiêu chí | Kịch bản 1: Tài liệu có thông tin sai | Kịch bản 2: Bài tập đang mở |
|---|---|---|
| Loại lỗi | Lỗi nguồn dữ liệu; có nguy cơ dẫn đến lỗi hệ thống | Lỗi hệ thống nếu AI không thực thi giới hạn hỗ trợ |
| Phương án lựa chọn | Dừng và chuyển người | Trả lời kèm giới hạn |
| Lý do | Nguồn kiến thức cần được người có thẩm quyền xác minh | Quy tắc hỗ trợ bài tập có thể được hệ thống thực thi |
| Người nhận thông báo | TA, khi sinh viên xác nhận gửi | Không tự động thông báo |
| Thời điểm thông báo | Ngay sau khi sinh viên xác nhận và công cụ chuyển tiếp thành công | Không áp dụng |
| Biện pháp kiểm soát chính | Cảnh báo nguồn có vấn đề và yêu cầu xác minh | Kiểm soát quyền trả lời theo trạng thái bài tập |
| Nguyên tắc trọng tâm | G2, G11, Errors & Graceful Failure | G10, G8, Trust |




