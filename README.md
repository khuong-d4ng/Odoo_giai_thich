
## Mục Lục

1. [Giới Thiệu Hệ Thống](#1-giới-thiệu-hệ-thống)
2. [Truy Cập Hệ Thống](#2-truy-cập-hệ-thống)
3. [Module Quản Lý Khách Hàng](#3-module-quản-lý-khách-hàng)
4. [Module Quản Lý Văn Bản](#4-module-quản-lý-văn-bản)
5. [Sử Dụng Dashboard](#5-sử-dụng-dashboard)

---

## 1. Giới Thiệu Hệ Thống

Hệ thống **Quản lý Khách hàng và Văn bản** giúp doanh nghiệp:

- ✅ Quản lý thông tin khách hàng tập trung
- ✅ Theo dõi đơn hàng theo trạng thái
- ✅ Quản lý văn bản đến/đi liên quan đến khách hàng
- ✅ Lưu trữ hồ sơ văn bản và công việc
- ✅ Xem thống kê trực quan qua Dashboard

### Hai Module Chính

| Module | Chức Năng Chính |
|--------|-----------------|
| **Quản lý Khách hàng** | Khách hàng, Đơn hàng, Thống kê |
| **Quản lý Văn bản** | Văn bản đến/đi, Hồ sơ văn bản, Hồ sơ công việc |

---

## 2. Truy Cập Hệ Thống

### Bước 1: Đăng nhập Odoo
1. Mở trình duyệt, truy cập địa chỉ hệ thống (ví dụ: `http://localhost:8069`)
2. Nhập **Email** và **Mật khẩu**
3. Nhấn **Đăng nhập**

### Bước 2: Chọn Module
Sau khi đăng nhập, trên thanh menu chính sẽ thấy:
- 📁 **Quản lý khách hàng**
- 📁 **Quản lý văn bản**

---

## 3. Module Quản Lý Khách Hàng

### 3.1. Quản Lý Khách Hàng

#### Xem danh sách khách hàng
1. Vào menu **Quản lý khách hàng** → **Quản lý khách hàng**
2. Danh sách hiển thị: Mã, Tên, Email, Loại, Trạng thái, Số đơn hàng

#### Thêm khách hàng mới
1. Nhấn nút **Tạo**
2. Điền thông tin:
   - **Tên khách hàng** *(bắt buộc)*
   - **Tên doanh nghiệp** *(nếu là doanh nghiệp)*
   - **Email**
   - **Loại khách hàng**: Cá nhân / Doanh nghiệp
   - **Trạng thái**: Mới / Cũ
3. Nhấn **Lưu**

> 💡 **Mẹo:** Mã khách hàng sẽ tự động sinh từ tên. Nếu muốn nhập tay, chỉ cần gõ vào ô Mã khách hàng.

#### Xem chi tiết khách hàng
- Nhấn vào tên khách hàng để mở form chi tiết
- Xem các tab: **Đơn hàng**, **Văn bản đến**, **Văn bản đi**
- Xem thống kê: Tổng đơn chờ xử lý, đã giao, đã hủy, tổng giao dịch

---

### 3.2. Quản Lý Đơn Hàng

#### Xem danh sách đơn hàng
1. Vào menu **Quản lý khách hàng** → **Quản lí đơn hàng**
2. Danh sách hiển thị: Tên đơn, Khách hàng, Đơn giá, Trạng thái, Ngày tạo

#### Tạo đơn hàng mới
1. Nhấn nút **Tạo**
2. Điền thông tin:
   - **Tên đơn hàng** *(bắt buộc)*
   - **Khách hàng** *(chọn từ danh sách)*
   - **Đơn giá** *(bắt buộc)*
   - **Trạng thái**: Mới (chờ xử lí) / Đã giao / Đã hủy
   - **Ngày tạo đơn**, **Hạn bàn giao**
3. Nhấn **Lưu**

#### Cập nhật trạng thái đơn hàng
1. Mở đơn hàng cần cập nhật
2. Thay đổi trường **Trạng thái**
3. Nhấn **Lưu**

> 📊 Thống kê đơn hàng của khách sẽ **tự động cập nhật** khi thay đổi trạng thái.

---

## 4. Module Quản Lý Văn Bản

### 4.1. Văn Bản Đến

Văn bản đến là văn bản nhận từ bên ngoài (khách hàng, đối tác, cơ quan).

#### Xem danh sách văn bản đến
1. Vào menu **Quản lý văn bản** → **Văn bản đến**

#### Tạo văn bản đến mới
1. Nhấn **Tạo**
2. Chọn **Phân loại**:
   - **Nội bộ**: Văn bản từ nội bộ công ty
   - **Khách hàng**: Văn bản từ khách hàng → chọn khách hàng
3. Điền thông tin:
   - **Số văn bản** *(bắt buộc)*
   - **Trích yếu** *(bắt buộc)*
   - **Ngày văn bản**, **Ngày đến**
   - **Cơ quan ban hành**, **Người ký**
   - **Loại văn bản**: Quyết định, Công văn, Thông báo...
   - **Độ khẩn**: Thường / Khẩn / Hỏa tốc
   - **Độ mật**: Bình thường / Mật / Tuyệt mật
   - **Trạng thái**: Mới / Đang xử lý / Đã xử lý
4. Đính kèm file (nếu có)
5. Nhấn **Lưu**

---

### 4.2. Văn Bản Đi

Văn bản đi là văn bản gửi ra bên ngoài.

#### Tạo văn bản đi
1. Vào menu **Quản lý văn bản** → **Văn bản đi**
2. Nhấn **Tạo**
3. Chọn **Phân loại** (Nội bộ / Khách hàng)
4. Điền thông tin:
   - **Số văn bản**, **Trích yếu**
   - **Nơi nhận**, **Người ký**
   - **Loại văn bản**, **Độ khẩn**, **Độ mật**
   - **Trạng thái**: Dự thảo → Chờ duyệt → Đã duyệt → Đã gửi
5. Nhấn **Lưu**

---

### 4.3. Hồ Sơ Văn Bản

Hồ sơ văn bản dùng để **nhóm các văn bản liên quan** vào cùng một hồ sơ.

#### Tạo hồ sơ văn bản
1. Vào menu **Quản lý văn bản** → **Hồ sơ văn bản**
2. Nhấn **Tạo**
3. Điền: Số hồ sơ, Tên hồ sơ, Loại hồ sơ, Mức độ bảo mật
4. Thêm văn bản vào hồ sơ:
   - Tab **Văn bản đến**: Chọn các văn bản đến liên quan
   - Tab **Văn bản đi**: Chọn các văn bản đi liên quan
5. Nhấn **Lưu**

---

### 4.4. Hồ Sơ Công Việc

Theo dõi công việc liên quan đến văn bản.

#### Tạo hồ sơ công việc
1. Vào menu **Quản lý văn bản** → **Hồ sơ công việc**
2. Nhấn **Tạo**
3. Điền thông tin:
   - **Mã công việc**, **Tên công việc**
   - **Mức độ ưu tiên**: Thấp / Trung bình / Cao / Rất cao
   - **Ngày giao**, **Hạn hoàn thành**
   - **Trạng thái**: Mới → Đang thực hiện → Hoàn thành
4. Liên kết văn bản liên quan (nếu có)
5. Nhấn **Lưu**

> 💡 Khi chuyển trạng thái sang **Hoàn thành**, tiến độ tự động = 100% và ghi nhận ngày hoàn thành.

---

### 4.5. Quản Lý Danh Mục

Vào menu **Quản lý văn bản** → **Hệ thống - Danh mục** để quản lý:

| Danh Mục | Mô Tả |
|----------|-------|
| Đơn vị | Danh sách đơn vị trong tổ chức |
| Chức vụ | Các chức vụ/vị trí |
| Loại văn bản | Quyết định, Công văn, Thông báo... |
| Độ mật | Bình thường, Mật, Tuyệt mật |
| Độ khẩn | Thường, Khẩn, Hỏa tốc |

---

## 5. Sử Dụng Dashboard

### 5.1. Dashboard Khách Hàng

1. Vào menu **Quản lý khách hàng** → **Dashboard khách hàng**
2. Các view có sẵn:
   - **Biểu đồ (Graph)**: Thống kê tổng giao dịch theo khách hàng
   - **Pivot**: Phân tích đa chiều theo loại và trạng thái khách hàng

### 5.2. Dashboard Đơn Hàng

1. Vào menu **Quản lý khách hàng** → **Dashboard đơn hàng**
2. Hiển thị **Kanban board** với các cột theo trạng thái:
   - Mới (chờ xử lí)
   - Đã giao
   - Đã hủy

### 5.3. Dashboard Văn Bản

1. Vào menu **Quản lý văn bản** → **Dashboard**
2. Hiển thị **Kanban board** văn bản đến:
   - Nhóm theo trạng thái: Mới, Đang xử lý, Đã xử lý
   - Badge màu cho độ khẩn: 🟡 Khẩn, 🔴 Hỏa tốc
   - Hiển thị tên khách hàng (nếu có)

---
