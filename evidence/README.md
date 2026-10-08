# Phân tích kết quả Prompt V1 và V2

## Kết quả RAGAS

| Metric | Prompt V1 | Prompt V2 |
|---|---:|---:|
| Faithfulness | 0.9586 | 0.9530 |
| Answer relevancy | 0.9083 | 0.8929 |
| Context recall | 1.0000 | 1.0000 |
| Context precision | 0.9396 | 0.9417 |

## Nhận xét

Prompt V1 đạt điểm cao hơn V2 ở faithfulness và answer relevancy. Nguyên nhân có thể là V1 yêu cầu câu trả lời ngắn gọn, chỉ sử dụng context và không suy đoán ngoài tài liệu. Cách hướng dẫn đơn giản này giúp câu trả lời bám sát nguồn và giảm thông tin không cần thiết.

Prompt V2 yêu cầu câu trả lời có cấu trúc và giọng chuyên gia. Cách này phù hợp khi cần giải thích rõ ràng hơn, nhưng câu trả lời dài hơn có thể làm tăng nguy cơ thêm chi tiết không trực tiếp xuất hiện trong context, nên faithfulness thấp hơn một chút.

Hai phiên bản đều có context recall bằng 1.0, cho thấy retriever đã lấy được thông tin cần thiết cho các câu hỏi. Khác biệt chính đến từ cách LLM sử dụng context để tạo câu trả lời, không phải do thiếu context.

## Kết luận

V1 là lựa chọn phù hợp hơn cho pipeline hiện tại vì có faithfulness và answer relevancy cao hơn, đồng thời đạt mục tiêu `faithfulness >= 0.8`. V2 vẫn hữu ích cho các tình huống cần câu trả lời có cấu trúc; V2 có context precision nhỉnh hơn V1 (0.9417 so với 0.9396).
