# Ứng dụng Học sâu trong Phân loại Bệnh trên Lá Lúa tại Đồng bằng Sông Cửu Long

## 1. Giới thiệu đề tài
Lúa gạo là cây lương thực chủ lực tại Đồng bằng Sông Cửu Long (ĐBSCL), nhưng năng suất thường xuyên chịu thiệt hại nghiêm trọng bởi các bệnh phổ biến như đạo ôn, cháy bìa lá và đốm nâu. Dự án này ứng dụng Thị giác máy tính và Học sâu (Deep Learning) nhằm tự động nhận diện sớm bệnh hại qua ảnh chụp thực địa.

## 2. Mục tiêu nghiên cứu
- Xây dựng và đánh giá hiệu năng các kiến trúc mạng nơ-ron tích chập (CNN) trong bài toán phân loại 4 trạng thái lá lúa (Khỏe mạnh, Đạo ôn, Cháy bìa lá, Đốm nâu).
- Lựa chọn mô hình tối ưu nhất về độ chính xác và khả năng triển khai trên thiết bị di động hỗ trợ nông dân.

## 3. Phương pháp thực hiện
- **Dữ liệu:** 4.000 ảnh lá lúa thực địa chia đều 4 lớp theo tỷ lệ 70% Train – 15% Validation – 15% Test.
- **Tiền xử lý:** Chuẩn hóa kích thước `224 × 224` pixel, tăng cường dữ liệu (xoay, lật ngẫu nhiên).
- **Huấn luyện:** Tinh chỉnh (Fine-tuning) 3 kiến trúc **VGG16**, **MobileNetV2** và **ResNet50** trong 30 epoch trên GPU Tesla T4 với bộ tối ưu Adam ($lr = 10^{-4}$) và hàm mất mát Cross-Entropy.

## 4. Kết quả chính
| Mô hình | Độ chính xác (Accuracy) | Chỉ số F1-Score |
| :--- | :---: | :---: |
| VGG16 | 89,40% | 0,89 |
| MobileNetV2 | 92,15% | 0,92 |
| **ResNet50** | **95,30%** | **0,95** |

## 5. Cấu trúc thư mục dự án
```text
rice-leaf-disease-classification/
├── data/               # Thông tin mô tả và liên kết bộ dữ liệu 4.000 ảnh lá lúa
├── src/                # Mã nguồn huấn luyện mô hình và sinh biểu đồ đánh giá
├── docs/               # Toàn văn bài báo khoa học (PDF) và Poster khổ A0
├── results/            # Biểu đồ so sánh hiệu năng (300 DPI) và ma trận nhầm lẫn
├── LICENSE             # Giấy phép mã nguồn mở MIT
├── README.md           # Tài liệu tổng quan dự án
├── CONTRIBUTING.md     # Hướng dẫn quy trình đóng góp mã nguồn
└── CITATION.cff        # Chuẩn trích dẫn dự án trong nghiên cứu khoa học
