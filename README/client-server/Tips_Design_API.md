# Tips Khi truyền parameter và nhận biết
Link: https://viblo.asia/p/restful-api-huong-dan-thiet-ke-the-best-practices-Qpmlex9DZrd#:~:text=Searching%2C%20Sorting%2C%20Filtering%2C%20and%20Pagination
* `Các parameter Sẽ bắt đầu sau dấu ? ở sau endpoint của url`

* `1 Filter là sử dụng toán tử && và truyền vào nhiều parameter cùng nhau`
    ```bash



    
    parameter1 & parameter2
    
    parameter có kiểu dữ liệu là 1 object chứa key:value 
    ```
    

* `2 Search`
    ```bash
    1 Sử dụng Get
    2 Tips thiết kế: chỉ có key duy nhất là search và truyền vào value để tìm kiếm
    ```

* `3 Pagination`
    ```bash
    1 Sử dụng Get
    2 Tips thiế kế: 
    ```
* `4 Sorting`
    ```bash
    Sử dụng Get
    ```