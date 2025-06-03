![image](https://github.com/user-attachments/assets/d14d4846-dfab-4b72-ae79-77d7e9117110)
Mục tiêu: lấy file /etc/passwd

Bài này thì đã bị mã hóa bằng URL-decode (không biết là Double hay là Unicode) nhưng có vẻ web này đã không filter kĩ mã hóa trước khi đưa vào sử dụng

Kịch bản: sử dụng cả Double và Unicode encoding để giải

Đầu tiên ta sử dụng payload của unicode là %2e%2e%2f%2e%2e%2f%2e%2f%2e%2e%2fec%2fpasswd  là mã hóa của ../../../etc/passwd nhưng có vẻ như cái này cũng đã được filter để không thể đọc được file /etc/passwd 
![image](https://github.com/user-attachments/assets/4d53f1bc-3ecf-4c23-bde7-e98ffa397fd5)

Sau đó sử dụng sang payload của double là %252e%252e%252f%252e%252e%252f%252e%252e%252f%252e%252e%252fetc%252fpasswd và ở đây thì đã ra solve

Từ đó có thể thấy web chỉ có thể giải mã hóa được 1 lần và không thể giải ra mã hóa thứ 2 

Link đọc thêm: https://owasp.org/www-community/Double_Encoding

Ảnh solve:  ![image](https://github.com/user-attachments/assets/32a72500-483e-4c74-aa9c-9d8d97a3fb32)
