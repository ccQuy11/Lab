<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/38c25271-ddd3-45e4-a98a-1d214423f7ea" />

Mục tiêu: trích xuất file trong /home/carlos/secret

Trong bài này máy chủ đã chặn 1 vài đuôi file nhưng nó có thể được bảo vệ bằng cách thêm 1 đuôi file vào phía sau

Ví dụ:
      
      1.abc%00.def

%00 là kĩ thuật null byte, khi đưa vào hệ thống kiểm tra nó vẫn nhận kết quả và cho upload nhưng khi truyền xuống ở tầng thấp, nó được hiểu là kết thúc chuỗi và làm cho chương trình xử lí coi như .def không tồn tại

<img width="1919" height="1022" alt="image" src="https://github.com/user-attachments/assets/d666c2e3-5cc7-496d-a132-71eef6f4974f" />

Có thể thấy máy chủ chỉ nhận 2 file là Jpg và Png nên thay thử 1 trong 2 vào sau đuôi .php

<img width="1919" height="1020" alt="image" src="https://github.com/user-attachments/assets/46467e81-868b-4b1f-82e6-2ebccd9adfe6" />

Khai thác và lấy kết quả

<img width="1919" height="664" alt="image" src="https://github.com/user-attachments/assets/63d99d0a-6496-4866-9c18-76116f1bd975" />

<img width="1919" height="1024" alt="image" src="https://github.com/user-attachments/assets/44ebecd2-2307-488c-931f-fd7a09e8fc25" />
