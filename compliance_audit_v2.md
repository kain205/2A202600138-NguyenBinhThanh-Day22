# Workshop 4: Compliance Audit (Synapsy)

## VI PHẠM 1: Cảnh báo y tế "thay thế bác sĩ"
- **Luật áp dụng:** Luật Quảng cáo / Nghị định 15/2018 (sản phẩm y tế), Điều 198 BLHS.
- **Điều khoản:** Có rủi ro hiểu nhầm thành công cụ tư vấn lâm sàng.
- **Bằng chứng trong sản phẩm:** "Chatbot thông minh như bác sĩ, tư vấn và chẩn đoán mọi ca lâm sàng." (từ `marketing_claims_audit.md`).
- **Pattern khớp với:** Vụ kẹo Kera (KOL quảng cáo sai sự thật).
- **Hành động sửa:** 1. Gỡ ngay câu marketing "thông minh như bác sĩ" và thay bằng "giải thích khái niệm giới hạn trong giáo trình".
  2. Thêm disclaimer in đậm trên giao diện chat: "Nội dung do AI tạo từ tài liệu học tập — KHÔNG sử dụng làm tư vấn lâm sàng".
  3. Cập nhật Terms of Service (Clickwrap liability) yêu cầu user xác nhận không dùng để điều trị.
- **Deadline:** Càng sớm càng tốt (Trước Launch).

## VI PHẠM 2: Gửi file PII (Dữ liệu cá nhân) sang API nước ngoài
- **Luật áp dụng:** Nghị định 13/2023/NĐ-CP (Bảo vệ Dữ liệu Cá nhân VN).
- **Điều khoản:** Điều 8 & Chương V (Chuyển dữ liệu ra nước ngoài).
- **Bằng chứng trong sản phẩm:** "Hệ thống đẩy trực tiếp file PDF và text prompt sang các server của OpenAI (GPT-4o), Anthropic (Claude), Google (Gemini)..." (từ `territorial_scope.md`).
- **Pattern khớp với:** Vụ rò rỉ CIC 9/2025.
- **Hành động sửa:** 1. Thêm Checkbox đồng ý điều khoản ngay bước Onboarding, ghi rõ file sẽ được gửi cho bên thứ 3 (OpenAI/Anthropic) xử lý.
  2. Chuyển sang dùng các gói API/Enterprise (như quy định trong `rules_rails_ritual.md`) để có cam kết không train model (Zero Data Retention).
  3. Chuẩn bị Hồ sơ Đánh giá tác động chuyển dữ liệu ra nước ngoài.
- **Deadline:** Tuần 1 (Checkbox & API setting) / Tuần 3 (Hồ sơ).

## VI PHẠM 3: Rò rỉ API Keys / Lộ Source Code
- **Luật áp dụng:** Luật An toàn thông tin mạng / Bảo mật nội bộ.
- **Bằng chứng trong sản phẩm:** Rủi ro "Rò rỉ dữ liệu nhạy cảm... do thành viên team sử dụng các công cụ LLM public không an toàn" (từ `rules_rails_ritual.md` & RISK-09 trong `risk_register.md`).
- **Pattern khớp với:** Lỗi vận hành nội bộ (Internal AI Safety).
- **Hành động sửa:** 1. Bắt buộc nhân viên dùng API/OpenAI Enterprise hoặc công cụ IDE có bản quyền (Cursor/Copilot).
  2. Cài đặt `git-secrets` OSS hoặc pre-commit hooks chặn push API key.
  3. Duy trì "Friday 30' Risk Review".
- **Deadline:** Trong tuần này (Trước khi có beta users).

## VI PHẠM 4: Phân loại rủi ro AI (Giáo dục & Y tế)
- **Luật áp dụng:** Luật AI Việt Nam 134/2025/QH15.
- **Điều khoản:** Điều 9 (Phân loại AI rủi ro cao).
- **Bằng chứng trong sản phẩm:** "Dự án Synapsy chạm trực tiếp vào cả hai lĩnh vực nhạy cảm là Y tế và Giáo dục... có thể ảnh hưởng nghiêm trọng đến tư duy điều trị" (từ `territorial_scope.md`).
- **Pattern khớp với:** Quy định phân loại AI có rủi ro cao.
- **Hành động sửa:** 1. Chuẩn bị sẵn sàng hồ sơ đánh giá giới hạn an toàn AI (AI Guardrails).
  2. Implement tính năng F4-lite (Source Traceability - Chia đôi màn hình xem nguồn) để ép buộc kiểm chứng.
  3. Thiết lập Incident Playbook để có kịch bản xử lý ngay khi AI phát ngôn sai.
- **Deadline:** Hoàn thiện F4-lite trước PMF confirm.

## VI PHẠM 5: Quảng cáo sai "0% Hallucination"
- **Luật áp dụng:** Luật Quảng cáo / Điều 198 BLHS.
- **Điều khoản:** Thổi phồng tính năng, lừa dối người tiêu dùng.
- **Bằng chứng trong sản phẩm:** "Tự động sinh flashcard mà AI không bao giờ bịa đặt (0% Hallucination)." (từ `marketing_claims_audit.md`).
- **Pattern khớp với:** Vụ kẹo Kera (Quảng cáo sai công dụng).
- **Hành động sửa:** 1. Đổi claim thành "Tự động sinh flashcard đi kèm tính năng 'Xem Nguồn' chia đôi màn hình, cho phép bạn tự kiểm chứng".
  2. Xóa các cam kết tuyệt đối (100%, 0%, chính xác tuyệt đối) khỏi mọi tài liệu marketing/website.
  3. Truyền thông giáo dục user rằng AI có sai sót và luôn cần đối chiếu nguồn.
- **Deadline:** Ngay lập tức.
