# HCM-KS26-CNTT1_KNPromtingAl_Session06_BTPT
# BÁO CÁO BÀI TẬP PHÂN TÍCH
## SO SÁNH TRADE-OFF CÁC GIẢI PHÁP RA LỆNH CHO ỨNG DỤNG AI TRONG HỌC TẬP & NGHIÊN CỨU

**Họ và tên:** Võ Trần Tháp
**Lớp:** HCM-KS26-CNTT1  
**Tên đề tài:** So sánh hai phương pháp Prompting trong xây dựng AI Study Assistant.

---

# I. GIỚI THIỆU BÀI TOÁN

## 1. Bối cảnh

Trong quá trình học tập và đào tạo, việc sử dụng AI để giải thích kiến thức và tự động chấm bài đang ngày càng phổ biến.

Tuy nhiên, nếu viết Prompt quá ngắn, AI có thể hiểu sai yêu cầu, bỏ sót thông tin hoặc đưa ra kết quả chấm điểm thiếu chính xác. Ngược lại, nếu Prompt quá dài và có nhiều ràng buộc, người dùng sẽ mất thời gian xây dựng, đồng thời tiêu tốn nhiều token hơn.

Vì vậy, bài toán đặt ra là so sánh hai phương pháp viết Prompt khác nhau để tìm ra giải pháp phù hợp nhất cho hệ thống AI hỗ trợ học tập.

## 2. Mục tiêu

- Xây dựng hai giải pháp Prompting cho cùng một bài toán.
- Phân tích ưu điểm và nhược điểm của từng giải pháp.
- So sánh mức độ hiệu quả dựa trên các tiêu chí cụ thể.
- Đánh giá sự đánh đổi giữa độ đơn giản, chi phí token và khả năng kiểm soát lỗi.
- Lựa chọn giải pháp tối ưu và thực hiện chạy thử.

## 3. Mô tả bài toán

Xây dựng một AI Study Assistant có hai chức năng:

**Chức năng 1 – Feynman Prompt gia sư:**
- Giải thích kiến thức bằng ngôn ngữ đơn giản.
- Đưa ra ví dụ thực tế.
- Đặt câu hỏi kiểm tra mức độ hiểu bài.

**Chức năng 2 – Rubric chấm bài tự động:**
- Phân tích câu trả lời của người học.
- Đánh giá theo các tiêu chí có sẵn.
- Chấm điểm và giải thích lý do.
- Đề xuất cách sửa lỗi và cải thiện bài làm.

---

# II. ĐỀ XUẤT HAI GIẢI PHÁP PROMPT

## 1. Giải pháp 1: Prompt đơn giản, ngắn gọn

### 1.1. Nội dung Prompt

**PROMPT 1 – SIMPLE PROMPT**

Bạn là một trợ lý AI hỗ trợ học tập.

Hãy sử dụng phương pháp Feynman để giải thích chủ đề tôi cung cấp bằng ngôn ngữ đơn giản, dễ hiểu, có ví dụ thực tế và câu hỏi kiểm tra kiến thức.

Sau đó, sử dụng Rubric để đánh giá bài làm của người học. Hãy chấm điểm theo từng tiêu chí, nhận xét ưu điểm, chỉ ra lỗi sai và đề xuất cách cải thiện.

Thông tin đầu vào:
- Chủ đề: [Nhập chủ đề]
- Tài liệu: [Nhập tài liệu]
- Câu hỏi: [Nhập câu hỏi]
- Bài làm: [Nhập câu trả lời]
- Rubric: [Nhập tiêu chí chấm điểm]

Hãy trình bày kết quả rõ ràng, dễ hiểu và có bảng điểm tổng kết.

### 1.2. Đặc điểm của giải pháp 1

- Cấu trúc Prompt đơn giản.
- Ít câu lệnh và ràng buộc.
- Dễ viết, dễ sử dụng.
- Phù hợp với những yêu cầu học tập cơ bản.
- Không quy định chi tiết cách xử lý dữ liệu thiếu hoặc sai lệch.

**Ưu điểm:**
- Tiết kiệm thời gian xây dựng Prompt.
- Ít tiêu tốn token hơn.
- Người mới học Prompt Engineering dễ tiếp cận.
- Có thể sử dụng linh hoạt với nhiều chủ đề.

**Nhược điểm:**
- AI có thể bỏ sót một số tiêu chí chấm điểm.
- Chưa có quy định cụ thể khi dữ liệu đầu vào bị trống.
- Kết quả có thể thiếu nhất quán giữa các lần chạy.
- Phản hồi đôi khi còn chung chung, chưa chỉ rõ cách sửa lỗi.

---

## 2. Giải pháp 2: Prompt chi tiết, có nhiều ràng buộc

### 2.1. Nội dung Prompt

**PROMPT 2 – ADVANCED PROMPT**

**VAI TRÒ (ROLE)**

Bạn là AI Study Assistant, chuyên hỗ trợ học tập và nghiên cứu. Bạn có nhiệm vụ giải thích kiến thức theo phương pháp Feynman và đánh giá bài làm bằng hệ thống Rubric.

**BỐI CẢNH (CONTEXT)**

Hệ thống được sử dụng để đào tạo nhân viên mới tại một cửa hàng kinh doanh trực tuyến. Người học cần nắm được quy trình tiếp nhận đơn hàng, kiểm tra thông tin, xác nhận đơn và bàn giao vận chuyển.

**NHIỆM VỤ (TASK)**

Thực hiện hai nhiệm vụ:

1. Gia sư Feynman:
   - Giải thích kiến thức bằng ngôn ngữ đơn giản.
   - Chia nội dung thành các bước nhỏ.
   - Sử dụng ví dụ thực tế.
   - Chỉ ra những lỗi hiểu sai phổ biến.
   - Đặt hai câu hỏi kiểm tra kiến thức.

2. Chấm bài bằng Rubric:
   - Đọc và phân tích câu trả lời.
   - Đối chiếu từng tiêu chí.
   - Chấm điểm theo đúng thang điểm quy định.
   - Giải thích lý do cho từng mức điểm.
   - Đưa ra nhận xét và hướng cải thiện cụ thể.

**DỮ LIỆU ĐẦU VÀO (INPUT)**

- Chủ đề: [Nhập chủ đề]
- Tài liệu kiến thức: [Nhập tài liệu]
- Trình độ người học: [Nhập trình độ]
- Câu hỏi: [Nhập câu hỏi]
- Câu trả lời: [Nhập bài làm]
- Rubric: [Nhập tiêu chí và thang điểm]

**QUY TRÌNH XỬ LÝ (PROCESS)**

Bước 1: Kiểm tra tính đầy đủ và hợp lệ của dữ liệu đầu vào.

Bước 2: Phân tích tài liệu và xác định kiến thức trọng tâm.

Bước 3: Giải thích kiến thức theo phương pháp Feynman.

Bước 4: Phân tích câu trả lời và đối chiếu với yêu cầu bài tập.

Bước 5: Chấm điểm từng tiêu chí theo Rubric. Không tự ý thay đổi trọng số hoặc thang điểm.

Bước 6: Đưa ra nhận xét, chỉ rõ lỗi sai và hướng sửa chữa.

Bước 7: Đặt câu hỏi vận dụng để kiểm tra mức độ hiểu bài.

**RÀNG BUỘC VÀ XỬ LÝ LỖI (CONSTRAINTS)**

- Nếu tài liệu bị trống, yêu cầu người dùng bổ sung.
- Nếu câu trả lời bị trống, không thực hiện chấm điểm.
- Nếu Rubric bị thiếu, thông báo và đề xuất Rubric thay thế trước khi chấm.
- Nếu dữ liệu không liên quan đến chủ đề, cảnh báo người dùng.
- Nếu dữ liệu mâu thuẫn, phải chỉ ra nội dung mâu thuẫn.
- Không tự tạo thông tin rồi khẳng định đó là dữ liệu từ tài liệu.
- Không tự ý thay đổi thang điểm.
- Không cho điểm tối đa nếu bài làm chưa đáp ứng tiêu chí.
- Phân biệt lỗi kiến thức, lỗi diễn đạt và nội dung còn thiếu.
- Mỗi nhận xét phải có căn cứ cụ thể.

**ĐỊNH DẠNG ĐẦU RA (OUTPUT)**

1. Tóm tắt kiến thức:
   - Nội dung chính.
   - Giải thích Feynman.
   - Ví dụ thực tế.

2. Bảng chấm điểm:

| Tiêu chí | Điểm tối đa | Điểm đạt | Nhận xét |
|---|---:|---:|---|

3. Tổng kết:
   - Tổng điểm.
   - Mức độ hoàn thành.

4. Phản hồi cải thiện:
   - Điểm mạnh.
   - Điểm yếu.
   - Lỗi cần sửa.
   - Hướng khắc phục.

5. Câu hỏi kiểm tra:
   - Hai câu hỏi vận dụng.

**PHONG CÁCH (STYLE)**

Sử dụng tiếng Việt rõ ràng, dễ hiểu, trình bày khoa học. Phản hồi mang tính xây dựng, không chỉ đưa ra điểm số mà phải giúp người học hiểu bản chất kiến thức.

### 2.2. Đặc điểm của giải pháp 2

- Có cấu trúc Prompt rõ ràng.
- Phân chia nhiệm vụ thành nhiều bước.
- Quy định cụ thể điều kiện đầu vào và đầu ra.
- Có cơ chế xử lý các trường hợp dữ liệu bất thường.
- Kiểm soát quá trình chấm điểm bằng Rubric.

**Ưu điểm:**
- Hạn chế AI hiểu sai yêu cầu.
- Kết quả có cấu trúc và nhất quán hơn.
- Kiểm soát tốt các trường hợp dữ liệu thiếu hoặc sai lệch.
- Phản hồi chi tiết và có tính ứng dụng cao.
- Phù hợp với quy trình đào tạo cần đánh giá nhiều người học.

**Nhược điểm:**
- Tốn nhiều token hơn.
- Mất thời gian xây dựng Prompt.
- Cần cập nhật khi nghiệp vụ hoặc tiêu chí đánh giá thay đổi.
- Có thể quá phức tạp đối với những yêu cầu đơn giản.

---

# III. SO SÁNH TRADE-OFF GIỮA HAI GIẢI PHÁP

## 1. Bảng so sánh tổng quan

| Tiêu chí | Giải pháp 1 (Đơn giản) | Giải pháp 2 (Chi tiết) |
|---|---|---|
| Độ dễ hiểu | Cao | Trung bình |
| Thời gian xây dựng | Nhanh | Lâu hơn |
| Tốn token | Ít | Nhiều hơn |
| Độ dài Prompt | Ngắn | Dài |
| Khả năng kiểm soát AI | Trung bình | Tốt |
| Độ nhất quán đầu ra | Trung bình | Cao hơn |
| Chặn lỗi dữ liệu trống | Trung bình, không có quy tắc cụ thể | Tốt |
| Xử lý dữ liệu sai lệch | Hạn chế | Tốt hơn |
| Độ chi tiết phản hồi | Cơ bản | Chi tiết |
| Khả năng mở rộng | Khá linh hoạt | Tốt nếu cập nhật đúng cấu trúc |
| Phù hợp | Nhu cầu học tập đơn giản | Đào tạo và đánh giá có quy trình |

## 2. Phân tích Trade-off

### 2.1. Độ đơn giản và độ kiểm soát

Giải pháp 1 có ít câu lệnh nên người dùng dễ hiểu và dễ sử dụng. Tuy nhiên, do thiếu các quy định chi tiết, AI có thể tự diễn giải yêu cầu theo nhiều cách khác nhau.

Giải pháp 2 có nhiều hướng dẫn và điều kiện cụ thể hơn, giúp AI bám sát nhiệm vụ. Đổi lại, người dùng cần đầu tư thời gian để xây dựng và duy trì Prompt.

### 2.2. Chi phí token và chất lượng đầu ra

Giải pháp 1 sử dụng ít token hơn vì nội dung ngắn gọn. Điều này phù hợp với các tác vụ đơn giản hoặc khi cần tiết kiệm chi phí xử lý.

Giải pháp 2 tiêu tốn nhiều token hơn do phải mô tả vai trò, nhiệm vụ, quy trình, ràng buộc và định dạng đầu ra. Tuy nhiên, lượng hướng dẫn bổ sung giúp giảm sự mơ hồ và tăng khả năng kiểm soát kết quả.

Lưu ý: Prompt dài không mặc nhiên đảm bảo AI chính xác hơn. Chất lượng còn phụ thuộc vào dữ liệu đầu vào, mô hình và cách thiết kế chỉ dẫn.

### 2.3. Khả năng xử lý lỗi

Giải pháp 1 chưa quy định rõ cách xử lý khi thiếu tài liệu, câu trả lời trống hoặc Rubric không hợp lệ. Vì vậy, AI có thể vẫn tạo ra kết quả dù dữ liệu chưa đủ căn cứ.

Giải pháp 2 có các điều kiện kiểm tra cụ thể. Khi dữ liệu thiếu, AI phải thông báo và yêu cầu bổ sung thay vì tự suy đoán.

### 2.4. Khả năng mở rộng

Giải pháp 1 phù hợp với các tác vụ nhỏ nhưng khi bổ sung thêm nhiều chức năng, Prompt có thể trở nên khó kiểm soát.

Giải pháp 2 có cấu trúc rõ ràng nên dễ bổ sung tiêu chí, thay đổi quy trình và mở rộng sang các lĩnh vực đào tạo khác.

## 3. Đánh giá tổng thể

| Tiêu chí | Giải pháp phù hợp hơn |
|---|---|
| Dễ sử dụng | Giải pháp 1 |
| Tiết kiệm token | Giải pháp 1 |
| Triển khai nhanh | Giải pháp 1 |
| Kiểm soát lỗi | Giải pháp 2 |
| Chấm điểm có căn cứ | Giải pháp 2 |
| Phản hồi chi tiết | Giải pháp 2 |
| Đào tạo có hệ thống | Giải pháp 2 |

**Nhận xét:** Không có giải pháp nào tốt nhất trong mọi trường hợp. Việc lựa chọn phụ thuộc vào mục tiêu, độ phức tạp của nhiệm vụ và mức độ chính xác mong muốn.

---

# IV. LỰA CHỌN GIẢI PHÁP TỐI ƯU

## 1. Phương án được lựa chọn

Em lựa chọn **Giải pháp 2 – Advanced Prompt**.

## 2. Lý do lựa chọn

Thứ nhất, bài toán yêu cầu kết hợp hai chức năng là Feynman Prompt gia sư và Rubric chấm bài tự động. Đây là quy trình có nhiều bước nên cần Prompt có cấu trúc rõ ràng.

Thứ hai, việc chấm điểm đòi hỏi tính nhất quán. Nếu không quy định cụ thể tiêu chí và thang điểm, AI có thể đánh giá bài làm thiếu đồng đều.

Thứ ba, dữ liệu đầu vào có thể bị trống, sai lệch hoặc thiếu thông tin. Giải pháp 2 có những điều kiện xử lý riêng, giúp hạn chế việc AI đưa ra kết quả không có căn cứ.

Thứ tư, giải pháp 2 phù hợp hơn khi triển khai lâu dài cho nhiều người học, nhiều chủ đề và nhiều dạng bài tập.

Mặc dù tiêu tốn nhiều token hơn, nhưng lợi ích về khả năng kiểm soát, tính nhất quán và chất lượng phản hồi đáng để đánh đổi trong bài toán này.

---

# V. CHẠY THỬ GIẢI PHÁP ĐƯỢC LỰA CHỌN

## 1. Dữ liệu đầu vào

Sử dụng Prompt 2 để kiểm tra tình huống thực tế.

**Chủ đề:** Quy trình xử lý đơn hàng trực tuyến.

**Tài liệu kiến thức:**
1. Tiếp nhận đơn hàng.
2. Kiểm tra thông tin khách hàng và sản phẩm.
3. Xác nhận đơn hàng.
4. Đóng gói sản phẩm.
5. Bàn giao cho đơn vị vận chuyển.

**Trình độ:** Nhân viên mới.

**Câu hỏi:** Hãy trình bày các bước xử lý một đơn hàng trực tuyến.

**Câu trả lời của người học:**

"Đầu tiên, nhân viên nhận đơn hàng từ hệ thống. Sau đó kiểm tra thông tin khách hàng và sản phẩm. Tiếp theo đóng gói sản phẩm rồi giao cho đơn vị vận chuyển."

**Rubric đánh giá:**

| Tiêu chí | Điểm tối đa |
|---|---:|
| Xác định đúng các bước trong quy trình | 4 |
| Trình bày đúng thứ tự | 2 |
| Giải thích rõ từng bước | 2 |
| Diễn đạt rõ ràng, logic | 2 |
| **Tổng cộng** | **10** |

## 2. Kết quả phản hồi của AI

### A. Giải thích kiến thức theo phương pháp Feynman

Quy trình xử lý đơn hàng trực tuyến là quá trình thực hiện các công việc từ khi cửa hàng nhận được đơn đặt hàng cho đến khi sản phẩm được chuyển cho đơn vị vận chuyển.

Ví dụ: Khi khách hàng đặt mua một chiếc áo trên mạng:

- Bước 1: Nhân viên nhận thông báo đơn hàng từ hệ thống.
- Bước 2: Kiểm tra thông tin khách hàng, địa chỉ và sản phẩm.
- Bước 3: Xác nhận đơn hàng để chuẩn bị thực hiện.
- Bước 4: Đóng gói sản phẩm cẩn thận.
- Bước 5: Bàn giao gói hàng cho đơn vị vận chuyển.

Có thể hiểu đơn giản rằng đây là một chuỗi công việc liên tiếp. Mỗi bước đều có vai trò quan trọng để đơn hàng được xử lý chính xác.

### B. Bảng chấm điểm

| Tiêu chí | Điểm tối đa | Điểm đạt | Nhận xét |
|---|---:|---:|---|
| Xác định đúng các bước | 4 | 3 | Thiếu bước xác nhận đơn hàng. |
| Trình bày đúng thứ tự | 2 | 2 | Các bước được trình bày đúng thứ tự cơ bản. |
| Giải thích rõ từng bước | 2 | 1 | Chưa giải thích mục đích của từng bước. |
| Diễn đạt rõ ràng, logic | 2 | 2 | Câu văn dễ hiểu, có liên kết. |
| **Tổng cộng** | **10** | **8** | |

### C. Tổng kết điểm

**Kết quả: 8/10 điểm – Hoàn thành tốt.**

Người học đã hiểu được phần lớn quy trình nhưng cần bổ sung bước xác nhận đơn hàng và giải thích rõ hơn các công đoạn.

### D. Phản hồi cải thiện

**Điểm mạnh:**
- Nắm được các bước quan trọng.
- Trình bày đúng trình tự cơ bản.
- Diễn đạt ngắn gọn, dễ hiểu.

**Điểm cần cải thiện:**
- Chưa đề cập bước xác nhận đơn hàng.
- Chưa giải thích lý do cần kiểm tra thông tin.
- Cần trình bày rõ hơn mục đích của từng công đoạn.

**Bài làm đề xuất sau khi cải thiện:**

"Đầu tiên, nhân viên tiếp nhận đơn hàng từ hệ thống. Tiếp theo, kiểm tra thông tin khách hàng, địa chỉ giao hàng và tình trạng sản phẩm. Sau đó, xác nhận đơn hàng để chuẩn bị xử lý. Tiếp theo, nhân viên đóng gói sản phẩm cẩn thận và kiểm tra lại đơn hàng. Cuối cùng, bàn giao sản phẩm cho đơn vị vận chuyển để giao đến khách hàng."

### E. Câu hỏi kiểm tra kiến thức

1. Tại sao cần kiểm tra thông tin khách hàng trước khi xác nhận đơn hàng?
2. Nếu bỏ qua bước xác nhận đơn hàng, cửa hàng có thể gặp những rủi ro gì?

## 3. Đánh giá kết quả chạy thử

Kết quả thử nghiệm cho thấy Prompt 2 đã thực hiện được các chức năng chính:

- Giải thích kiến thức theo phương pháp Feynman.
- Phân tích câu trả lời của người học.
- Đánh giá theo từng tiêu chí Rubric.
- Chỉ ra nội dung còn thiếu.
- Đưa ra phương án sửa bài cụ thể.
- Tạo câu hỏi kiểm tra kiến thức.

Qua đó, giải pháp được lựa chọn đáp ứng mục tiêu của bài toán và phù hợp hơn với quy trình đào tạo có nhiều bước.

Lưu ý: Điểm số 8/10 là kết quả chạy thử minh họa theo Rubric đã thiết kế, cần được đối chiếu với người hướng dẫn khi triển khai thực tế.

---

# VI. KẾT LUẬN

Qua quá trình phân tích và so sánh hai giải pháp Prompting, em nhận thấy mỗi phương pháp đều có những ưu điểm và hạn chế riêng.

Giải pháp 1 phù hợp với các yêu cầu đơn giản nhờ cấu trúc ngắn gọn, dễ sử dụng và tiết kiệm token. Trong khi đó, Giải pháp 2 phù hợp với các quy trình phức tạp hơn nhờ có cấu trúc rõ ràng, nhiều ràng buộc và khả năng xử lý dữ liệu bất thường tốt hơn.

Đối với bài toán xây dựng AI Study Assistant, em lựa chọn Giải pháp 2 vì cần đảm bảo tính nhất quán trong việc giải thích kiến thức, đánh giá bài làm và phản hồi cho người học.

Thông qua bài tập, em hiểu rằng tối ưu Prompt không phải là viết càng dài càng tốt mà là lựa chọn lượng thông tin và ràng buộc phù hợp với mục tiêu sử dụng.

**Bài học rút ra:** Một Prompt tốt cần cân bằng giữa chi phí, độ đơn giản, độ chính xác và khả năng kiểm soát. Đây chính là tư duy Trade-off quan trọng khi thiết kế và ứng dụng AI vào thực tế.
