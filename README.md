### Đây là đồ án cuối kỳ môn Xử lý dữ liệu lớn, với đề tài là GOM CỤM DỮ LIỆU BẰNG PHƯƠNG PHÁP HỌC SÂU KHÔNG GIÁM SÁT – DEEP UNSUPERVISED METHOD.
### Mục tiêu của dự án là:
Cải thiện kết quả phân cụm (clustering) trên các bộ dữ liệu phức tạp bằng cách sử dụng các phương pháp học sâu (deep learning) để trích xuất các đặc trưng quan trọng của dữ liệu trước khi áp dụng thuật toán gom cụm. Phân tích chuyên sâu nội dung
### Đề tài đã nghiên cứu các phương pháp:
Học sâu không giám sát phổ biến như Autoencoder (AE) và các biến thể (Variational Autoencoder - VAE, Denoising AE, Sparse AE), cùng với Generative Adversarial Network (GAN) và biến thể Bidirectional GAN (BiGAN).
Phương pháp được đề xuất và triển khai là sử dụng Variational Autoencoder (VAE) để học cách biểu diễn dữ liệu (tạo latent codes), sau đó sử dụng Encoder của VAE để ánh xạ dữ liệu và áp dụng thuật toán gom cụm K-means với số cụm $k=10$.
VAE được chọn vì nó giúp giảm hiện tượng overfitting so với AE thông thường và khắc phục được nhược điểm GAN collapse của GAN/BiGAN.
#### Mô hình VAE:
Encoder: Gồm 5 lớp Convolutional.
Decoder: Gồm 4 lớp Conv2DTranspose.
Latent Space (Bottleneck): Sử dụng 2 lớp mean và std để mã hóa dữ liệu thành một phân bố xác suất (khác với vector cố định của AE truyền thống).
Hàm Loss: Bao gồm Reconstruction Loss (tái tạo đầu vào) và Regularization Loss (sử dụng KL divergence để đảm bảo phân bố xác suất).
Thực nghiệm:
Dữ liệu: Bộ dữ liệu Fashion MNIST (70,000 ảnh xám 28x28), chia 60,000 ảnh cho huấn luyện và 10,000 cho kiểm thử.
Thông số: Số epoch là 20, batch size là 32.
Công nghệ: Sử dụng Python 3.7 với các thư viện Keras, TensorFlow, matplotlib và sklearn.
Đánh giá: Sử dụng hai chỉ số đo lường hiệu suất gom cụm là Adjusted Rand Index (ARI) và Fowlkes-Mallows Index.
