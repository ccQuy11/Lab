<img width="1235" height="632" alt="image" src="https://github.com/user-attachments/assets/e4b556f7-e561-4c2e-bbab-db2c31132b2d" /><img width="1235" height="632" alt="image" src="https://github.com/user-attachments/assets/1066822b-7dba-4dc1-b388-fcb3ef504433" />

Đây là 1 dạng XSS khá lạ khi nó chồng chéo cả 2 loại là Reflect và Dom vào với nhau

Gõ thử 1 cái gì đó và vào code để xem  

<img width="1918" height="842" alt="image" src="https://github.com/user-attachments/assets/79e9b1dd-db3e-44de-99b9-f2430fc9d809" />

Có thể thấy chuỗi tìm kiếm được lưu trong thẻ <h1> còn 2 đoạn <script> bên trên được dùng để xử lí code, thử vào đoạn searchResults.js

<img width="1918" height="943" alt="image" src="https://github.com/user-attachments/assets/df17f633-bcca-4165-9601-c011e6fcdc28" />

    function search(path) {
    var xhr = new XMLHttpRequest();
    xhr.onreadystatechange = function() {
        if (this.readyState == 4 && this.status == 200) {
            eval('var searchResultsObj = ' + this.responseText);
            displaySearchResults(searchResultsObj);
        }
    };
    xhr.open("GET", path + window.location.search);
    xhr.send();

Đoạn mã này dùng để xử lí việc tìm kiếm cho trang web này

    var xhr dùng để khai báo hàm XMLHttpRequest, hàm này dùng để thực hiện yêu cầu path đến 1 đường dẫn được chỉ định cùng với các tham số tìm kiếm của URL hiện tại

    xhr.onreadystatechange dùng để xử lí việc gọi thuộc tính thay đổi "readyState" của XMLHttpRequest, nó kiểm tra tình trang ready là 4 và status là 200

    eval('var searchResultsObj = ' + this.responseText);: sử dụng hàm eval để diễn giải văn bản bằng cách tạo 1 biến searchResultsObj và gán giá trị phản hồi vào và thực hiện việc hiển thị nó ra

    xhr.open dùng để gọi để method Get nhằm nhận dữ liệu từ path chỉ định đén địa chỉ với các tham số tìm kiếm của URL  hiện tại 

    xhr.send thực hiện việc gửi yêu cầu HTTP

Trong đoạn mã này, hàm eval() thực chất là 1 lỗ hổng, theo trích dẫn từ [MDN  ](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/eval)

<img width="1918" height="762" alt="image" src="https://github.com/user-attachments/assets/214a147a-46b2-4b5a-ab0f-9d92c4cb3252" />

<img width="1918" height="552" alt="image" src="https://github.com/user-attachments/assets/3c10ce87-a439-446c-826f-0269675fe775" />

Nhìn vào đoạn này có thể thấy 123 đang được đặt trong dấu ngoặc kép, tuy nhiên chuyện gì xảy ra nếu đặt thêm 1 dấu hoặc kép ở phía trước 

<img width="1918" height="583" alt="image" src="https://github.com/user-attachments/assets/16375f37-ca4a-4cbc-9ad1-d5e9a7155b24" />

Kí tự \ là kí tự thoát để nói bỏ qua kí tự tiếp theo để không kết thúc chuỗi searchTerms, có thể thử dụng thêm 1 \ trong phần nhập của người dùng để thông báo là kết thúc dòng này 

<img width="1918" height="1030" alt="image" src="https://github.com/user-attachments/assets/27015416-e776-483e-b00a-a644d2a43eed" />

Có thể thấy alert(1) đã được thoát ra ngoài tuy nhiên vẫn còn 1 dấu "} nữa cần được vượt , lúc này có thể thêm kí tự }// để đóng gói nốt đối tượng JavaScript.

<img width="1918" height="975" alt="image" src="https://github.com/user-attachments/assets/8663596a-521d-4f92-b03c-bf7a4d353405" />

Copy lại và đưa vào phần search 

<img width="1918" height="982" alt="image" src="https://github.com/user-attachments/assets/866c9afb-2037-4063-991b-95becdacb5cc" />

