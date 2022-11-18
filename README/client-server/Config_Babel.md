# Config BabelRc

* `1 Tạo file .babelrc.json`

    ```bash
    run babelrcConfig
    ```
* `2 Add 6 thằng @babel vào package.json dev`

    ```bash
    yarn add @babel/cli @babel/core @babel/node @babel/plugin-proposal-export-default-from @babel/preset-env babel-plugin-root-import -D
    ```

* `3 Config đoạn yarn dev trong package.json: Thêm đoạn --exec babel-node vào giữa`

    ```bash
     "dev": "nodemon --exec babel-node ./bin/server",
    ```
* `4 done`