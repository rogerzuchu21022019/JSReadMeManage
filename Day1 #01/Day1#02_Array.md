# Array

- `1` Tips Array

  ```bash
  <!-- Check -->
  Array.isArray([]) => true
  Array.isArray({}) => false

  <!-- legnth -->
  Array.length => tổng elements

  <!-- Lấy index -->
  Array.[0] => index = 0
  ```

- `2` Method in array

  - Tạo ra

  * Tác dụng

    - đều có 3 tham số ở trong 1 func

    ```bash
    (item(newArray), indexOfArray, arrayOld)

    item: này thì quá quen,

    index: cũng quá quen,

    arrayOld : có thể lấy ra xài cũng được, hoặc nếu không thì lấy cái newArray
    ```

  * Solve

    ```bash
    <!-- Pop  => Xoá phần tử cuối mảng và lấy value của nó ra -->
    const languages = [1,2,3,"Java"]
    console.log(languages.pop()) => Java
    console.log(languages) => [1,2,3] đã xoá phần tử cuối
    Nếu xoá hết rồi thì pop sẽ là undefiled
    Array languages thì mảng rỗng

    <!-- Push -->
    languages.push('Dart','java')
    push vào cuối mảng

    <!-- Shift -->
    Nguợc lại với pop => xoá phần tử đầu ở mảng

     <!-- Unshift -->
    Ngược lại với thằng Push => push vào đẩu mảng

        <!-- Splice -->
    Tổ hợp của push và pop nhưng thêm tính năng vị trí
    splice(a,b) có 2 tham số là xoá
    vd: a là index muốn bắt đầu
    b là số lượng thì khi chạy nó sẽ xoá chính vị trí index = indextruyền vào và tuỳ theo số lượng sẽ quyết định có xoá các phần tửliền sau của nó hay không ( nếu b =0 thì không xoá, b =1,2,3,4thì xoá số lượng theo nó)

    splice(a,b,c) có 3 tham số có thể là xoá và add
                    xoá khi (1,1,"Dart") => Xoá số 1 và thêm Dart vào
                    hoặc cũng là add không
                    add khi (1,0,"Dart")
                    hoặc là thay thế,
                    replace khi (1,1,"Dart")
                    link: https://youtu.be/KrYacXScNQk?t=724

    <!-- Foreach  --> => Lặp qua từng item trong array
    <!-- Every  --> => All For one
    hoạt động y chang mảng như có bọc thêm 1 điều kiện
    nó trả về true/false => Nếu tất cả đều > 0 thì sẽ
    true Ngược lại chỉ cần có 1 thằng lạc loài < 0 thì sẽ false

    const data = [
    {
        id: 1,
        name: "vu",
        age: 19,
    },
    {
        id: 2,
        name: "vu",
        age: 20,
    },
    {
        id: 3,
        name: "vu",
        age: 18,
    },
    {
        id: 4,
        name: "vu",
        age: 29,
    },
    ];

    const isAge = data.every((user,index) => {
        return user.age < 18;
    });


    console.log(isAge); => false
    ```

    ```bash
    some() ngược lại với every . => One for all :)))
    Every cần tất cả các ông để thoả mãn yêu cầu,
    còn thằng some chỉ cần 1 ông thoả mãn là được. Này xử lý khi
    ông nào có điều kiện ở trước (0,1,2,3,4) càng gần 0 thì
    càng nhanh ra

    find() => tìm 1 item trong đó và return về 1 object => quá quen

    filter() => thì ra nó là trả về tất cả object và nó còn có thể filter theo từng diều kiện
    ```

    Lịnk : https://youtu.be/AT-yhX26_Ao?t=802

    ```bash
    map()
    Là 1 func dùng để CRUD

    Read: return item
    Update: return {
        ...item,
        age: item.age+1
    }
    Create return  {
        ...item, // => lấy lại nguyên item cũ
        newData1:{}, // add new data dô
        newData2:{}, // add new data dô
        newData3:"", // add new data dô
        newData4: 4, // add new data dô
    }
    Delete: return null | 123 | "abc"
    ```

    ```bash
    const mainList = [
        { id: 1, name: 'vu', age: 19 },
        { id: 2, name: 'vu', age: 20 },
        { id: 3, name: 'vu', age: 18 },
        { id: 4, name: 'vu', age: 29 }
    ];

    const subList_Update = mainList.map((item) => {
        return {
        ...item,
        age: item.age+1
        }
    });

    subList_Update = [
        { id: 1, name: 'vu', age: 20 },
        { id: 2, name: 'vu', age: 21 },
        { id: 3, name: 'vu', age: 19 },
        { id: 4, name: 'vu', age: 30 }
    ]

    const subList_Delete = mainList.map((item) => {
        return null
        //  return 123
        //  return "abc xyz"
        //  return {}
        //  return anythings
    });

    subList_Update = [
        { id: 1, name: 'vu', age: 20 },
        { id: 2, name: 'vu', age: 21 },
        { id: 3, name: 'vu', age: 19 },
        { id: 4, name: 'vu', age: 30 }
    ]

    const subList_Read = mainList.map((item) => {
        return item
    });

    subList_Read = [
        { id: 1, name: 'vu', age: 19 },
        { id: 2, name: 'vu', age: 20 },
        { id: 3, name: 'vu', age: 18 },
        { id: 4, name: 'vu', age: 29 }
    ]

    const subList_Create = mainList.map((item) => {
        return  {
            ...item,
            address: {
                street: "TMT2A",
                houseNumber: item.age,
            },
            listFriend: {
                name: item.name,
                phone: `${item.id}${item.age}${item.age}${item.age}${item.age}`,
                income: `${item.id}${item.id}${item.id}${item.id}${item.id}${item.id}${item.id}`,
            },
        };
    });

    subList_Create = [
        {
            //get old data
            id: 1,
            name: 'vu',
            age: 19,
            
            // new data
            address: {
                street: 'TMT2A', 
                houseNumber: 19 
            },
            listFriend: {
                name: 'vu',
                phone: '119191919',
                income: '1111111' 
            }
        },
        {
            //get old data
            id: 2,
            name: 'vu',
            age: 20,

            // new data
            address: { 
                street: 'TMT2A', 
                houseNumber: 20 
            },
            listFriend: { 
                name: 'vu',
                phone: '220202020', 
                income: '2222222' 
            }
        },
        {
            //get old data
            id: 3,
            name: 'vu',
            age: 18,

            // new data
            address: { street: 'TMT2A', houseNumber: 18 },
            listFriend: {
                name: 'vu', 
                phone: '318181818', 
                income: '3333333' 
            }
        },
        {
            //get old data
            id: 4,
            name: 'vu',
            age: 29,

            // new data
            address: {
                street: 'TMT2A', 
                houseNumber: 29 
            },
            listFriend: {
                name: 'vu', 
                phone: '429292929', 
                income: '4444444' 
            }
        }
    ]

    ```
