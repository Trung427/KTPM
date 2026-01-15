# Bài tập thực hành kiểm thử với JUnit
## Chủ đề: Phân tích dữ liệu điểm số học sinh

---

## 1. Mô tả bài toán
Bài toán yêu cầu xây dựng một chương trình Java để phân tích dữ liệu điểm số học sinh.

Lớp `StudentAnalyzer` cung cấp hai chức năng chính:
- Đếm số học sinh đạt loại Giỏi (điểm >= 8.0).
- Tính điểm trung bình của các điểm hợp lệ trong danh sách.

Quy ước xử lý dữ liệu:
- Chỉ chấp nhận điểm trong khoảng từ 0 đến 10.
- Các điểm nhỏ hơn 0 hoặc lớn hơn 10 được coi là dữ liệu không hợp lệ và bị bỏ qua.
- Nếu danh sách điểm rỗng hoặc không có điểm hợp lệ, kết quả trả về là 0.

---

## 2. Cấu trúc thư mục
unittest/
├── src/
│ └── unittest/
│ └── StudentAnalyzer.java
├── test/
│ └── unittest/
│ └── StudentAnalyzerTest.java
├── lib/
│ └── junit-platform-console-standalone-1.13.0-M3.jar
├── bin/
└── README.md


---

## 3. Công nghệ sử dụng
- Ngôn ngữ: Java
- Thư viện kiểm thử: JUnit 5 (JUnit Jupiter)
- Môi trường phát triển: Visual Studio Code

---

## 4. Cách chạy chương trình và kiểm thử

### Cách 1: Chạy kiểm thử bằng Visual Studio Code
1. Mở thư mục `unittest` bằng Visual Studio Code.
2. Mở file `StudentAnalyzerTest.java`.
3. Nhấn nút **Run Test** hoặc **Run All Tests**.
4. Xem kết quả trong tab **Testing**.

### Cách 2: Chạy kiểm thử bằng dòng lệnh
```bash
java -jar lib/junit-platform-console-standalone-1.13.0-M3.jar --class-path bin --scan-class-path

