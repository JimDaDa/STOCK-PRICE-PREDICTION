### Đây là đồ án cuối kỳ môn Nhập môn học máy, với đề tài là DỰ ĐOÁN GIÁ CỔ PHIẾU BẰNG CÁC MÔ HÌNH HỌC MÁY.
#### Mục tiêu của dự án là:
- Phân tích và đưa ra giải pháp dựa vào học máy để dự đoán giá cổ phiếu SHB trong tương lai.
- Các mốc thời gian dự đoán: 14 ngày (theo ngày) và 7 tuần (theo tuần).
- Cơ sở lý thuyết: Đề tài bắt đầu bằng việc giới thiệu về thị trường chứng khoán, khái niệm cổ phiếu, và các chỉ số tài chính cơ bản để đánh giá cổ phiếu (P/E, EPS, P/B, DPR).
#### Phương pháp Nghiên cứu và Mô hình Học máy
Đề tài tập trung vào việc áp dụng và so sánh hiệu suất của ba mô hình học máy (Machine Learning - ML) và học sâu (Deep Learning - DL) sau:
- Mô hình Học máy Hồi quy (RNN - Recurrent Neural Network):
  + Nghiên cứu kiến trúc, ưu nhược điểm của RNN, và ứng dụng trong các bài toán chuỗi thời gian.
  + Xây dựng mô hình và thực hiện dự đoán theo cả ngày và tuần.
- Mô hình Học máy Đa lớp (MLP - Multi-Layer Perceptron):
  + Nghiên cứu kiến trúc và ứng dụng của MLP.
  + Xây dựng mô hình và thực hiện dự đoán.
- Mô hình Học sâu (LSTM - Long Short-Term Memory):
  + Nghiên cứu khái niệm, so sánh với học máy, và đi sâu vào cấu trúc cổng của LSTM.
  + Xây dựng mô hình LSTM để dự đoán giá cổ phiếu, tận dụng khả năng ghi nhớ dài hạn của mô hình này đối với dữ liệu chuỗi thời gian.
#### Xử lý Dữ liệu và Kỹ thuật Tăng cường Hiệu suất
- Thu thập Dữ liệu: Dữ liệu giao dịch của cổ phiếu SHB được thu thập từ trang web dstock.vndirect.com.vn thông qua API.
- Chọn lọc Đặc trưng (Features): Các đặc trưng được sử dụng bao gồm:
  + date (Ngày/Tháng/Năm)
  + open (Giá mở cửa)
  + ceilingPrice (Giá trần)
  + floorPrice (Giá sàn)
  + close (Giá đóng cửa)
- Xây dựng Tập dữ liệu: Dữ liệu thô được xử lý thành hai tập dữ liệu riêng biệt:
  + SHB_dataset_date.csv (dữ liệu theo ngày)
  + SHB_dataset_week.csv (dữ liệu theo tuần, bằng cách gom nhóm theo tuần và tính trung bình các chỉ số).
- Chống Overfitting: Đề tài đã nghiên cứu và áp dụng các phương pháp chống Overfitting (hiện tượng mô hình quá khớp dữ liệu huấn luyện) vào cả hai mô hình RNN và MLP, bao gồm:
  + Validation
  + Cross-validation
  + Early stopping
  + Dropout
  + Regularization
