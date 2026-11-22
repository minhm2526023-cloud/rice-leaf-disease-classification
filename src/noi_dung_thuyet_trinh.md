# ỨNG DỤNG HỌC SÂU TRONG PHÂN LOẠI BỆNH TRÊN LÁ LÚA TẠI ĐBSCL
Học viên: Đinh Hoàng Minh | GVHD: PGS. TS. Nguyễn Thanh Hải | Đại học Cần Thơ

## 1. Giới thiệu & Đặt vấn đề
- Lúa gạo là cây lương thực chủ lực tại Đồng bằng Sông Cửu Long nhưng thường chịu thiệt hại bởi bệnh đạo ôn, cháy bìa lá và đốm nâu.
- Phương pháp chẩn đoán bằng mắt thường tốn nhiều thời gian, phụ thuộc kinh nghiệm và dễ nhầm lẫn trên diện rộng.
- Mục tiêu: Xây dựng mô hình Học sâu (CNN) tự động nhận diện 4 trạng thái lá lúa từ ảnh chụp thực địa.

## 2. Dữ liệu & Phương pháp nghiên cứu
- Bộ dữ liệu gồm 4.000 ảnh thực địa chia đều 4 nhóm theo tỷ lệ 70% Train – 15% Val – 15% Test.
- Tiền xử lý: Chuẩn hóa kích thước 224x224 pixel và tăng cường dữ liệu (xoay, lật ngẫu nhiên).
- Huấn luyện và tinh chỉnh 3 kiến trúc VGG16, MobileNetV2, ResNet50 trong 30 epoch với bộ tối ưu Adam.

## 3. Kết quả thực nghiệm & Đánh giá
- VGG16 đạt độ chính xác 89,40% (F1-Score: 0,89).
- MobileNetV2 đạt 92,15% với kích thước gọn nhẹ (3,5 triệu tham số), tối ưu cho thiết bị di động.
- ResNet50 dẫn đầu với độ chính xác 95,30% (F1-Score: 0,95) nhờ cơ chế kết nối tắt chống triệt tiêu đạo hàm.
[IMAGE: bieu_do_bao_cao.png]

## 4. Kết luận & Hướng phát triển
- Khẳng định tính khả thi cao của mạng nơ-ron tích chập trong bài toán chẩn đoán bệnh hại trên cây lúa.
- Hướng phát triển: Mở rộng thu thập ảnh ngoài đồng ruộng và đóng gói ứng dụng di động hoạt động ngoại tuyến (Offline).