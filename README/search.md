# Search Logic

- Đầu tiên phải call data về

  - Tạo ra 2 list

    - mainList với useState

    - subList với useState

  - Tác dụng

    - mainList để hiển thị dữ liệu từ api

    - subList để filter với thanh search

  - Solve

    - const [mainList, setMainList] = useState([]);

    - const [subList, setSubList] = useState([]);

- Viết function beginFilter

  - Tạo ra các event xử lý logic

  - Tác dụng:

          * Gõ vào để tìm kiếm theo keyword và show nút clear

          * Click vào nút clear sẽ set Empty và list trở lại full elements

  - Solve:

    - Check text của search bar null

      - filterByTitle with subList

      - return về các filter

      - setMainList với cái filterByTitle đó để hiển thị ra cái list mới chỉ có 1 phần tử

      - setSearch với text rỗng

    - else

      - setMainList với cái mainList ban đầu

      - setSearch với text rỗng

    - code support: filterArrayPattern
