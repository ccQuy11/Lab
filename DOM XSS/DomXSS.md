<img width="1225" height="746" alt="Screenshot 2026-08-26 092523" src="https://github.com/user-attachments/assets/b3f33e11-3b0d-4fcb-a2ba-963e5b1a2795" />

<img width="1902" height="157" alt="Screenshot 2026-08-26 093020" src="https://github.com/user-attachments/assets/547b8449-ce09-475c-a673-b7231dcccf2c" />

Trình duyệt xử lí dữ liệu đầu vào bằng cách thiết lập eventListener trên đối tượng window để chờ message. Nó được kích hoạt khi có một sự kiện nào đó gọi hàm window.postMessage() đến trang hiện tại. Khi thông điệp đến, hàm callback thực thi và nhận đối tượng e, dữ liệu được truyền vào e.data

Mò 1 lúc trong tài liệu thì tôi tìm ra payload này 

    <iframe src="//vulnerable-website" onload="this.contentWindow.postMessage('print()','*')">

Tuy nhiên nếu để như thế mà đưa vào exploit server thì nó chỉ in ra chữ print() chứ chưa có sự kiện nào được kích hoạt nên không gọi được hàm print()

Payload cuối 

        <iframe src="//vulnerable-website" onload="this.contentWindow.postMessage('<img src=1 onerror=print()>','*')">

<img width="1911" height="898" alt="Screenshot 2026-08-26 094912" src="https://github.com/user-attachments/assets/35bf34a7-5a13-42f4-b660-c94cc40fbff0" />

<img width="1176" height="686" alt="Screenshot 2026-08-26 095012" src="https://github.com/user-attachments/assets/06aa1795-233b-4c7b-9523-c04814e07be4" />

<img width="935" height="183" alt="Screenshot 2026-08-26 095136" src="https://github.com/user-attachments/assets/a154deab-d030-46ae-959c-5ffe60238ac1" />

Trong thử thách này, trình duyệt kiểm tra thêm cả index của http hoặc https nếu bằng -1 thì sẽ bị false còn không sẽ kích hoạt location.href để trả về giá trị của url được đưa vào

Ngồi 1 lúc mày mò không ra tôi có xem solution và thấy người ta dùng payload kiểu <code>javascript:print()//http:</code> thì payload gửi message chứa payload của javascript và chuỗi http:. 

Payload cuối 

    <iframe src="//vulnerable-website" onload="this.contentWindow.postMessage('javascript:print()//http:','*')">

<img width="1917" height="875" alt="Screenshot 2026-08-26 095939" src="https://github.com/user-attachments/assets/43954097-6db5-42f5-b49e-95d059e1d12e" />
