<img width="1354" height="937" alt="image" src="https://github.com/user-attachments/assets/36cd155f-78f2-4522-b0df-ebf9bad5c544" />

Mục tiêu: bỏ qua SameSite lax và ghi đè phương thức

Lỗ hổng

Đăng nhập và thử thay đổi email của người dùng xong đưa nó vào repeater:

<img width="1919" height="1015" alt="image" src="https://github.com/user-attachments/assets/ae0477c3-2b74-48f9-a8b5-cf71bd406a2f" />

Như trong bài viết thì ví dụ có nêu ra rằng phương thức method có thể được hỗ trợ và được ưu tiên hơn phương thức thông thường cho mục đích định tuyến. Từ đó có thể dùng phương thức đó để che giấu cho cái phương thức yêu cầu chính:

Thay đổi method cùng với đó thêm &_method=POST ở cuối dòng

<img width="1919" height="1002" alt="image" src="https://github.com/user-attachments/assets/d16aa2ee-af73-4b59-975c-fe5997440312" />

Nhìn vào có thể thấy là response trả về vẫn được nhận thay vì nếu chỉ dùng mỗi GET thì sẽ không được thậm chí là đơ luôn

<img width="1919" height="924" alt="image" src="https://github.com/user-attachments/assets/7741b964-e498-437b-a668-7411dd56ca4e" />

Từ đó tạo CSRF PoC và thay đổi email là xong 

<img width="1919" height="992" alt="image" src="https://github.com/user-attachments/assets/a2fa5fb0-7eaa-43b4-9098-6643178de879" />


