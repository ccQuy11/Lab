![image](https://github.com/user-attachments/assets/de5fb2cd-9533-4d1f-aa3f-624aff89ad02)
Mục tiêu: lấy được file /etc/passwd

Ở bài này ta vẫn cần phải lấy được file /etc/passwd nhưng ở đây thì chuỗi đường dẫn trước khi được đưa vào sẽ bị ứng dụng xóa. Hiểu đơn giản thì nếu ta dùng ../../../ để lấy file etc/passwd tác dụng sẽ nhưng bằng không

Kịch bản tấn công: sử dụng payload được cho ở solution 
Ở solution tác giả đã cho payload ....//....//....//etc/passwd để sử dụng và nó có thể lấy được file /etc/passwd 
![image](https://github.com/user-attachments/assets/fcce9f13-826c-4307-b2bc-f385869909ab)
Tuy nhiên lúc này không hiểu được payload có ý nghĩa gì cho nên có như không

Sau 1 hồi nghĩ thì nhớ ra có 1 payload khác kiểu ..././..././..././etc/passwd, thử vào thì bất ngờ là nó cũng có thể lấy được 

Link đọc cái payload đấy: https://cookiearena.org/hoc-pentester/lo-hong-file-path-traversal/?utm_source=get_more_hint

Nói đơn giản thì khi nhập payload này vào nếu lập trình viên phát hiện “../” trong input, chương trình sẽ thực hiện việc xoá bỏ chuỗi đó. Nên hacker sẽ đưa vào …/./ để khi nó xoá thì còn lại chuỗi ../ (trích từ bài viết) 

Từ đó có vẻ cái payload được cho nó cũng sẽ có cách hoạt động như vậy và trang web đang không chuẩn hóa đường dẫn trước khi sử dụng 

Kết quả 
![image](https://github.com/user-attachments/assets/d2fa6f7a-9b97-4b73-a0b0-205725ff9181)

Hẹ hẹ
