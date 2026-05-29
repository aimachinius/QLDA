### **Tên Kỹ Năng: Xác định Công việc phù hợp với Nhân lực dự án (Task-to-Resource Matching)**

#### **1. Mục tiêu (Objective)**
AI Agent có khả năng phân tích từng công việc trong WBS để xác định **công việc này phù hợp với ai** trong 4 thành viên dự án: Chung, Hậu, Lợi, Thái. Kết quả không chỉ liệt kê nhân sự, mà phải gán từng hạng mục WBS cho người phù hợp nhất dựa trên vai trò, kỹ năng và phạm vi phụ trách.

#### **2. Điều kiện đầu vào (Prerequisites)**
*   **WBS của dự án:** Danh sách công việc từ phân tích yêu cầu, thiết kế, phát triển AI, Backend, Frontend, Testing đến Deployment & Handover.
*   **Phạm vi kỹ thuật:** Hệ thống DevSecOps gồm Frontend ReactJS, Backend Spring Boot, AI Layer dùng CodeBERT/BigVul, Execution Layer dùng Docker Sandbox, WebSocket, Terminal, Editor và Dashboard.
*   **Nguồn nhân lực cố định:** Chỉ sử dụng 4 người trong dự án: Chung, Hậu, Lợi, Thái.

#### **3. Hồ sơ nhân lực dự án**

| Người | Vai trò đề xuất | Hạng mục WBS phụ trách chính | Kỹ năng cần có |
|---|---|---|---|
| Chung | Project Manager / Business Analyst / System Analyst | 1.0, 2.1, 2.2, 6.3 | Thu thập và phân tích yêu cầu, viết SRS, Use Case, Sequence Diagram, thiết kế kiến trúc tổng quan, lập kế hoạch dự án, quản lý phạm vi, quản lý rủi ro, viết tài liệu PBL, hiểu cơ bản DevSecOps và CWE. |
| Hậu | AI / Machine Learning Engineer | 1.2, 3.1, 3.2, 3.3, 3.4 | Python, xử lý dữ liệu BigVul, tiền xử lý dữ liệu mã nguồn, hiểu CWE, CodeBERT, học sâu cho phân loại lỗ hổng, multi-task learning, Inverse Frequency Weighting, Uncertainty Weighting, đánh giá F1-score, đóng gói mô hình thành API Service. |
| Lợi | Backend / DevOps / Security Engineer | 2.2, 4.1.1-4.1.5, 5.1, 5.3, 6.1, 6.2 | Java Spring Boot, REST API, Entity/Repository, JWT/Session, thiết kế database, WebSocket, Message Broker, Docker Client, Docker Sandbox, stream dữ liệu terminal, tích hợp AI Server, Docker Compose, bảo mật hệ thống, kiểm thử backend và hiệu năng WebSocket. |
| Thái | Frontend / UI Engineer / Integration Tester | 2.3, 4.2.1-4.2.6, 5.2 | ReactJS, TailwindCSS, Router, thiết kế layout dạng IDE, Dashboard, cây thư mục đệ quy, Context Menu, Monaco Editor, auto-complete, đồng bộ WebSocket, xterm.js, hiển thị cảnh báo AI, highlight dòng lỗi, panel chi tiết CWE, kiểm thử tích hợp Frontend -> Backend -> AI Server. |

#### **4. Quy trình thực hiện (Task-to-Resource Matching Workflow)**

**Bước 1: Đọc và chuẩn hóa từng công việc WBS**
*   Tách WBS thành từng dòng công việc có mã rõ ràng như 1.1, 3.2, 4.1.4, 5.3.
*   Giữ nguyên tên công việc, không gộp các công việc chi tiết nếu WBS đã có mã con.
*   Nếu một công việc thuộc nhiều chuyên môn, vẫn chọn một người phù hợp nhất và ghi người hỗ trợ.

**Bước 2: Phân loại công việc theo năng lực chính**
*   Công việc yêu cầu phân tích, tài liệu, kiến trúc tổng quan, quản lý phạm vi hoặc bàn giao: ưu tiên **Chung**.
*   Công việc liên quan CWE, BigVul, CodeBERT, huấn luyện, đánh giá hoặc đóng gói mô hình AI: ưu tiên **Hậu**.
*   Công việc liên quan Spring Boot, database, JWT/Session, WebSocket backend, Docker, Sandbox, API, bảo mật, deployment: ưu tiên **Lợi**.
*   Công việc liên quan ReactJS, TailwindCSS, Router, UI/UX, Dashboard, Monaco Editor, xterm.js, highlight cảnh báo AI hoặc kiểm thử tích hợp giao diện: ưu tiên **Thái**.

**Bước 3: Xác định công việc này phù hợp với ai**
Với mỗi công việc WBS, AI Agent phải tạo một dòng kết quả theo mẫu bắt buộc:

| Mã WBS | Công việc | Người phù hợp nhất | Người hỗ trợ | Lý do phù hợp |
|---|---|---|---|---|
| 1.1 | Thu thập yêu cầu hệ thống từ bài toán DevSecOps | Chung | Hậu, Lợi, Thái | Chung phụ trách BA/System Analyst; cần lấy yêu cầu từ AI, Backend và Frontend. |
| 1.2 | Xác định danh mục CWE cần phát hiện | Hậu | Chung | Hậu hiểu CWE và bài toán phát hiện lỗ hổng bằng AI; Chung hỗ trợ chuẩn hóa yêu cầu. |
| 4.1.4 | Tích hợp Docker Client, khởi tạo Sandbox độc lập, xử lý I/O Terminal | Lợi | Thái | Lợi phụ trách Backend/DevOps/Security, Docker Client và Sandbox; Thái hỗ trợ phía Terminal UI. |
| 4.2.4 | Nhúng Monaco Editor, xử lý auto-complete và đồng bộ qua WebSocket | Thái | Lợi | Thái phụ trách Frontend/IDE; Lợi hỗ trợ WebSocket phía Backend. |

**Bước 4: Kiểm tra độ bao phủ WBS**
AI Agent phải kiểm tra kết quả đã bao phủ đủ:
*   Phân tích yêu cầu và tài liệu.
*   Thiết kế kiến trúc, database và UI/UX.
*   AI model, dữ liệu BigVul và API AI Service.
*   Backend Spring Boot, WebSocket, Docker Sandbox và bảo mật.
*   Frontend ReactJS, Editor, Terminal và Dashboard.
*   Unit Test, Integration Test, Security/Performance Test.
*   Docker Compose, triển khai thử nghiệm và bàn giao.

**Bước 5: Phân bổ trách nhiệm tổng quan theo RACI rút gọn**

| Hạng mục WBS | Responsible | Accountable | Consulted |
|---|---|---|---|
| 1.0 Phân tích yêu cầu | Chung | Chung | Hậu, Lợi, Thái |
| 2.0 Thiết kế hệ thống | Chung | Chung | Hậu, Lợi, Thái |
| 3.0 Module AI | Hậu | Hậu | Chung, Lợi |
| 4.1 Backend | Lợi | Lợi | Chung, Hậu |
| 4.2 Frontend | Thái | Thái | Chung, Lợi |
| 5.0 Testing | Lợi, Thái | Chung | Hậu |
| 6.0 Deployment & Handover | Lợi, Chung | Chung | Hậu, Thái |

#### **5. Quy tắc lựa chọn nhân sự**
*   Luôn trả lời trọng tâm: **công việc này phù hợp với ai**.
*   Chỉ chọn một người ở cột **Người phù hợp nhất** để tránh mơ hồ trách nhiệm.
*   Dùng cột **Người hỗ trợ** cho công việc có phụ thuộc chéo giữa AI, Backend, Frontend hoặc quản lý.
*   Không tách riêng Tester; kiểm thử được chia cho Lợi và Thái, Chung chịu trách nhiệm điều phối chất lượng tổng thể.
*   Không tách riêng DevOps; DevOps được gộp với Lợi vì WBS có Docker Client, Docker Sandbox, Docker Compose và triển khai server.
*   Không tách riêng UI/UX Designer; UI/UX được gộp với Thái, còn Chung hỗ trợ làm rõ yêu cầu giao diện.
*   Hậu cần phối hợp sớm với Chung để xác định danh mục CWE và phối hợp với Lợi để đóng gói AI Service.

#### **6. Đầu ra của Kỹ năng (Skill Output)**
Đầu ra bắt buộc là bảng xác định từng công việc WBS phù hợp với ai:

| Mã WBS | Công việc | Người phù hợp nhất | Người hỗ trợ | Lý do phù hợp |
|---|---|---|---|---|

Ngoài bảng chính, có thể kèm:
*   Bảng hồ sơ 4 người: Chung, Hậu, Lợi, Thái.
*   Ma trận RACI rút gọn.
*   Ghi chú các công việc cần phối hợp nhiều người.
