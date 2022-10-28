# String

- `1` Length

    ```bash
    /* length */
    let myString = " Hoc JS tai JS JS JS"
    const length = myString.length
    => length === 20
    ```

- `2` Find Index

  ```bash
    /\* indexOf
    -là tìm vị trí của chuỗi

    -rồi nếu có 2 hoặc nhiều các ký tự xuất hiện nhiều lần

    thì sử dụg tham số thứ 2 có vị trí sau cái thằng đầu tiên tìm được

    -

    \*/
    console.log(myString.indexOf("JS", 6));

  ```

- `3` Search

  ```bash
  Dùng để search giống indexOf nhưng để sử dụng cho regExpression
  ```

  - `4` Cut

  ```bash
  Dùng để search giống indexOf nhưng để sử dụng cho regExpression
  ```


    - `5`

    ```bash
    /_ length _/
    /_ lastIndexOf _/
    /_ search _/
    /_ slice _/
    /_ split _/
    /_ charAt _/
    /_ trim _/
    Kiểm tra kiểu dữ liệu: typeof 

    const string1 = myString.slice(1, myString.indexOf("JS", 6))
    console.log(typeof string1);  => string

    console.log(myString.slice(1,myString.indexOf("JS",6)));
    ```
