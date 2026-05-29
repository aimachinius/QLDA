### **Tên Kỹ Năng: Ước lượng Thời gian Công việc (Task Duration Estimation)**

#### **1. Mục tiêu (Objective)**
AI Agent có khả năng dự đoán thời gian cần thiết để hoàn thành các công việc cụ thể hoặc toàn bộ dự án, đồng thời giảm thiểu sai số qua từng giai đoạn của chu trình dự án.

#### **2. Điều kiện đầu vào (Prerequisites)**
Để thực hiện ước lượng, AI Agent yêu cầu các thông tin sau:
*   **Cấu trúc phân rã công việc (WBS):** Phải có một WBS chi tiết và rõ ràng.
*   **Mức độ phân rã:** Các công việc nhỏ nên được chia xuống mức không quá **8 giờ** hoặc tối đa là **một tuần** để đảm bảo độ chính xác.
*   **Thông tin nguồn lực:** Trình độ chuyên gia, kinh nghiệm thực tế và các khiếm khuyết của nguồn lực (nếu có).

#### **3. Quy trình thực hiện (Estimation Workflow)**

**Bước 1: Phân tích và Hiểu công việc**
*   Kiểm tra tính chi tiết của WBS. Nếu công việc còn mơ hồ, yêu cầu làm rõ mục đích, mục tiêu và kết quả.
*   Phân loại công việc dựa trên độ phức tạp (Thấp, Trung bình, Cao).

**Bước 2: Lựa chọn kỹ thuật ước lượng (Logic xử lý)**
AI Agent sẽ áp dụng một hoặc kết hợp các kỹ thuật sau tùy theo dữ liệu có sẵn:
*   **Kỹ thuật PERT (Dành cho công việc có độ rủi ro cao):**
    *   Công thức: $EST = (MO + 4(ML) + MP) / 6$.
    *   Trong đó: $MO$ là thời gian lạc quan nhất, $ML$ là khả dĩ nhất, và $MP$ là bi quan nhất.
*   **Kỹ thuật Điểm chức năng (Dành cho lập trình):**
    *   Công thức: $D = C \times (G + J)$.
    *   Trong đó: $D$ là độ dài thời gian, $C$ là nhân tố độ phức tạp (dựa trên ngôn ngữ và chức năng), $G$ là kinh nghiệm chung và $J$ là tri thức về công việc cụ thể.
*   **Kỹ thuật Năng suất toàn cục (GEF) (Dành cho việc điều chỉnh theo thực tế):**
    *   Tính $GEF = 100\% - \text{tổng \% khiếm khuyết}$ (như tinh thần thấp, kỹ năng chưa cao, trang thiết bị kém).
    *   Ước lượng cuối cùng = $\text{Thời gian lý tưởng} / GEF$.

**Bước 3: Điều chỉnh theo tâm lý và rủi ro**
*   **Bù đắp sai số lạc quan:** Các lập trình viên thường rất lạc quan (ước lượng thấp hơn thực tế). AI cần cộng thêm ít nhất **10%** thời gian cho mỗi thành viên bổ sung vào nhóm để tính đến sự hao phí do tương tác.
*   **Đưa ra khoảng giá trị:** Thay vì một con số chính xác (ví dụ: 12 tháng), AI nên cung cấp một khoảng ước lượng (ví dụ: 10-14 tháng) để tăng độ tin cậy.

**Bước 4: Kiểm chứng và Phê duyệt**
*   So sánh với lịch sử các dự án tương tự.
*   Tổ chức họp nhóm để lấy ý kiến tập thể (nguyên tắc "ba cây chụm lại nên hòn núi cao").

#### **4. Quy tắc cải thiện độ chính xác (Iterative Refinement)**
AI Agent phải tuân thủ tính chất lặp của ước lượng theo các mốc thời gian (Milestones):
*   **Giai đoạn xác định dự án:** Sai số chấp nhận được là 50% - 100%.
*   **Giai đoạn phân tích:** Điều chỉnh sai số xuống 25% - 50%.
*   **Sau thiết kế mức trung gian:** Sai số chỉ được còn khoảng 10% (Lớp A).

#### **5. Xử lý các tình huống đặc biệt (Edge Cases)**
*   **Ước lượng quá thấp:** Yêu cầu người thực hiện cam kết bằng văn bản hoặc tăng thêm một tỷ lệ % dự phòng.
*   **Ước lượng quá cao:** Đề xuất thu hẹp phạm vi dự án hoặc phát triển các phiên bản nhỏ hơn.
*   **Rút ngắn thời gian:** Nếu bị yêu cầu rút ngắn, AI chỉ tập trung rút ngắn các nhiệm vụ nằm trên **đường găng (Critical Path)**.

#### **6. Đầu ra của Kỹ năng (Skill Output)**
*   Bảng chi tiết ước lượng (bao gồm: Tên nhiệm vụ, Độ phức tạp, Nguồn lực, Thời gian ước lượng, Chú thích).
*   Biên bản thống nhất giữa các bên liên quan.
*   Sơ đồ Gantt hoặc PERT mô phỏng lịch trình.