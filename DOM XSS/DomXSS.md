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

<img width="1183" height="682" alt="image" src="https://github.com/user-attachments/assets/b4790207-0c4d-4a04-93c0-136bc1c65a65" />

<img width="1005" height="503" alt="image" src="https://github.com/user-attachments/assets/1cf06acd-1964-4deb-b79b-fd2d1820b4fe" />

Trong source code có thể thấy thuộc tính type và load-channel bên trong thay đổi thuộc tính src

Từ đó có thể dựa vào 2 điều kiện này để khai thác. Ngồi 1 lúc thì tôi không có mày mò được gì nữa nên xem lời giải để tìm payload cuối 

    <iframe src=https://YOUR-LAB-ID.web-security-academy.net/ onload='this.contentWindow.postMessage("{\"type\":\"load-channel\",\"url\":\"javascript:print()\"}","*")'>

<img width="1917" height="871" alt="image" src="https://github.com/user-attachments/assets/ac270d53-31dd-484b-b8a1-71ef8da6e513" />


<img width="1241" height="540" alt="image" src="https://github.com/user-attachments/assets/95b8ba79-51f8-4f45-b53b-130596413544" />

Open redirection xảy ra khi attacker có thể thao túng được đích để chuyển hướng giữa các miền khác nhau 

<img width="1846" height="127" alt="image" src="https://github.com/user-attachments/assets/710b7518-7973-4a94-ac7b-913a9aabf72f" />

Lỗ hổng xảy ra do url chỉ check rằng nó có chứa https hay không còn lại đoạn đằng sau không được bảo mật kĩ. Thêm vào đó có cả location.href là điều kiện cần để Open Redirection xảy ra

Payload 

        https://0a0300e103e7b1d683145fd200c90004.web-security-academy.net/post?postId=5&url=https://exploit-0abe00dd03c5b14a83aa5e4a011d00ff.exploit-server.net/

<img width="1917" height="850" alt="image" src="https://github.com/user-attachments/assets/bb68a8e7-896b-4270-b405-a22cbdbaf957" />

<img width="1287" height="730" alt="image" src="https://github.com/user-attachments/assets/667c4957-0489-4e40-9eb4-6c4b374478ad" />

Cookie bị thao túng khi attacker có thể thiết lập một giá trị cookie tùy ý khi user đăng nhập vào

<img width="1303" height="145" alt="image" src="https://github.com/user-attachments/assets/da7d999a-5746-4697-a243-539927531687" />

Trong chall này cookie được tạo ra khi user đăng nhập vào và lưu nó trong một cookie tên là lastViewProduct

Ngồi 1 lúc không tra được tài liệu cho mẫu payload về dạng này tôi tham khảo solution và payload như sau

        <iframe src="https://YOUR-LAB-ID.web-security-academy.net/product?productId=1&'><script>print()</script>" onload="if(!window.x)this.src='https://YOUR-LAB-ID.web-security-academy.net';window.x=1;">

Đoạn mã khi gửi vào exploit server, khi nạn nhân mở thẻ iframe và truy cập url có chứa payload. Lúc này đoạn mã script sẽ lấy toàn bộ cookie lưu vào lastViewedProduct và nó sẽ chứa cả mã độc product?productId=1&'><script>print()</script>. Sau khi truyền vào, sự kiện onload của thẻ được kích hoạt và chuyển hướng nạn nhân về trang chủ. Tại đó, lập trình viên lấy ra dữ liệu từ cookie và payload được kích hoạt

<img width="1917" height="907" alt="image" src="https://github.com/user-attachments/assets/03162d38-bfe9-461d-b807-a389bacf5c22" />


