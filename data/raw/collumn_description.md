# Mô tả các trường dữ liệu cần crawl

| Trường | Vai trò | Nơi lấy và cách lưu |
| --- | --- | --- |
| `price_vnd` | Nhãn dự đoán | Giá bán công khai, lưu số nguyên VND.  |
| `brand` | Đầu vào | Hãng từ tên sản phẩm hoặc đường dẫn danh mục, ví dụ `ASUS`. |
| `cpu_model` | Đầu vào | Bộ xử lý → Công nghệ CPU. Giữ đầy đủ mã và hậu tố, ví dụ `Intel Core 5 210H`. |
| `ram_gb` | Đầu vào | Bộ nhớ RAM, Ổ cứng → RAM. Lưu dung lượng lắp sẵn theo GB. |
| `ssd_gb`, `hdd_gb` | Đầu vào | Bộ nhớ RAM, Ổ cứng → Ổ cứng. Tách dung lượng lắp sẵn theo loại ổ, tính bằng GB. |
| `gpu_model` | Đầu vào | Đồ họa → Card màn hình. Chọn GPU rời chính nếu máy có cả GPU rời và tích hợp. |
| `screen_size_in` | Đầu vào | Màn hình → Kích thước màn hình, tính bằng inch. |
| `screen_width_px`, `screen_height_px` | Đầu vào tùy chọn | Màn hình → Độ phân giải. Tách chiều ngang và chiều dọc theo pixel. |
| `condition_type` | Đầu vào bắt buộc | Chuẩn hóa nhãn của tin bán hoặc bộ lọc danh mục thành `new` cho máy mới, `used` cho máy đã qua sử dụng. |
| `cosmetic_condition` | Đầu vào tùy chọn | Lưu nguyên văn phần mô tả sau nhãn **Tình trạng sản phẩm** trên cùng trang chi tiết với giá của chiếc máy cũ. Để trống với máy mới hoặc khi nguồn thiếu mô tả. |

Bắt buộc có `price_vnd`, `brand` và `condition_type`.

`cpu_model`, `gpu_model`, `ram_gb`, `ssd_gb`, `hdd_gb`, `screen_size_in`, `screen_width_px` và `screen_height_px` có thể thiếu. Nếu không xác định được độ phân giải, để trống cả hai chiều. Lưu dữ liệu thiếu thành `null` trong checkpoint và ô trống trong CSV. Chỉ ghi `0` cho SSD hoặc HDD khi xác định máy không có loại ổ đó. Với giá bán, bỏ qua giá trả góp, thu cũ và ưu đãi yêu cầu điều kiện riêng.
