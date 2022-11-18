# Step

## `I Part1 ` 
* `1 add global express`

```bash
yarn global add express-generator
```

* `2 init project`

```bash
express --view=ejs Server 

**Server là tên folder của app
```

* `3 cd đến folder vừa tạo`


* `4 add libraries`

```bash
yarn add  bcrypt mongoose nodemon randombytes dotenv jsonwebtoken joi nodemon redis body-parser express-session ioredis connect-redis  
```


* `5 đổi file www thành server.js`

```bash
chạy code helper
server.JS

```

* `6 Tạo folder src để chứa tất cả các file public,routes,utils,views,app.js`
* `7 Vào server.js thay đổi import app.js`
```bash
const app = require(`../src/app`);
```

* `8 tạo file .env run code helper`
```bash
.env.Node...
```
* `9 run nodemon trong package.js`

    `duplicate start đổi thành dev và import đường dẫn của server.js vào`

```bash
"scripts": {
"start": "node ./bin/www",
"dev": "nodemon ./bin/www"
},
thành 
"scripts": {
    "start": "node ./bin/server",
    "dev": "nodemon ./bin/server"
  },
```

* `10 yarn dev chạy thử`

## `II Part2 Connect DB,Server`

* `11 connect Mongodb`
  * `Tạo folder utils trong src và tạo 2 folder`

    ```bash
    1 client-web

    2 server
    ```

  * `Tạo file MultiConnection.js trong folder server`
  * `Chạy code helper`

  ```bash
  multiConnection...
  ```
* `12 connect Heroku`

  * `Nhớ 3 bước quan trọng:`

    * `1 Tạo file Procfile trong ServerGraduate và add`

      ```bash
      web:node ./bin/server.js 
      or
      web:node ./bin/server

      nhớ chú ý web:node ko được có khoảng trắng
      ```

    * `2 là thêm "engines":{} dưới "dev" trong package.json`

      * `Chạy lệnh để lấy version của nodejs`

        ```bash
        node -v
        ```

      * `Copy paste vào`

        ```bash
        "start": "node ./bin/server",
        "dev": "nodemon ./bin/server",
        "engines":{
          "node":"18.11.0"
        }
        ```

    * `3 là PORT ở trong file server.js không được để hardcode`


* `13 up project lên github rồi chia 2 nhánh server1 server2`
* `14 Tạo .gitignore và bỏ vào các file `

    ```bash
    node_modules
    .env
    yarn.lock
    ```

* `15 Chạy git init rồi push lên`

* `16 Vào terminal login heroku`

  ```bash
  Heroku login
  ```
* `17 Vào Heroku Git rồi create a new app`

* `18 Vô phần heroku chạy lệnh ở trong terminal`


  ```bash
  heroku git:remote -a asm-game-server
  asm-game-server là tên của project
  ```
  * `1 yarn dev chạy ở local thử`
  * `2 chọn repository `
* `19 Vô connect nhánh server2 -> Autho deploy -> Deploy`
  * `Theo dõi log nếu nó chuyển từ State app crash sang thành State up là ok`

* `20 connect Redis`
  * `Tạo folder middlewares trong src và tạo file RedisConnection`
  * `Chạy code helper`

    ```bash
    redisConfig.Pattern
    ```

* `21 vào file server.js trong src/bin/server.js và import vào`

  * `Lưu ý về redis sẽ lỗi phần client nên tạm thời ko import`
  ```bash
  require(`../src/middlewares/RedisConnection`)
  ```

  * `để ý thấy có thông báo connect là ok`

## III Tái cấu trúc folder
* `22 vào file app.js chạy code helper`

  ```bash
  app.JS...
  ```
*  `23 config từ trên xuống như trong file app.js theo thứ tự`

    ```bash
    1 ManagerMiddleware

    2 HandleError

    3 ManagerRouter
    ```

*  `24 Vô folder middleware tạo file Manager.js và HandlerError.js`

    ```bash
    1 ManagerMiddleware

    2 HandleError
    ```

*  `25 Run code helper trong từng file`

    ```bash
    1 middleware...

    2 handleError...
    ```

*  `26 Run code helper trong từng file`

    ```bash
    1 middleware...

    2 handleError...
    ```
*  `27 Vô routers Tạo folder manager -> Tạo Manager.js rồi run code helper`

    ```bash
    1 routerManager....

    2 Đọc lại chú thích về 1 url để nhớ lại
    
    3 Tổ chức cấu trúc folder routes lại luôn

    4 Nhớ tab cho đến lúc hết để tránh bỏ quên điều gì

    5 Các ApiUser.router chưa có bây giờ sẽ đi tạo
    ```
*  `28 Trong folder API Tạo 2 file`

    ```bash
    1 Api.User.js

    2 Api.Product.js

    ** Lưu ý là nếu project có nhiều tính năng thì mỗi thằng
    sẽ được khởi tạo như User và Product . VD có thêm tính năng của Admin
    thì 
    3 Api.Admin.js 
    ...
    ```

*  `29 Trong Api.User.js`

    ```bash
    1 import router ở trong folder users vào và sử dụng
    module.exports để export tất cả cả router này ra để sử dụng trong
    Manager.js của routes

    2 run coder helper
    ApiUser....
    ...
    ```

*  `30 Vào folder auth và tạo 2 file`

    ```bash
    1 Login.js

    2 Logout.js
    ```
*  `31 Trong folder users tạo file `

    ```bash
    1 Register.js

    **Thử chạy vào file Api.User.js và xài cmd+left chuột test đúng đường dẫn là okey
    ```

## `IV Chuẩn bị các file end_point `
    
* `32`
    ```bash
    1 Copy từ file index.js lên hoặc tự gõ syntax

    2 Trong client-web tạo file Navigation.js và chạy code helper navigation....

    2 Chuẩn bị UI 
    ```

    
    










    
  


