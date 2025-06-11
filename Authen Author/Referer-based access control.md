![image](https://github.com/user-attachments/assets/7a0d1e1f-60c5-471b-aaee-aefcfefa5bc2)

Mục tiêu: đẩy wiener lên làm admin

Lỗ hổng: kiểm soát truy cập dựa trên người giới thiệu

Sơ qua thì dạng tấn công này sẽ tập trung vào phần reference nơi mà có thể thêm vào để làm thay đổi tiêu đề cũng như yêu cầu 

Mở burpsuite, vào tk admin và nâng user carlos lên admin

![image](https://github.com/user-attachments/assets/9c9fbe10-1298-46d2-9059-a4566f94558e)

Ở phần request check phần reference thì có thể thấy ở đây đã có đường dẫn admin như trong lí thuyết nên từ đây có thể để bất cứ 1 user nào( nếu không có thì phải thêm vào)

Để request kia vào repeater, thay đổi username sang wiener cũng như session của nó 

![image](https://github.com/user-attachments/assets/d6e5ee66-5c6c-4124-a4c2-4110a907fa9b)

Có vẻ đã nhận 

![image](https://github.com/user-attachments/assets/a25d6dce-678f-43b3-bbd4-94c49b035dfa)
