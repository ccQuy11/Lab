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
