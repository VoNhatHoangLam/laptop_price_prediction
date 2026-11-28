
## 1. Tổng quan dữ liệu

- **Nguồn dữ liệu:** Tổng hợp từ 7 hệ thống bán lẻ (An Phát, HACOM, LaptopAZ, Phi Long, Phong Vũ, Phúc Anh, TechCare)
- **Tổng số bản ghi raw đầu vào:** 3.021 (sau khi loại bỏ các bản ghi thiếu trường bắt buộc `price_vnd`, `brand`, `condition_type` và khử trùng theo URL nội bộ)
- **Số bản ghi hợp lệ & không trùng lặp:** 2.961 (đã lọc bỏ 60 bản ghi trùng lặp y hệt cả 12 cột nội bộ và đối chiếu loại trừ trùng lặp 2 chiều với tập tham chiếu bản ghi của Thế Giới Di Động)

## 2. Phân bố theo tình trạng máy (`condition_type`)

| `condition_type` | Số lượng | Tỷ lệ |
| --- | ---: | ---: |
| `new` (máy mới) | 2.523 | 85,21% |
| `used` (máy đã qua sử dụng) | 438 | 14,79% |
| **Tổng cộng** | **2.961** | **100,00%** |

## 3. Thống kê giá trị bị thiếu (null / rỗng) theo từng cột

| Cột | Nhóm cột | Số ô thiếu | Tỷ lệ thiếu | Ghi chú |
| --- | --- | ---: | ---: | --- |
| `price_vnd` | Nhãn dự đoán | 0 | 0,00% | Trường bắt buộc |
| `brand` | Đầu vào | 0 | 0,00% | Trường bắt buộc |
| `cpu_model` | Đầu vào | 121 | 4,09% | |
| `ram_gb` | Đầu vào | 18 | 0,61% | |
| `ssd_gb` | Đầu vào | 184 | 6,21% | |
| `hdd_gb` | Đầu vào | 184 | 6,21% | |
| `gpu_model` | Đầu vào | 346 | 11,69% | |
| `screen_size_in` | Đầu vào | 142 | 4,80% | |
| `screen_width_px` | Đầu vào tùy chọn | 187 | 6,32% | |
| `screen_height_px` | Đầu vào tùy chọn | 187 | 6,32% | |
| `condition_type` | Đầu vào bắt buộc | 0 | 0,00% | Trường bắt buộc |
| `cosmetic_condition` | Đầu vào tùy chọn | 2.931 | 98,99% | Để trống với 2.523 máy `new`; 408 máy `used` thiếu mô tả |