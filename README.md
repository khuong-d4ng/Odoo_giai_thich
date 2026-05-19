# CHƯƠNG 2. CÔNG NGHỆ SỬ DỤNG

## 2.1. Công nghệ xây dựng hệ thống nền tảng (Backend & Frontend)

Để xây dựng một hệ thống lập kế hoạch và phân công giảng dạy toàn diện, ổn định và có khả năng mở rộng tốt, việc lựa chọn kiến trúc và các công nghệ nền tảng đóng vai trò quyết định. Hệ thống được thiết kế theo mô hình kiến trúc Web Application hai lớp (Client-Server) hiện đại với sự phân tách rõ ràng về mặt trách nhiệm (Separation of Concerns). Phía máy chủ (Backend) chịu trách nhiệm quản trị cơ sở dữ liệu, thực thi các thuật toán tối ưu tổ hợp phức tạp và cung cấp các dịch vụ Web API chuẩn hóa. Phía máy trạm (Frontend) tập trung vào việc mang lại trải nghiệm người dùng tương tác thời gian thực, mượt mà và trực quan hóa các dữ liệu lịch biểu. Dưới đây là phân tích chi tiết về các công nghệ cốt lõi được lựa chọn ứng dụng trong hệ thống phân công giảng dạy cho Khoa Công nghệ Thông tin – Trường Đại học Đại Nam.

---

### 2.1.1. Tổng quan về ngôn ngữ Python

Python là một ngôn ngữ lập trình bậc cao, thông dịch, hướng đối tượng và đa mục đích, được phát triển bởi Guido van Rossum và ra mắt lần đầu vào năm 1991. Trải qua hơn ba thập kỷ phát triển, Python đã trở thành một trong những ngôn ngữ lập trình phổ biến nhất thế giới và là lựa chọn hàng đầu cho các ứng dụng từ phát triển web, khoa học dữ liệu cho đến trí tuệ nhân tạo. Trong dự án xây dựng hệ thống lập kế hoạch và giảng dạy này, Python được tin tưởng lựa chọn làm ngôn ngữ chủ đạo phía máy chủ nhờ những ưu điểm vượt trội sau:

*   **Cú pháp sáng sủa, dễ đọc và dễ bảo trì:** Triết lý thiết kế của Python nhấn mạnh vào độ thẩm mỹ và tính dễ đọc của mã nguồn (thể hiện qua tài liệu nổi tiếng *The Zen of Python*). Việc sử dụng khoảng trắng thụt lề (indentation) để phân cấp khối mã giúp mã nguồn Python cực kỳ gọn gàng, giảm thiểu mã mẫu dư thừa (boilerplate code). Điều này giúp rút ngắn chu kỳ phát triển phần mềm và tạo điều kiện thuận lợi cho việc bảo trì, chuyển giao mã nguồn.
*   **Hệ sinh thái thư viện dữ liệu khổng lồ:** Python sở hữu kho tàng thư viện bên thứ ba cực kỳ phong phú và mạnh mẽ thông qua trình quản lý gói PyPI. Đối với bài toán lập kế hoạch giảng dạy, khả năng tích hợp dễ dàng với các thư viện xử lý bảng biểu chuyên sâu (như Pandas) và các framework tối ưu hóa toán học giúp hệ thống xử lý trơn tru hàng ngàn dòng dữ liệu nghiệp vụ.
*   **Hỗ trợ đa phương thức lập trình:** Python cho phép lập trình viên linh hoạt áp dụng các phong cách lập trình hướng đối tượng (OOP), lập trình thủ tục (Procedural) hoặc lập trình hàm (Functional) tùy thuộc vào tính chất của từng module chức năng, giúp tối ưu hóa cấu trúc mã nguồn ở mức tối đa.

---

### 2.1.2. Tổng quan về TypeScript

Trong những ngày đầu của sự phát triển web, JavaScript là ngôn ngữ duy nhất chạy trên trình duyệt để tương tác giao diện. Tuy nhiên, JavaScript là một ngôn ngữ định kiểu động (dynamically typed) và yếu (weakly typed), dẫn đến việc các lỗi về kiểu dữ liệu (Type Errors) chỉ được phát hiện khi ứng dụng thực sự chạy trên môi trường thực tế (Runtime). Đối với một giao diện Workspace xếp lịch phức tạp có hàng chục thuộc tính dữ liệu đan xen, việc sử dụng JavaScript thuần túy tiềm ẩn rủi ro rất lớn về độ ổn định. Để khắc phục triệt để hạn chế này, hệ thống đã ứng dụng **TypeScript** làm ngôn ngữ lập trình chính cho toàn bộ mã nguồn Frontend.

TypeScript là một siêu tập (superset) mã nguồn mở của JavaScript được phát triển và bảo trì bởi tập đoàn Microsoft, được biên dịch trực tiếp ra JavaScript thuần trước khi chạy trên trình duyệt. TypeScript mang lại các giá trị cốt lõi vô cùng quan trọng cho dự án thông qua các cơ chế sau:

```
+---------------------------------------+
|  TypeScript: Kiểu dữ liệu tĩnh (Static Types)  |
|                                       |
|   +-------------------------------+   |
|   |  ES6+: Các tính năng JS mới   |   |
|   |                               |   |
|   |   +-----------------------+   |   |
|   |   | JavaScript thuần túy   |   |   |
|   |   +-----------------------+   |   |
|   +-------------------------------+   |
+---------------------------------------+
```

*   **Cơ chế Định kiểu Tĩnh (Static Typing):** TypeScript yêu cầu định nghĩa rõ ràng kiểu dữ liệu cho các biến, tham số truyền vào và kết quả trả về của hàm. Hệ thống định nghĩa các giao diện dữ liệu nghiêm ngặt cho các thực thể nghiệp vụ:
    *   `Lecturer`: Chứa thông tin chi tiết về mã, tên, chức vụ, loại giảng viên và số giờ dạy.
    *   `TimetableRow`: Định nghĩa cấu trúc một dòng thời khóa biểu gồm lớp, môn học, buổi và giảng viên được gán.
    *   `Preference`: Lưu trữ thông tin đăng ký nguyện vọng và vai trò của giảng viên.
    Nhờ đó, trình biên dịch TypeScript sẽ tự động phát hiện và cảnh báo ngay lập tức các lỗi sai lệch kiểu dữ liệu trong quá trình viết mã, triệt tiêu 95% các lỗi giao tiếp dữ liệu giữa Frontend và Backend.
*   **Hỗ trợ tối đa cho các công cụ lập trình (IDE Tooling):** Nhờ cơ chế định kiểu rõ ràng, các trình soạn thảo hiện đại (như VS Code hay Cursor) có thể cung cấp các tính năng tự động hoàn thành mã thông minh (IntelliSense), điều hướng mã nguồn nhanh chóng và hỗ trợ tái cấu trúc mã nguồn (Refactoring) quy mô lớn một cách an toàn mà không sợ phá vỡ các liên kết logic cũ.
*   **Khả năng tự động tài liệu hóa (Self-documenting):** Các Interfaces và Types trong TypeScript đóng vai trò như một bản đặc tả tài liệu sống động. Bất kỳ lập trình viên nào khi tham gia phát triển dự án chỉ cần nhìn vào định nghĩa kiểu dữ liệu là có thể lập tức hiểu được cấu trúc dữ liệu đầu ra đầu vào của từng component mà không cần đọc hàng ngàn dòng code logic bên dưới.

---

### 2.1.3. Tổng quan về ReactJS, Vite và thư viện giao diện Ant Design

Giao diện người dùng của hệ thống lập kế hoạch giảng dạy đòi hỏi tính tương tác cực kỳ cao, phản hồi nhanh chóng và bố cục trực quan sinh động để giảm thiểu áp lực cho cán bộ giáo vụ. Để hiện thực hóa mục tiêu đó, hệ thống sử dụng một bộ ba công nghệ Frontend hiện đại và mạnh mẽ hàng đầu hiện nay bao gồm ReactJS làm nền tảng ứng dụng, Vite làm công cụ đóng gói và Ant Design làm thư viện thành phần giao diện.

```
       +--------------------------------------------+
       |             FRONTEND APPLICATION           |
       +--------------------------------------------+
                              |
       +----------------------2----------------------+
       |                                             |
[ ReactJS (v19) ]                              [ Ant Design (v6) ]
- Kiến trúc Component-based                     - Drawer, Modal, Table
- State Management (useState, Context)         - Grid System, Typography
- Virtual DOM render tối ưu                    - Form Validation
       |                                             |
       +----------------------3----------------------+
                              |
                      [ Vite Bundler ]
                      - Native ESM Dev Server
                      - Siêu tốc độ biên dịch esbuild
```

#### A. ReactJS (Phiên bản 19)
ReactJS là một thư viện JavaScript mã nguồn mở được phát triển bởi Facebook dùng để xây dựng giao diện người dùng Single Page Application (SPA). ReactJS hoạt động dựa trên triết lý lập trình khai báo (Declarative UI) và kiến trúc dựa trên thành phần (Component-based).
- **Kiến trúc Component-based:** Giao diện hệ thống được chia nhỏ thành các thành phần độc lập, tự quản lý trạng thái riêng và có khả năng tái sử dụng rất cao (như thẻ thông tin giảng viên `LecturerCard`, dòng lịch học `TimetableRowComponent`, hộp thoại xác nhận `ConfirmationModal`). Điều này giúp mã nguồn Frontend cực kỳ ngăn nắp, dễ kiểm thử và dễ nâng cấp mở rộng.
- **Cơ chế Virtual DOM hiệu năng cao:** Thay vì cập nhật trực tiếp lên cấu trúc DOM của trình duyệt (vốn là một tác vụ tiêu tốn rất nhiều tài nguyên hiệu năng), ReactJS sử dụng một bản sao ảo của DOM trong bộ nhớ. Mỗi khi trạng thái (State) của ứng dụng thay đổi – ví dụ như khi cán bộ kéo giảng viên thả vào ô phân công, React sẽ tính toán sự khác biệt tối thiểu giữa DOM ảo cũ và mới (cơ chế Reconciliation/Diffing) và chỉ cập nhật đúng phần tử thay đổi lên DOM thật, mang lại tốc độ phản hồi cực kỳ nhanh chóng.
- **Quản trị trạng thái mạnh mẽ (State Management):** React cung cấp các Hooks mạnh mẽ như `useState`, `useEffect`, `useContext` và `useMemo` giúp hệ thống quản lý luồng dữ liệu một chiều (Unidirectional Data Flow) một cách rõ ràng và nhất quán, đảm bảo tính đồng bộ dữ liệu trên toàn bộ giao diện thời gian thực.

#### B. Vite (Phiên bản 8)
Vite là công cụ xây dựng (build tool) và đóng gói mã nguồn Frontend thế hệ mới được sáng tạo bởi Evan You (cha đẻ của VueJS). Trong nhiều năm qua, Webpack là tiêu chuẩn đóng gói dự án nhưng thường bộc lộ sự chậm trễ nghiêm trọng khi dự án phình to. Vite ra đời để giải quyết triệt để vấn đề này.
- **Tận dụng Native ESM:** Trong quá trình phát triển (development phase), Vite tận dụng cơ chế Native ES Modules (ESM) có sẵn trên các trình duyệt hiện đại. Vite không cần đóng gói toàn bộ dự án trước khi khởi động server, mà chỉ biên dịch và phân phối đúng file module mà trình duyệt yêu cầu, giúp thời gian khởi động server phát triển giảm xuống dưới 1 giây.
- **Biên dịch siêu tốc với esbuild:** Vite sử dụng `esbuild` – một công cụ biên dịch viết bằng ngôn ngữ Go – để đóng gói các thư viện phụ thuộc (dependencies), mang lại tốc độ nhanh hơn từ 10 đến 100 lần so với các công cụ viết bằng JavaScript truyền thống.
- **Hot Module Replacement (HMR) tức thời:** Khi lập trình viên thay đổi một dòng code giao diện, Vite chỉ cập nhật đúng module đó trên trình duyệt mà không cần tải lại toàn bộ trang web, giữ nguyên trạng thái làm việc hiện tại và tăng tốc độ phát triển lên gấp nhiều lần.

#### C. Thư viện giao diện Ant Design (Phiên bản 6)
Ant Design (AntD) là một trong những thư viện UI component chuyên nghiệp dành cho phân khúc doanh nghiệp phổ biến nhất thế giới. Được phát triển bởi các kỹ sư Ant Group, AntD cung cấp một hệ thống thiết kế (Design System) chuẩn hóa với tính thẩm mỹ cực kỳ cao.
- **Bộ thành phần phong phú và đồng nhất:** AntD cung cấp sẵn các component giao diện cao cấp đã được tối ưu hóa tối đa về mặt trải nghiệm người dùng và khả năng tương thích trình duyệt như bảng dữ liệu thông minh (`Table`), hộp thoại tương tác (`Modal`), bảng trượt thông tin (`Drawer`), các thanh lựa chọn tìm kiếm (`Select`, `Dropdown`), và hệ thống lưới (`Grid System`) hỗ trợ thiết kế đáp ứng (Responsive Design).
- **Thẩm mỹ cao và chuyên nghiệp:** Việc áp dụng triết lý thiết kế định hướng doanh nghiệp của AntD giúp giao diện của hệ thống lập kế hoạch giảng dạy thoát khỏi vẻ thô kệch của các phần mềm giáo vụ cũ, mang lại cảm giác cao cấp, sang trọng, tạo cảm hứng làm việc cho cán bộ khoa.
- **Cơ chế xác thực Form tự động:** AntD tích hợp sẵn thư viện quản lý Form vô cùng mạnh mẽ, hỗ trợ tự động kiểm tra tính hợp lệ của dữ liệu nhập vào (Validation) phía Client như kiểm tra định dạng email, bắt buộc nhập các ô dữ liệu gốc, giúp ngăn ngừa các dữ liệu rác trước khi gửi lên Backend.

---

### 2.1.4. Overview về FastAPI (Xây dựng Web API tốc độ cao)

Phía Backend của hệ thống lập kế hoạch giảng dạy đòi hỏi một framework có hiệu năng xử lý cực cao, hỗ trợ bất đồng bộ để đáp ứng tốt các tác vụ tính toán thuật toán CSP nặng nề và xử lý file Excel dung lượng lớn. **FastAPI** chính là sự lựa chọn tối ưu nhất đáp ứng hoàn hảo các tiêu chuẩn kỹ thuật khắt khe này.

FastAPI là một Web framework mã nguồn mở hiện đại, hiệu năng cao dùng để xây dựng các API bằng Python, được tạo ra bởi Sebastián Ramírez vào năm 2018. Dù ra đời muộn hơn Django và Flask, FastAPI đã nhanh chóng vươn lên dẫn đầu xu hướng phát triển Web API nhờ sở hữu các tính năng đột phá:

*   **Hiệu năng vượt trội (High Performance):** FastAPI là một trong những framework Python nhanh nhất hiện nay, có hiệu năng tiệm cận với NodeJS và Go. Có được tốc độ kinh ngạc này là nhờ FastAPI được xây dựng trực tiếp trên nền tảng của hai công nghệ cốt lõi: **Starlette** (đảm nhận chức năng định tuyến web siêu nhanh) và **Uvicorn** (máy chủ ASGI bất đồng bộ tốc độ cao).
*   **Hỗ trợ lập trình bất đồng bộ hoàn hảo (Asynchronous Programming):** FastAPI tích hợp sẵn cú pháp `async/await` của Python. Khi hệ thống nhận được các yêu cầu API đồng thời (ví dụ: hàng trăm giảng viên đăng ký nguyện vọng cùng lúc, hoặc cán bộ đang xuất Excel thời khóa biểu), cơ chế bất đồng bộ giúp máy chủ xử lý hiệu quả hàng ngàn kết nối song song mà không bị nghẽn (non-blocking), tối ưu hóa tài nguyên phần cứng server.
*   **Tự động tạo tài liệu API tương tác (Auto Documentation):** FastAPI tự động hóa hoàn toàn việc tạo tài liệu hướng dẫn sử dụng API theo tiêu chuẩn OpenAPI. Ngay khi cán bộ viết code định nghĩa các Endpoint, hệ thống sẽ tự động sinh ra trang Swagger UI trực quan tại đường dẫn `/docs`. Điều này giúp quá trình phối hợp kiểm thử tích hợp (Integration Test) giữa Frontend và Backend diễn ra cực kỳ suôn sẻ và minh bạch.
*   **Kiểm soát và chuẩn hóa dữ liệu mạnh mẽ bằng Pydantic:** FastAPI tích hợp chặt chẽ với thư viện Pydantic để thực hiện kiểm tra và chuẩn hóa dữ liệu (Data Validation & Serialization). Khi Frontend gửi một Request Body lên Backend, Pydantic sẽ tự động đối chiếu các trường thông tin đầu vào với Model đã định nghĩa. Nếu dữ liệu bị thiếu hoặc sai kiểu, FastAPI sẽ tự động trả về phản hồi lỗi chi tiết mã lỗi 422 (Unprocessable Entity) kèm mô tả chính xác trường bị lỗi, loại bỏ hoàn toàn các lỗi dữ liệu không hợp lệ đi sâu vào tầng Database.

---

### 2.1.5. Tổng quan về SQLAlchemy (ORM)

Trong kiến trúc phát triển phần mềm hiện đại, việc tương tác trực tiếp với cơ sở dữ liệu bằng các câu lệnh SQL thuần túy (Raw SQL) lồng ghép trong mã nguồn bộc lộ nhiều hạn chế nghiêm trọng như khó bảo trì, dễ xảy ra lỗi cú pháp khi cơ sở dữ liệu thay đổi cấu trúc, và đặc biệt là nguy cơ cao bị tấn công bảo mật thông qua lỗ hổng SQL Injection. Để giải quyết triệt để bài toán này, hệ thống đã ứng dụng thư viện **SQLAlchemy** làm cầu nối tương tác dữ liệu.

SQLAlchemy là thư viện ánh xạ quan hệ đối tượng (ORM - Object-Relational Mapping) mạnh mẽ và phổ biến nhất trong hệ sinh thái Python. Nó cung cấp cho lập trình viên một giải pháp trừu tượng hóa cơ sở dữ liệu toàn diện:

```
+--------------------------------------------------------+
|                   MÃ NGUỒN PYTHON (APP)                |
|  (Thao tác với đối tượng: lecturer.name = "Dũng")      |
+--------------------------------------------------------+
                           |
+--------------------------v-----------------------------+
|                     SQLALCHEMY ORM                     |
|  (Tự động ánh xạ đối tượng thành các câu lệnh SQL)     |
+--------------------------------------------------------+
                           |
+--------------------------v-----------------------------+
|              TẦNG TRỪU TƯỢNG HÓA DATABASE              |
|  (Hỗ trợ SQLite, PostgreSQL, MySQL...)                 |
+--------------------------------------------------------+
```

*   **Trừu tượng hóa Cơ sở dữ liệu và Độc lập Hệ quản trị:** SQLAlchemy cho phép định nghĩa cấu trúc bảng dữ liệu dưới dạng các class Python thuần túy. Lập trình viên tương tác với cơ sở dữ liệu thông qua các phương thức hướng đối tượng (ví dụ: `db.query(Lecturer).filter_by(id=1).first()`). SQLAlchemy sẽ tự động biên dịch các phương thức này thành các câu lệnh SQL tương ứng với hệ quản trị cơ sở dữ liệu đang sử dụng. Điều này mang lại sự linh hoạt tuyệt đối, cho phép hệ thống dễ dàng chuyển đổi hệ quản trị cơ sở dữ liệu từ SQLite (dùng khi lập trình cục bộ) sang PostgreSQL (khi triển khai production thực tế) mà không cần thay đổi bất kỳ dòng code logic nghiệp vụ nào.
*   **Quản trị Session và Transaction an toàn:** SQLAlchemy cung cấp cơ chế quản lý Session (phiên làm việc) mạnh mẽ. Toàn bộ các thao tác thêm, sửa, xóa dữ liệu trong một phiên làm việc được gom lại dưới dạng một Transaction. Nếu một thao tác trong chuỗi bị lỗi, SQLAlchemy hỗ trợ rollback toàn bộ để đưa cơ sở dữ liệu về trạng thái an toàn trước đó, đảm bảo tính toàn vẹn dữ liệu tuyệt đối của thời khóa biểu.
*   **Phòng ngừa tấn công SQL Injection tự động:** Nhờ cơ chế tham số hóa các truy vấn (Parameterized Queries), SQLAlchemy tự động lọc và vô hiệu hóa tất cả các ký tự đặc biệt nguy hiểm trong dữ liệu nhập vào từ người dùng, xây dựng một lá chắn bảo mật vững chắc cho tầng lưu trữ dữ liệu của khoa.

---

### 2.1.6. Tổng quan về Hệ quản trị Cơ sở dữ liệu (PostgreSQL/SQLite)

Cơ sở dữ liệu là trái tim của hệ thống lập kế hoạch giảng dạy, nơi lưu giữ toàn bộ thông tin nhạy cảm và quan trọng của Khoa như hồ sơ giảng viên, định mức giờ dạy, khung chương trình đào tạo của từng chuyên ngành và lịch sử các đợt nguyện vọng. Để tối ưu hóa hiệu quả hoạt động giữa hai giai đoạn phát triển phần mềm và vận hành thực tế, hệ thống áp dụng chiến lược sử dụng linh hoạt hai hệ quản trị cơ sở dữ liệu quan hệ: **SQLite** và **PostgreSQL**.

#### A. SQLite (Hệ quản trị Cơ sở dữ liệu Nhẹ cho Phát triển)
SQLite là một thư viện phần mềm cung cấp hệ quản trị cơ sở dữ liệu quan hệ dung lượng siêu nhẹ, không cần cấu hình máy chủ độc lập (Serverless). Toàn bộ cơ sở dữ liệu của SQLite được gói gọn trong duy nhất một tệp tin vật lý nằm trực tiếp trên ổ đĩa cứng của máy trạm.
*   **Lợi ích trong môi trường phát triển (Development):** Nhờ tính chất không cần cài đặt dịch vụ nền hay cấu hình cổng kết nối phức tạp, SQLite giúp lập trình viên khởi động và chạy thử dự án ngay lập tức. Tốc độ đọc ghi cục bộ cực nhanh của SQLite giúp việc chạy thử các bộ dữ liệu nhỏ và các ca kiểm thử tự động (Unit Tests) diễn ra vô cùng nhanh chóng và thuận tiện.

#### B. PostgreSQL (Hệ quản trị Cơ sở dữ liệu Cao cấp cho Vận hành Thực tế)
PostgreSQL (thường gọi là Postgres) là một hệ quản trị cơ sở dữ liệu quan hệ đối tượng mã nguồn mở mạnh mẽ, ổn định và có lịch sử phát triển hơn 30 năm. Postgres nổi tiếng thế giới nhờ tuân thủ nghiêm ngặt các tiêu chuẩn chuẩn hóa cơ sở dữ liệu và khả năng xử lý các tác vụ quy mô lớn của doanh nghiệp.
*   **Lợi ích trong môi trường vận hành thực tế (Production):** 
    *   *Khả năng chịu tải và đồng thời cao:* PostgreSQL hỗ trợ cơ chế MVCC (Multi-Version Concurrency Control) tiên tiến, cho phép nhiều người dùng đồng thời thực hiện thao tác ghi và đọc dữ liệu mà không gây ra tình trạng khóa bảng dữ liệu lẫn nhau, cực kỳ phù hợp khi hàng trăm giảng viên truy cập hệ thống đăng ký nguyện vọng cùng một thời điểm.
    *   *Hỗ trợ toàn diện ACID Transactions:* Đảm bảo các giao dịch dữ liệu (như phân công gán lịch chéo lớp học phần) được thực hiện một cách Nguyên tố, Nhất quán, Biệt lập và Bền vững, loại bỏ hoàn toàn các rủi ro mất mát hay sai lệch số liệu lịch biểu khi xảy ra sự cố đột ngột.
    *   *Tích hợp sao lưu tự động:* Hỗ trợ lập lịch sao lưu cơ sở dữ liệu định kỳ tự động (`PROJECT_1_SCHEDULE_BACKUP`), bảo vệ an toàn tuyệt đối dữ liệu lịch sử giảng dạy của Khoa qua nhiều năm đào tạo học thuật.
