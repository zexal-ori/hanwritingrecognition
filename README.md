# HandwritingRecognition - Nhận dạng chữ viết tay bằng CRNN
- [Giới thiệu](#angel-giới-thiệu)
- [Dataset](#anchor-dataset)
- [Train and predict](#anchor-train-and-predict)

## :angel: Giới thiệu
- Bài toán đặt ra là chuyển những hình ảnh chữ viết tay tiếng Việt thành dữ liệu lưu trong tệp văn bản (text). Đại khái, input là một hình ảnh chứa một câu văn và output là những đoạn text xuất hiện trong hình ảnh đó.
- Cách tiếp cận ở đây là sử dụng thuật toán deep learning để giải quyết. Cụ thể, chúng ta sẽ cần một **CNNs** để trích xuất các đặc trưng của ảnh, và bởi vì đầu ra là chuỗi, nên ta nghĩ ngay đến cần **RNN** để xử lý. Ngoài ra còn cần sử dụng **CTC network** để tính loss trong quá trình huấn luyện và thu được output theo thời gian.
  
![image](image.png)
    
## :anchor: Dataset:
- Dữ liệu để train (test) là một foldler chứa 2 folder con là **img** và **label**.
- Trong đó:
  - **img** là tập các file hình ảnh về chữ viết tay (trên 1 dòng)
  - **label** là tập các file txt chứa nội dung về hình ảnh tương ứng.
(các file trong img và label tương ứng cần có tên giống nhau)
- Tham khảo: [train_data](https://github.com/zexal-ori/hanwritingrecognition/tree/teambr/data)
  
## :anchor: Train and predict
- Training:
    ```bash
    python main.py --dstrain {train_folder} --dsval {val_folder} --savedir {save_folder} --nepochs {num} 
    ```
    
  - Để biết chi tiết các cấu hình khi train, ta có thể sử dụng lệnh sau:
    ```
    python main.py -h
    ```
  - Quá trình training: [link_train](https://colab.research.google.com/drive/1HAr-5Yl_6vAoxbGhlvV9VfTHdzECsxzZ?usp=sharing)

- Predict:
  - Tham khảo tại [predict.ipynb](https://github.com/zexal-ori/hanwritingrecognition/blob/teambr/predict.ipynb).
  - Kết quả:

  ![image](https://github.com/zexal-ori/hanwritingrecognition/blob/teambr/predict.ipynb)
