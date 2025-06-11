![image](https://github.com/user-attachments/assets/95833a2a-4aac-49f8-a1cd-bbcd62f1a362)

Mục tiêu: lấy được bản ghi của người dùng trước, từ đó có được mật khẩu của user carlos

Lỗ hổng: IDOR

Ở bài này lỗ hổng IDOR có thể làm thay đổi các tệp tĩnh, mở burpsuite lên và dán link lab vào 

![image](https://github.com/user-attachments/assets/2f1b252c-2988-4a91-aab2-05ace561d8c4)

Tạo 1 bản nói chuyện gì đó với sever và download tất cả cái đấy về

![image](https://github.com/user-attachments/assets/a742808b-cbd0-4f95-be99-dc0239fc9992)

![image](https://github.com/user-attachments/assets/9989baf0-debb-40d6-a8b6-e4a405ead4ba)

Có thể thấy view transcript chỉ cho tải từ 2.txt trở lên và 1.txt đã bị ẩn đi nên mặc định 1.txt đang chứa passwd của user carlos

Đưa phần downloadtranscript/2.txt và repeater và thay đổi 2 thành 1

![image](https://github.com/user-attachments/assets/09faf57a-7444-4262-9868-5493956dcb81)

Có thể thấy ở đây đã tìm thấy passwd quay về và nhập tên user cũng như mật khẩu vào 

![image](https://github.com/user-attachments/assets/c2ddd546-0331-4edb-ad88-42c4067f3439)
