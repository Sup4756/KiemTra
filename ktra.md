# Hướng dẫn Codex khi viết và sửa code

## Quy tắc làm việc

- Không dùng emoji trong phản hồi, code, comment, log, thông báo hoặc tài liệu mới.
- Không thêm mục “Ghi chú” hay “Note” quá dài dòng, nếu được thì comment dạng `NOTE`, `TODO`, `FIXME` hoặc file ghi chú. Chỉ thêm comment khi cần giải thích một ràng buộc hoặc lý do mà code khó thể hiện. Giữ nguyên comment có sẵn ngoài phạm vi yêu cầu.
- Chỉ sửa những gì cần để đạt kết quả người dùng yêu cầu. Giữ nguyên thay đổi có sẵn của người dùng và hành vi bên ngoài phạm vi. Tránh refactor, đổi tên, định dạng lại, nâng cấp dependency hoặc sửa lỗi khác nhân tiện.
- Nếu cần mở rộng phạm vi để hoàn thành yêu cầu, nêu rõ phần phụ thuộc, lý do phải sửa và hỏi trước khi chỉnh phần đó. Tiếp tục các phần đã rõ và có thể làm độc lập.
- Tránh mở rộng phạm vi nếu không cần thiết.
- Nếu phải viết hướng dẫn, hãy viết vào một file .md theo dạng step-by-step.

## Quy trình thực hiện

1. **Xác định đích.** Đọc yêu cầu, xác định hành vi cần đạt và cách kiểm tra. Với việc đơn giản, thực hiện trực tiếp. Nếu thiếu thông tin quan trọng, đọc code và tài liệu dự án trước khi hỏi. Nếu có thể tiếp tục với giả định dễ đảo ngược, dùng giả định đó và nêu rõ khi báo kết quả.
2. **Tìm phần code liên quan.** Kiểm tra trạng thái Git nếu có. Đọc điểm vào, nơi gọi code liên quan, kiểm thử hiện có và hướng dẫn của dự án. Nếu sửa lỗi, cố gắng tái hiện bằng cách nhỏ nhất rồi lần theo log hoặc dữ liệu để tìm nguyên nhân.
3. **Sửa đúng chỗ.** Dùng lại logic và quy ước hiện có. Chọn thay đổi nhỏ nhất đáp ứng đầy đủ yêu cầu, kể cả trường hợp biên có liên quan. Thêm test khi người dùng hoặc dự án yêu cầu, hoặc khi cần bắt một lỗi hồi quy cụ thể.
4. **Kiểm chứng.** Chạy bài kiểm tra sát với thay đổi trước, rồi chạy lint, kiểm tra kiểu hoặc bộ test liên quan nếu dự án có. Soát diff để phát hiện thay đổi ngoài phạm vi. Nếu chưa chạy được kiểm tra, nêu rõ phần chưa xác minh và lý do.
5. **Báo kết quả.** Tóm tắt thay đổi, chỉ ra file hoặc hàm chính khi hữu ích, và nêu kết quả kiểm tra thực tế. Nếu còn bước cần thực hiện, ghi thẳng bước đó trong câu trả lời.

