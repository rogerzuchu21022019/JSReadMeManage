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
yarn add  bcrypt mongoose nodemon randombytes dotenv jsonwebtoken joi nodemon redis
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

* `9 tạo file .env run code helper`
```bash
.env.Node...
```
* `8 run nodemon trong package.js`

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

* `8 yarn dev chạy thử`
* `9 connect Redis`
  * `Tạo folder middlewares trong src và tạo file RedisConnection`
  * `Chạy code helper`
```bash
redisConfig.Pattern
```

* `10 vào file server.js trong src/bin/server.js và import vào`
  
```bash
require(`../src/middlewares/RedisConnection`)
```
  * `để ý thấy có thông báo connect là ok`


## `II Part2`

* `11 connect Mongodb`
  * `Tạo folder utils trong src và tạo file MultiConnection.js`
  * `Chạy code helper`

  ```bash
  multiConnection...
  ```


