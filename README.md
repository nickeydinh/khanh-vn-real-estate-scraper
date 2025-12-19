# Real Estate Data Scraper
## 1. Giới thiệu
Dự án được xây dựng nhằm thu thập, chuẩn hóa và lưu trữ dữ liệu bất động sản từ website **batdongsanvn**.  
Dữ liệu sau khi thu thập được lưu trữ trong **MongoDB** để phục vụ cho việc phân tích dữ liệu, xây dựng báo cáo.
---
## 2. Nguồn dữ liệu
- Website: https://batdongsan.com.vn/
---
## Mô Tả Trường Dữ Liệu Đầu Ra

| Trường (Field) | Kiểu dữ liệu (Type) | Mô Tả (Description)                                                      |
| :--- |:--------------------|:-------------------------------------------------------------------------|
| `post_id` | `string`            | ID duy nhất của bài đăng (trích xuất từ URL).                            |
| `property_url` | `string`            | Địa chỉ URL đầy đủ của bài đăng nguồn.                                   |
| `scraped_at` | `date(YY/MM/DD)`    | Dấu thời gian (timestamp) thể hiện thời điểm dữ liệu được cào.           |
| `type_property` | `string`            | Loại hình bất động sản đã được phân loại (e.g., House, Apartment, Land). |
| `title` | `string`            | Tiêu đề của bài đăng.                                                    |
| `address.province` | `string`            | Tỉnh / Thành phố của bất động sản.                                       |
| `address.district` | `string`            | Quận / Huyện của bất động sản.                                           |
| `address.ward` | `string`            | Phường / Xã của bất động sản.                                            |
| `address.street` | `string`            | Đường / Khu vực chi tiết.                                                |
| `latitude` | `number (float)`    | Vĩ độ.                                                                   |
| `longitude` | `number (float)`    | Kinh độ.                                                                 |
| `price` | `number (float)`    | Tổng giá trị bất động sản(đơn vị: VND).                                  |
| `price_per_spm` | `number (float)`    | Giá trên mỗi mét vuông(đơn vị: triệu/$m^2$).                             |
| `spec.area` | `number (float)`    | Diện tích (đơn vị: $m^2$).                                               |
| `spec.bedroom` | `number (integer)`  | Số phòng ngủ.                                                            |
| `spec.bathroom` | `number (integer)`  | Số phòng tắm / vệ sinh.                                                  |
| `spec.num_floor` | `number (integer)`  | Số tầng.                                                                 |
| `spec.orientation` | `number (integer)`  | Hướng nhà.                                                               |
| `spec.balcony_direction` | `string`            | Hướng ban công.                                                          |
| `spec.front_width` | `number (float)`    | Mặt tiền (chiều rộng, mét).                                              |
| `spec.road_width` | `number (float)`    | Chiều rộng đường vào (mét).                                              |
| `spec.legal` | `string`            | Tình trạng pháp lý (e.g., Sổ đỏ, HĐMB).                                  |
| `spec.furniture` | `string`            | Tình trạng nội thất.                                                     |
| `description` | `string`            | Nội dung mô tả chi tiết về bất động sản.                                 |
| `images` | `array<string>`     | Danh sách các URL hình ảnh.                                              |
| `date_posted` | `date(YY/MM/DD)`    | Ngày bài đăng được đăng tải.                                             |
| `date_expired` | `date(YY/MM/DD)`    | Ngày bài đăng hết hạn.                                                   |
| `news_type` | `string`            | Loại tin đăng.                                                           |

## 5. Ví dụ dữ liệu đầu ra

```json
    {
        "post_id": "40739766",
        "property_url": "https://batdongsan.com.vn/ban-can-ho-chung-cu-duong-pham-hung-phuong-me-tri-prj-keangnam-hanoi-landmark-tower/chinh-chu-ban-158-4m2-4-ngu-view-san-van-dong-noi-that-moi-cao-cap-xem-nha-24-7-pr40739766",
        "type_property": "Apartment",
        "title": "Chính chủ bán căn Keangnam 158.4m2, 4 ngủ view hồ siêu mát, nội thất mới cao cấp xem nhà 24/7",
        "address": {
            "province": "Hà Nội",
            "district": "Nam Từ Liêm",
            "ward": "Phường Mễ Trì",
            "street": "Đường Phạm Hùng"
        },
        "latitude": 21.016947081585887,
        "longitude": 105.783421241366,
        "price": 14800000000,
        "price_per_spm": 93.43,
        "area": 158.0,
        "spec": {
            "bedroom": 4,
            "bathroom": 3,
            "orientation": "Đông - Bắc",
            "balcony_direction": "Đông - Nam",
            "legal": "Sổ đỏ/ Sổ hồng",
            "furniture": "Đầy đủ"
        },
        "description": "Diện tích 158.4m², 4 ngủ 3WC.Tầng đẹp view hồ.Giá 14.8 tỷ.Nội thất mới 100%.Có slot ô tô.Ảnh cam kết thật 100%.Anh chị đi xem nhà liên hệ em Hưởng:0968 862 ***.",
        "images": [
            "https://file4.batdongsan.com.vn/resize/200x200/2024/08/22/20240822150827-3425_wm.jpg",
            "https://file4.batdongsan.com.vn/resize/200x200/2024/08/22/20240822150827-853e_wm.jpg",
            "https://file4.batdongsan.com.vn/resize/200x200/2024/08/22/20240822150827-0b02_wm.jpg",
            "https://file4.batdongsan.com.vn/resize/200x200/2024/08/22/20240822150827-83fc_wm.jpg",
        ],
        "date_posted": "2025-12-12",
        "date_expired": "2025-12-27",
        "news_type": "Tin thường",
        "contact_info": {
            "name": "Bùi Văn Hưởng",
            "profile_url": "",
            "avatar_url": "",
            "phone_visible": "",
            "zalo_url": ""
        },
        "scraped_at": "2025-12-19 02:05:05"
    }