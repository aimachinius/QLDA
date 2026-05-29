### **Tên Kỹ Năng: Xác định Phụ thuộc Công việc (Task Dependency Identification)**

#### **1. Mục tiêu (Objective)**
AI Agent có khả năng xác định thứ tự thực hiện các hoạt động, thiết lập mối quan hệ giữa các nhiệm vụ tiền nhiệm (Predecessor) và kế nhiệm (Successor) để xây dựng một lịch trình dự án khả thi.

#### **2. Điều kiện đầu vào (Prerequisites)**
*   **Cấu trúc phân rã công việc (WBS):** Danh sách các công việc đã được chia nhỏ đến mức thấp nhất (theo quy tắc 80 giờ hoặc nhiệm vụ có thể giao cho một nhóm/cá nhân).
*   **Danh sách sản phẩm (PBS):** Để hiểu rõ mối liên hệ giữa các thành phần cấu thành hệ thống.

#### **3. Quy trình thực hiện (Dependency Analysis Workflow)**

**Bước 1: Phân tích trình tự logic (Logical Sequencing)**
*   AI Agent phân tích dựa trên câu hỏi: "Công việc nào phải làm trước công việc nào?".
*   Xác định các nhiệm vụ **không có công việc trước** để đặt làm điểm khởi đầu của sơ đồ.
*   Xác định các nhiệm vụ **không có công việc sau** để làm điểm kết thúc của dự án.

**Bước 2: Phân loại loại hình phụ thuộc (PDM Relationship Types)**
AI Agent sẽ gán một trong bốn loại quan hệ sau cho mỗi cặp công việc:
*   **Kết thúc - Bắt đầu (FS):** Công việc B chỉ có thể bắt đầu khi công việc A đã kết thúc (Loại phổ biến nhất).
*   **Bắt đầu - Bắt đầu (SS):** Công việc B bắt đầu đồng thời khi công việc A bắt đầu.
*   **Kết thúc - Kết thúc (FF):** Công việc B kết thúc khi công việc A kết thúc.
*   **Bắt đầu - Kết thúc (SF):** Công việc B kết thúc khi công việc A bắt đầu (Hiếm khi sử dụng).

**Bước 3: Thiết lập thời gian chồng lấn và trễ (Lead & Lag Time)**
*   **Lead Time:** AI Agent lập lịch để hai công việc thực hiện chồng nhau, giúp nhiệm vụ kế nhiệm bắt đầu trước khi nhiệm vụ tiền nhiệm kết thúc.
*   **Lag Time:** AI Agent đưa vào khoảng thời gian trì hoãn sự khởi đầu của nhiệm vụ kế nhiệm sau khi nhiệm vụ tiền nhiệm đã xong.

**Bước 4: Sử dụng "Công việc ảo" (Dummy Tasks) - Nếu dùng sơ đồ ADM**
*   Khi sử dụng sơ đồ mạng mũi tên (ADM), AI Agent cần tạo ra các **"Công việc ảo"** không đại diện cho công việc thực tế, chỉ dùng để biểu diễn sự phụ thuộc logic giữa các nhánh công việc khác nhau.

#### **4. Công cụ và Phương pháp mô hình hóa**
AI Agent cần sử dụng các phương pháp sau để trực quan hóa phụ thuộc:
*   **Sơ đồ mạng PDM (Precedence Diagramming Method):** Sử dụng các nút (hình chữ nhật) để mô tả công việc và mũi tên để chỉ ra loại quan hệ.
*   **Sơ đồ mạng ADM (Arrow Diagramming Method):** Sử dụng mũi tên đại diện cho công việc đi từ mốc sự kiện này đến mốc sự kiện khác.
*   **Bảng hoạt động (Activity Table):** Liệt kê ID công việc, tên công việc, thời gian và cột Predecessor (công việc trước đó).

#### **5. Kiểm soát và Tối ưu hóa**
*   **Xác định Đường găng (Critical Path):** AI Agent phải tìm ra chuỗi các nhiệm vụ có phụ thuộc lẫn nhau tạo thành đường dài nhất trong sơ đồ. Bất kỳ sự chậm trễ nào trên các mắt xích phụ thuộc này sẽ kéo dài toàn bộ dự án.
*   **Loại bỏ chu trình (Loop):** AI Agent phải kiểm tra để đảm bảo sơ đồ mạng **không được có chu trình lặp lại** (ví dụ: A phụ thuộc B, B lại phụ thuộc A).
*   **Thả nổi lịch (Slack Time):** Xác định các công việc ngoài đường găng có thể trì hoãn một khoảng thời gian nhất định mà không ảnh hưởng đến tiến độ chung.

#### **6. Đầu ra của Kỹ năng (Skill Output)**
*   **Bảng liệt kê phụ thuộc:** Chi tiết nhiệm vụ tiền nhiệm và loại quan hệ (FS, SS, FF, SF).
*   **Sơ đồ mạng dự án (Network Diagram):** Minh họa logic luồng công việc từ lúc bắt đầu đến khi kết thúc.
*   **Sơ đồ Gantt:** Thể hiện trực quan các thanh thời gian và đường nối phụ thuộc giữa chúng.