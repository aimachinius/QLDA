# Sơ đồ AON và đường găng dự án

Quy ước tính toán:
* Đơn vị thời gian: ngày làm việc.
* ES: thời gian bắt đầu sớm.
* EF: thời gian kết thúc sớm.
* LS: thời gian bắt đầu muộn.
* LF: thời gian kết thúc muộn.
* Slack = LS - ES. Công việc có Slack = 0 thuộc đường găng.

## Bảng thông tin nút AON

| Ký hiệu | Công việc | Duration | ES | EF | LS | LF | Slack | Trạng thái |
|---|---|---:|---:|---:|---:|---:|---:|---|
| A | Thu thập yêu cầu hệ thống từ bài toán DevSecOps | 4 | 0 | 4 | 0 | 4 | 0 | Găng |
| B | Xác định danh mục CWE cần phát hiện | 3 | 4 | 7 | 4 | 7 | 0 | Găng |
| C | Lập tài liệu SRS, Use Case, Sequence | 5 | 7 | 12 | 7 | 12 | 0 | Găng |
| D | Thiết kế kiến trúc tổng quan | 5 | 12 | 17 | 12 | 17 | 0 | Găng |
| E | Thiết kế database ERD và cấu trúc lưu trữ | 4 | 17 | 21 | 17 | 21 | 0 | Găng |
| F | Thiết kế UI/UX cho Editor, Terminal, Dashboard | 4 | 17 | 21 | 26 | 30 | 9 | Không găng |
| G | Tiền xử lý dữ liệu BigVul | 8 | 7 | 15 | 12 | 20 | 5 | Không găng |
| H | Cấu hình CodeBERT và đầu ra đa nhiệm | 9 | 15 | 24 | 20 | 29 | 5 | Không găng |
| I | Huấn luyện mô hình AI | 13 | 24 | 37 | 29 | 42 | 5 | Không găng |
| J | Đánh giá F1-score và đóng gói AI API | 6 | 37 | 43 | 42 | 48 | 5 | Không găng |
| K | Khởi tạo Backend, DB, Entity, JWT/Session | 6 | 21 | 27 | 21 | 27 | 0 | Găng |
| L | Xây dựng API quản lý dự án và cây thư mục | 8 | 27 | 35 | 27 | 35 | 0 | Găng |
| M | Message Broker và WebSocket đồng bộ mã nguồn | 8 | 35 | 43 | 38 | 46 | 3 | Không găng |
| N | Docker Client, Sandbox và Terminal I/O | 9 | 27 | 36 | 47 | 56 | 20 | Không găng |
| O | Hàng đợi gọi AI Server và stream kết quả | 6 | 43 | 49 | 48 | 54 | 5 | Không găng |
| P | Khởi tạo Frontend, TailwindCSS, Router, layout IDE | 5 | 21 | 26 | 30 | 35 | 9 | Không găng |
| Q | Dashboard quản lý dự án và form tạo mới | 5 | 35 | 40 | 35 | 40 | 0 | Găng |
| R | Cây thư mục đệ quy và Context Menu | 6 | 40 | 46 | 40 | 46 | 0 | Găng |
| S | Monaco Editor, auto-complete, đồng bộ WebSocket | 8 | 46 | 54 | 46 | 54 | 0 | Găng |
| T | xterm.js và WebSocket riêng cho Terminal | 6 | 36 | 42 | 87 | 93 | 51 | Không găng |
| U | Cảnh báo AI, highlight lỗi, panel CWE | 7 | 54 | 61 | 54 | 61 | 0 | Găng |
| V | Unit Test Backend và Docker Service | 5 | 36 | 41 | 56 | 61 | 20 | Không găng |
| W | Integration Test Frontend -> AI Server | 7 | 61 | 68 | 61 | 68 | 0 | Găng |
| X | Security & Performance Test WebSocket và Docker Sandbox | 6 | 68 | 74 | 68 | 74 | 0 | Găng |
| Y | Kết nối module và đóng gói Docker Compose | 6 | 74 | 80 | 74 | 80 | 0 | Găng |
| Z | Triển khai hệ thống lên server chạy thử | 5 | 80 | 85 | 80 | 85 | 0 | Găng |
| AA | Hoàn thiện tài liệu kiến trúc và báo cáo PBL | 8 | 85 | 93 | 85 | 93 | 0 | Găng |

## Sơ đồ AON

```mermaid
flowchart LR
    A["A<br/>Thu thập yêu cầu<br/>Dur=4<br/>ES=0 EF=4<br/>LS=0 LF=4"]
    B["B<br/>Xác định CWE<br/>Dur=3<br/>ES=4 EF=7<br/>LS=4 LF=7"]
    C["C<br/>SRS, Use Case, Sequence<br/>Dur=5<br/>ES=7 EF=12<br/>LS=7 LF=12"]
    D["D<br/>Thiết kế kiến trúc<br/>Dur=5<br/>ES=12 EF=17<br/>LS=12 LF=17"]
    E["E<br/>Thiết kế database<br/>Dur=4<br/>ES=17 EF=21<br/>LS=17 LF=21"]
    F["F<br/>Thiết kế UI/UX<br/>Dur=4<br/>ES=17 EF=21<br/>LS=26 LF=30"]
    G["G<br/>Tiền xử lý BigVul<br/>Dur=8<br/>ES=7 EF=15<br/>LS=12 LF=20"]
    H["H<br/>Cấu hình CodeBERT<br/>Dur=9<br/>ES=15 EF=24<br/>LS=20 LF=29"]
    I["I<br/>Huấn luyện AI<br/>Dur=13<br/>ES=24 EF=37<br/>LS=29 LF=42"]
    J["J<br/>Đánh giá và AI API<br/>Dur=6<br/>ES=37 EF=43<br/>LS=42 LF=48"]
    K["K<br/>Khởi tạo Backend<br/>Dur=6<br/>ES=21 EF=27<br/>LS=21 LF=27"]
    L["L<br/>API dự án/cây thư mục<br/>Dur=8<br/>ES=27 EF=35<br/>LS=27 LF=35"]
    M["M<br/>Broker/WebSocket<br/>Dur=8<br/>ES=35 EF=43<br/>LS=38 LF=46"]
    N["N<br/>Docker Sandbox<br/>Dur=9<br/>ES=27 EF=36<br/>LS=47 LF=56"]
    O["O<br/>Queue AI/stream<br/>Dur=6<br/>ES=43 EF=49<br/>LS=48 LF=54"]
    P["P<br/>Khởi tạo Frontend<br/>Dur=5<br/>ES=21 EF=26<br/>LS=30 LF=35"]
    Q["Q<br/>Dashboard<br/>Dur=5<br/>ES=35 EF=40<br/>LS=35 LF=40"]
    R["R<br/>Cây thư mục UI<br/>Dur=6<br/>ES=40 EF=46<br/>LS=40 LF=46"]
    S["S<br/>Monaco/WebSocket<br/>Dur=8<br/>ES=46 EF=54<br/>LS=46 LF=54"]
    T["T<br/>xterm.js Terminal<br/>Dur=6<br/>ES=36 EF=42<br/>LS=87 LF=93"]
    U["U<br/>Cảnh báo AI/CWE<br/>Dur=7<br/>ES=54 EF=61<br/>LS=54 LF=61"]
    V["V<br/>Unit Test<br/>Dur=5<br/>ES=36 EF=41<br/>LS=56 LF=61"]
    W["W<br/>Integration Test<br/>Dur=7<br/>ES=61 EF=68<br/>LS=61 LF=68"]
    X["X<br/>Security/Performance Test<br/>Dur=6<br/>ES=68 EF=74<br/>LS=68 LF=74"]
    Y["Y<br/>Docker Compose<br/>Dur=6<br/>ES=74 EF=80<br/>LS=74 LF=80"]
    Z["Z<br/>Triển khai server<br/>Dur=5<br/>ES=80 EF=85<br/>LS=80 LF=85"]
    AA["AA<br/>Tài liệu và báo cáo<br/>Dur=8<br/>ES=85 EF=93<br/>LS=85 LF=93"]

    A --> B
    A --> C
    B --> C
    B --> G
    C --> D
    D --> E
    D --> F
    E --> K
    F --> P
    G --> H
    H --> I
    I --> J
    J --> O
    K --> L
    K --> N
    L --> M
    L --> Q
    L --> R
    L --> V
    M --> O
    M --> S
    N --> T
    N --> V
    O --> U
    P --> Q
    P --> T
    Q --> R
    R --> S
    S --> U
    U --> W
    V --> W
    W --> X
    W --> AA
    X --> Y
    Y --> Z
    Z --> AA

    classDef critical fill:#ffd6d6,stroke:#d92d20,stroke-width:2px,color:#111;
    classDef normal fill:#eef4ff,stroke:#2f80ed,stroke-width:1px,color:#111;
    class A,B,C,D,E,K,L,Q,R,S,U,W,X,Y,Z,AA critical;
    class F,G,H,I,J,M,N,O,P,T,V normal;
```

## Đường găng

Đường găng của dự án:

```text
A -> B -> C -> D -> E -> K -> L -> Q -> R -> S -> U -> W -> X -> Y -> Z -> AA
```

Tổng thời gian đường găng:

```text
4 + 3 + 5 + 5 + 4 + 6 + 8 + 5 + 6 + 8 + 7 + 7 + 6 + 6 + 5 + 8 = 93 ngày làm việc
```

Kết luận: thời gian hoàn thành sớm nhất của dự án là **93 ngày làm việc**, tương đương khoảng **18.6 tuần**, nằm trong yêu cầu **5 tháng** nếu các công việc song song được thực hiện đúng theo lịch.
