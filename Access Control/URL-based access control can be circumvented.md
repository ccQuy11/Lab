![image](https://github.com/user-attachments/assets/fcc7ef47-093c-4422-be54-214efbf964ef)

Mục tiêu: xóa user carlos

Lỗ hổng: Kiểm soát truy cập do cấu hình nền tảng không đúng 

Bài này có sự thay đổi trong bài trước khi ta cần phải thay đổi và thêm X-Original-URL vào trong phần yêu cầu gốc đề vượt qua và tiến đến phần admin

Mở burpsuite và paste link vào browser của nó 

![image](https://github.com/user-attachments/assets/c4e5efaf-2dba-4a1c-a3ad-fba831816f19)

Thì ở đây nếu ta vào admin panel sẽ bị từ chối 

![image](https://github.com/user-attachments/assets/767a22d6-c2aa-4af0-872c-52d44b0241f4)

Do lỗ hổng này liên quan tới phương thức POST tức nó liên quan đến phần gửi dữ liệu lên server nên ta thay GET bằng POST, thêm phần X-ORIGINAL-URL: /admin vào cuối phần backend 

![image](https://github.com/user-attachments/assets/7bac83ad-767c-474b-8b1f-8437058c63c7)

Có thể thấy là đã vượt quyền và bypass và được admin nên tiếp tục thử với /admin/deleteUser xem như nào 

![image](https://github.com/user-attachments/assets/a42982bc-781d-48d5-8200-20ef210a204e)

Đã bị lỗi từ client,

Trong phần solution thì nó chỉ dẫn là nên sử dụng /?username=carlos là câu truy vẫn và chỉ để đường dẫn là /admin/delete thì sau khi hiểu ra thì có vẻ nó vẫn sẽ hoạt động như admin thường ở phần front-end 

![image](https://github.com/user-attachments/assets/6a8c770a-5e2e-41d1-9f50-2dbcee5dded2)

Nó đã found và trả về 302 tức là thành công

![image](https://github.com/user-attachments/assets/62901eed-a435-459e-84b3-1a59db534d93)
