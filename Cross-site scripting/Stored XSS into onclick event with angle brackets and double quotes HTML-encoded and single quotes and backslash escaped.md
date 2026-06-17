<img width="1257" height="801" alt="image" src="https://github.com/user-attachments/assets/82fbcb0c-c947-4ad9-8114-4e700efa5499" />

Trong bài này trừ dấu gạch chéo và ngoặc đơn còn lại đều bị mã hóa 

<img width="1583" height="792" alt="image" src="https://github.com/user-attachments/assets/d9709513-0024-4a43-b816-e2b954aad963" />

Có thể thấy lỗ hổng được giấu trong phân website của máy chủ

<img width="1843" height="162" alt="image" src="https://github.com/user-attachments/assets/5a697283-8d93-4275-ae65-ad542ab286f2" />

Sự kiện onclick xảy ra khi nó gọi 1 biến tên tracker sau đó biến tracker này gọi phương thức track với URL của người dùng

Thử payload với các dấu được gợi ý xem có thể thoát ra hay không

<img width="1857" height="387" alt="image" src="https://github.com/user-attachments/assets/2081717e-580b-4014-a281-b8eb17dff4d0" />

Nó vẫn bị mã hóa 

    http://hhjjhlkjlkk?&apos;-alert(1)-&apos;
    
Sau 1 lúc làm không ra thì tôi có đi xem hint và thấy có sử dụng &apos để mã hóa ' thay vì dùng hẳn, dù hiển thị vẫn là ' nhưng khi vào trong onclick việc mã hóa dấu ' khiến cho nó hiểu đây là link uy tín cho nên khi nhấn vào sẽ xuất hiện cái alert(1)

<img width="1905" height="951" alt="image" src="https://github.com/user-attachments/assets/f9d6041a-5482-49f1-918c-3bf7e1d7462d" />

<img width="1902" height="732" alt="image" src="https://github.com/user-attachments/assets/2dc84eb1-3766-4116-bc4c-f58553ad23fe" />
