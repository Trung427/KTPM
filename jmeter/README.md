# Kiểm thử hiệu năng với JMeter

## 1. Mục tiêu
- Sử dụng Apache JMeter để thực hiện kiểm thử hiệu năng website.
- Thiết kế nhiều kịch bản kiểm thử với các tham số khác nhau.
- Thu thập và phân tích các chỉ số hiệu năng cơ bản.
- Trình bày kết quả kiểm thử dưới dạng báo cáo markdown.

## 2. Website được kiểm thử
- Website: https://www.wikipedia.org
- Giao thức: HTTPS

## 3. Môi trường & công cụ
- Apache JMeter: 5.6.3
- Hệ điều hành: Windows
- Trình duyệt mô phỏng: Chrome (User-Agent)

## 4. Các kịch bản kiểm thử

### 4.1 Thread Group 1 – Kịch bản cơ bản
- Số lượng người dùng: 10
- Số vòng lặp: 5
- Hành vi:
  - Gửi yêu cầu HTTP GET đến trang chủ (`/`)
- Mục đích:
  - Đánh giá hiệu năng website trong điều kiện tải nhẹ.

### 4.2 Thread Group 2 – Kịch bản tải nặng
- Số lượng người dùng: 50
- Ramp-up period: 30 giây
- Số vòng lặp: 1
- Hành vi:
  - Gửi HTTP GET đến:
    - Trang chủ (`/`)
    - Trang con (`/wiki/Main_Page`)
- Mục đích:
  - Kiểm tra khả năng chịu tải của website khi số lượng người dùng tăng cao.

### 4.3 Thread Group 3 – Kịch bản tùy chỉnh
- Số lượng người dùng: 20
- Thời gian chạy: 60 giây
- Hành vi:
  - Gửi HTTP GET đến:
    - `/wiki/Software_testing`
    - `/wiki/Apache_JMeter`
- Mục đích:
  - Mô phỏng hành vi người dùng truy cập nhiều trang con trong một khoảng thời gian liên tục.

## 5. Kết quả kiểm thử
- Các chỉ số được thu thập:
  - Response Time
  - Throughput
  - Error Rate
- Kết quả được lưu dưới dạng file CSV trong thư mục `results/`:
  - `threadgroup1_basic.csv`
  - `threadgroup2_heavy_load.csv`
  - `threadgroup3_custom.csv`

## 6. Nhận xét & kết luận
- Khi số lượng người dùng tăng, thời gian phản hồi trung bình có xu hướng tăng.
- Throughput tăng đáng kể ở kịch bản tải nặng.
- Error Rate gần như bằng 0, cho thấy website hoạt động ổn định trong phạm vi kiểm thử.
- Apache JMeter là công cụ hiệu quả để kiểm thử hiệu năng và phân tích khả năng chịu tải của hệ thống.

## 7. Minh chứng
- File cấu hình JMeter: `test-plan.jmx`
- File kết quả: các file CSV trong thư mục `results/`
- Ảnh chụp Summary Report và View Results Tree
