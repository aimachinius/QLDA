## Work breakdown Struct


1.0 Phân tích yêu cầu
1.1 Thu thập yêu cầu hệ thống từ bài toán DevSecOps.
1.2 Xác định danh mục các loại lỗ hổng CWE cần phát hiện theo tiêu chuẩn.
1.3 Lập tài liệu đặc tả yêu cầu (SRS) và các biểu đồ Use Case, Sequence.
2.0 Thiết kế hệ thống
2.1 Thiết kế kiến trúc tổng quan (Frontend, Backend, AI Layer, Execution Layer).
2.2 Thiết kế cơ sở dữ liệu (ERD) và cấu trúc lưu trữ cho Project, User, File.
2.3 Thiết kế giao diện (UI/UX) cho hệ thống Editor, Terminal và Dashboard.
3.0 Phát triển Module Trí tuệ nhân tạo (AI)
3.1 Xử lý dữ liệu: Thu thập, làm sạch, tiền xử lý tập dữ liệu BigVul và lọc theo ngưỡng.
3.2 Xây dựng mô hình: Cấu hình CodeBERT, thiết kế kiến trúc đầu ra đa nhiệm.
3.3 Huấn luyện mô hình: Áp dụng Inverse Frequency Weighting và Uncertainty Weighting, tiến hành huấn luyện.
3.4 Đánh giá & Đóng gói: Đánh giá F1-score, kiểm thử dự đoán và đóng gói mô hình thành API Service.
4.0 Phát triển hệ thống phần mềm
4.1 Phát triển Backend (Spring Boot)
4.1.1 Khởi tạo dự án, cấu hình DB, Entity/Repository và thiết lập bảo mật JWT/Session.
4.1.2 Xây dựng API quản lý dự án (tạo, xóa) và logic đọc/ghi cây thư mục.
4.1.3 Cấu hình Message Broker và thiết lập luồng kết nối WebSocket đồng bộ mã nguồn.
4.1.4 Tích hợp Docker Client, khởi tạo Sandbox độc lập, xử lý luồng I/O Terminal.
4.1.5 Thiết kế hàng đợi gọi API sang AI Server và stream kết quả về Frontend.
4.2 Phát triển Frontend (ReactJS)
4.2.1 Khởi tạo dự án, cấu hình TailwindCSS, Router và dựng Layout chuẩn IDE.
4.2.2 Xây dựng Dashboard quản lý dự án và form tạo mới.
4.2.3 Render cây thư mục đệ quy, xử lý Context Menu (tạo/xóa tệp tin).
4.2.4 Nhúng Monaco Editor, xử lý auto-complete và đồng bộ nội dung qua WebSocket.
4.2.5 Tích hợp xterm.js, thiết lập kênh WebSocket riêng cho Terminal.
4.2.6 Xử lý cảnh báo AI: Highlight dòng lỗi và hiển thị panel chi tiết CWE.
5.0 Kiểm thử hệ thống (Testing)
5.1 Kiểm thử đơn vị (Unit Test): Test các logic độc lập ở Backend và Docker Service.
5.2 Kiểm thử tích hợp (Integration Test): Test luồng xuyên suốt từ Frontend -> AI Server và chức năng quét lỗ hổng.
5.3 Kiểm thử bảo mật & hiệu năng: Đo độ trễ phản hồi WebSocket và test tính cách ly (an toàn) của Docker Sandbox.
6.0 Triển khai và Tổng kết (Deployment & Handover)
6.1 Kết nối hoàn chỉnh các module và đóng gói ứng dụng (Docker Compose).
6.2 Triển khai hệ thống lên môi trường Server chạy thử nghiệm.
6.3 Hoàn thiện tài liệu kiến trúc, viết báo cáo tổng kết đồ án (PBL).



