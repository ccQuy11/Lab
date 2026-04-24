<img width="1174" height="610" alt="image" src="https://github.com/user-attachments/assets/03dd3e5b-5440-4f52-b718-51243e008d6d" />

Bài này yêu cầu tìm ra mật khẩu của admin. Tuy nhiên khi nhập truy vấn sẽ không trả về Database mà phải dựa vào cookie và ứng dụng hiển thị "Welcome back!" mới tính là thành công 

<img width="1725" height="692" alt="image" src="https://github.com/user-attachments/assets/1a8a3685-245d-4273-aeaa-10473ef8476a" />

Test thử 'OR 1=1' hiển thị Welcome Back có nghĩa là đã thành công, sau đó thử kiểm tra độ dài của mật khẩu

    AND (SELECT 'a' FROM users where username = 'administrator' and length(password) = 20)='a

<img width="1882" height="762" alt="image" src="https://github.com/user-attachments/assets/cec08d44-e5cc-41d3-a79d-752b7fe8bf46" />

Sau 1 lượt kiểm tra có thể thấy mật khẩu có 20 kí tự, từ đó kiểm tra từng kí tự và hàng một, đưa vào intruder để bruteforce từng mật khẩu một 

    AND (select substr(password, 1,1) FROM users where username = 'administrator')='a

<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/d5b3063c-be26-4415-bfcf-8b1c935f022f" />
