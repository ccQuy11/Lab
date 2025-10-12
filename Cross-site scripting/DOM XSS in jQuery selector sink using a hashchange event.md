<img width="1139" height="685" alt="image" src="https://github.com/user-attachments/assets/19665f7e-d6a3-4fe3-85b9-b6ece8cf2582" />

Mở src code ra đọc thì có dòng này 

<img width="1325" height="145" alt="image" src="https://github.com/user-attachments/assets/61c22394-b627-4e91-ba78-8d3f3d0a6f83" />

Hiểu thì là dùng để cuộn xuống trang tiếp theo tuy nhiên bị mã hóa và có thể dùng decodeURL để mở  

Có thể thử payload #<img src=1 onerror=print()> để thử thì lần đầu nó sẽ chuyển về src 1 nhưng lần 2 thì xong do nó đã chuyển xuống cuộn 1 và không thể trigger lại

Vào exploit server dùng payload sau để gửi

            <iframe src="https://0a5100fb038a6682807e12f5007b0097.web-security-academy.net/#" onload="this.src +='<img src=1 onerror=print()>'" hidden="hidden">

            </iframe>

![Uploading image.png…]()
