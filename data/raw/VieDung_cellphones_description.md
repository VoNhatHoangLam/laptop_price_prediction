# Báo cáo mô tả dữ liệu CellphoneS (`cellphones_laptops.csv`)

## 1. Tổng quan dữ liệu

- **Nguồn dữ liệu:** CellphoneS (`cellphones_laptops.csv`)
- **Tổng số bản ghi raw đầu vào:** 3.000
- **Số bản ghi hợp lệ & không trùng lặp:** 2.883 (đã lọc bỏ các bản ghi thiếu trường bắt buộc `price_vnd`, `brand`, `condition_type` và khử trùng lặp theo `product_id`)

## 2. Phân bố theo tình trạng máy (`condition_type`)

| `condition_type` | Số lượng | Tỷ lệ |
| --- | ---: | ---: |
| `new` (máy mới) | 1.449 | 50,26% |
| `used` (máy đã qua sử dụng) | 1.434 | 49,74% |
| **Tổng cộng** | **2.883** | **100,00%** |

## 3. Thống kê giá trị bị thiếu (null / rỗng) theo từng cột

| Cột | Nhóm cột | Số ô thiếu | Tỷ lệ thiếu | Ghi chú |
| --- | --- | ---: | ---: | --- |
| `price_vnd` | Nhãn dự đoán | 0 | 0,00% | Trường bắt buộc |
| `brand` | Đầu vào | 0 | 0,00% | Trường bắt buộc |
| `cpu_model` | Đầu vào | 4 | 0,14% | |
| `ram_gb` | Đầu vào | 17 | 0,59% | |
| `ssd_gb` | Đầu vào | 8 | 0,28% | |
| `hdd_gb` | Đầu vào | 8 | 0,28% | |
| `gpu_model` | Đầu vào | 9 | 0,31% | |
| `screen_size_in` | Đầu vào | 45 | 1,56% | |
| `screen_width_px` | Đầu vào tùy chọn | 88 | 3,05% | |
| `screen_height_px` | Đầu vào tùy chọn | 88 | 3,05% | |
| `condition_type` | Đầu vào bắt buộc | 0 | 0,00% | Trường bắt buộc |
| `cosmetic_condition` | Đầu vào tùy chọn | 1.454 | 50,43% | Để trống với 1.449 máy `new`; 5 máy `used` thiếu mô tả |
| `used_grade` | Phụ trợ | 1.461 | 50,68% | Phân hạng máy cũ |
| `product_id` | Phụ trợ | 0 | 0,00% | Dùng để khử trùng lặp |
| `related_new_product_id` | Phụ trợ | 1.781 | 61,78% | ID sản phẩm mới tương ứng (nếu có) |
| `product_name` | Phụ trợ | 0 | 0,00% | |
| `product_url` | Phụ trợ | 0 | 0,00% | |
