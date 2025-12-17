# Real Estate Data Scraper from batdongsanvn
## Mô Tả Trường Dữ Liệu Đầu Ra



| Trường (Field) | Mô Tả (Description)                                                      |
| :--- |:-------------------------------------------------------------------------|
| `post_id` | ID duy nhất của bài đăng (trích xuất từ URL).                            |
| `property_url` | Địa chỉ URL đầy đủ của bài đăng nguồn.                                   |
| `scraped_at` | Dấu thời gian (timestamp) thể hiện thời điểm dữ liệu được cào.           |
| `type_property` | Loại hình bất động sản đã được phân loại (e.g., House, Apartment, Land). |
| `title` | Tiêu đề của bài đăng.                                                    |
| `address` | Địa chỉ của bất động sản.                                                |
| `latitude` | Vĩ độ ở định dạng số thập phân.                                          |
| `longitude` | Kinh độ ở định dạng số thập phân.                                        |
| `price_vnd` | Tổng giá trị bất động sản, đơn vị VND.                                   |
| `price_per_spm` | Giá trên mỗi mét vuông.                                                  |
| `spec.area_m2` | Diện tích (đơn vị $m^2$).                                                |
| `spec.bedroom` | Số phòng ngủ.                                                            |
| `spec.bathroom` | Số phòng tắm/vệ sinh.                                                    |
| `spec.num_floor` | Số tầng.                                                                 |
| `spec.orientation` | Hướng nhà.                                                               |
| `spec.balcony_direction` | Hướng ban công.                                                          |
| `spec.front_width` | Mặt tiền (chiều rộng).                                                   |
| `spec.road_width` | Chiều rộng đường vào.                                                    |
| `spec.legal` | Tình trạng pháp lý (e.g., Sổ đỏ, HĐMB).                                  |
| `spec.furniture` | Tình trạng nội thất.                                                     |
| `description` | Nội dung mô tả chi tiết về bất động sản.                                 |
| `images` | Danh sách các URL hình ảnh.                                              |
| `date_posted` | Ngày bài đăng được đăng tải.                                             |
| `expire_posted` | Ngày bài đăng hết hạn.                                                   |
| `type_news` | Loại tin đăng (e.g., Tin thường, Tin VIP).                               |
