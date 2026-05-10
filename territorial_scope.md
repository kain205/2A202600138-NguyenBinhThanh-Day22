# Workshop 2: Đánh giá phạm vi lãnh thổ & Rủi ro pháp lý (Synapsy)

## 1. Câu hỏi 1: User EU?
- **Có 1 user EU không?** Không. Synapsy hiện tại (Pre-seed) tập trung 100% vào thị trường sinh viên Y khoa tại Việt Nam (60-90K sinh viên).
- **Có kế hoạch mở rộng EU 12 tháng tới không?** Không. Kế hoạch mở rộng (Expansion) tiếp theo là 2M+ sinh viên đại học tại Việt Nam, không có kế hoạch sang châu Âu.
- **Kết quả:** EU AI Act áp dụng – **KHÔNG**.

## 2. Câu hỏi 2: Dữ liệu Việt Nam?
- **Liệt kê 5 loại dữ liệu cá nhân đang xử lý:**
  1. Thông tin định danh: Email, Tên, UserID (lưu qua Firebase Auth).
  2. Dữ liệu học tập: File PDF/Slide bài giảng cá nhân upload.
  3. Hành vi học tập: Điểm số Diagnostic Quiz, tỷ lệ thẻ Easy/Hard (SRS data), lộ trình ưu tiên.
  4. Lịch sử giao tiếp: Dữ liệu chat (Sandboxed Chatbot) lưu trong log.
  5. Dữ liệu hệ thống: IP address, device log (để trace lỗi qua Helicone).
- **Có chuyển dữ liệu ra nước ngoài không?** **CÓ**. Hệ thống đẩy trực tiếp file PDF và text prompt sang các server của OpenAI (GPT-4o), Anthropic (Claude), Google (Gemini) và lưu trữ file tạm trên Cloudflare R2 / Firebase (server nước ngoài). 
- **Kết quả:** Nghị định 13/2023/NĐ-CP (PDPD - Bảo vệ Dữ liệu Cá nhân VN) áp dụng – **CÓ**. Cần lập Hồ sơ đánh giá tác động chuyển dữ liệu cá nhân ra nước ngoài.

## 3. Câu hỏi 3: Tầng rủi ro Luật AI VN?
- **Tầng rủi ro:** **CAO**.
- **1 câu lập luận tại sao:** Dự án Synapsy chạm trực tiếp vào cả hai lĩnh vực nhạy cảm là **Y tế** và **Giáo dục**; dù chỉ là công cụ ôn thi, nhưng nếu AI gặp ảo giác (hallucination) tạo ra kiến thức y khoa lâm sàng sai lệch, nó có thể ảnh hưởng nghiêm trọng đến tư duy điều trị của bác sĩ tương lai.

## 4. Lịch: 4 mốc deadline hành động (Notion)
- **Deadline 1 (Càng sớm càng tốt - trước Launch):** Code và chèn Checkbox "Đồng ý với Điều khoản & Chính sách bảo mật" (Clickwrap liability) ngay bước Onboarding / Upload file.
- **Deadline 2 (Trong tuần 1):** Bổ sung dòng Disclaimer cảnh báo y tế cứng trên UI: "Nội dung do AI tạo từ tài liệu học tập — KHÔNG sử dụng làm tư vấn lâm sàng".
- **Deadline 3 (Tuần 2):** Soạn thảo và công bố Privacy Policy (Chính sách bảo mật) chuẩn hóa theo NĐ 13 (nêu rõ việc gửi file qua LLM API).
- **Deadline 4 (Tuần 3 - Sau khi có PMF signal):** Hoàn thành form Hồ sơ Đánh giá tác động xử lý dữ liệu cá nhân (nội bộ) đề phòng thanh tra.
