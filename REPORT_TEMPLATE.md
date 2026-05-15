# CSC4005 Lab 4 Report – CRNN for UrbanSound8K

## 1. Thông tin sinh viên

- Họ tên: Đỗ Lê Mạnh Hùng
- Mã sinh viên: 1671040014
- Lớp: KHMT 16-01
- Link GitHub repo: https://github.com/FIT-DNU-CS-16-01/csc4005-lab3-1dcnn-Pangorin
- Link W&B project: https://wandb.ai/15sofme-dai-nam-university/csc4005-lab3-urbansound-1dcnn?nw=nwuser15sofme

## 2. Mục tiêu thí nghiệm

Viết ngắn gọn 3–5 dòng về mục tiêu của Lab 4.

Gợi ý:

- Vì sao dùng log-mel spectrogram?
- CRNN khác gì so với 1D-CNN ở Lab 3?
- Mục tiêu đánh giá mô hình là gì?

- Với CRNN, log-mel spectrogram thường trực quan hơn vì nó giữ được cấu trúc thời gian–tần số.
- 1D-CNN nhận diện nhanh các sự kiện âm thanh cục bộ, CRNN kết hợp thêm bộ nhớ để hiểu ngữ cảnh của các chuỗi âm thanh dài liên tục
- Mục tiêu đánh giá mô hình: đánh giá loss, accuracy trên tập train & validation, quan sát xem mô hình có bị overfit hoặc underfit hay không

## 3. Cấu hình dữ liệu

| Thành phần | Giá trị |
|---|---|
| Dataset | UrbanSound8K |
| Số lớp | 10 |
| Train folds | 1–8 |
| Validation fold | 9 |
| Test fold | 10 |
| Feature | log-mel spectrogram |
| Sampling rate | 16 kHz |
| Duration | 4 giây |

## 4. Cấu hình mô hình

| Thành phần | Giá trị |
|---|---|
| Model | CRNN |
| CNN blocks | ? |
| RNN type | GRU / LSTM |
| Hidden size | 96 |
| Dropout | 0.3 |
| Optimizer | adamw |
| Learning rate | 0.001 |
| Batch size | 32 |
| Epochs | 25 |

## 5. Kết quả huấn luyện

Điền kết quả tốt nhất từ W&B hoặc `metrics.json`.

| Run | best_val_acc | test_acc | Ghi chú |
|---|---:|---:|---|
| logmel_crnn_gru_baseline | | | |
| extension_bilstm_crnn | | | |

## 6. Learning curves

Chèn hình `curves.png`.

Nhận xét:

- Mô hình có overfitting không?
- Validation loss có giảm ổn định không?
- Có cần early stopping không?

## 7. Confusion matrix

Chèn hình `confusion_matrix.png`.

Nhận xét:

- Lớp nào phân loại tốt?
- Lớp nào dễ bị nhầm?
- Có thể giải thích bằng đặc điểm âm thanh không?

## 8. So sánh với Lab 3 1D-CNN

| Tiêu chí | Lab 3: 1D-CNN | Lab 4: CRNN |
|---|---|---|
| Feature chính | MFCC / log-mel | log-mel |
| Khả năng học pattern cục bộ | Có | Có |
| Khả năng học quan hệ thời gian | Hạn chế | Tốt hơn |
| Test accuracy | | |
| Nhận xét | | |

## 9. Kết luận

Viết 5–8 dòng:

- CRNN có cải thiện so với 1D-CNN không?
- Kết quả có ổn định không?
- Nếu làm tiếp, em sẽ cải thiện gì?

## 10. Link minh chứng

- GitHub commit cuối:
- W&B run baseline:
- W&B run mở rộng:
