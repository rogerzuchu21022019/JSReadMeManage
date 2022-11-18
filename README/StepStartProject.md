# Step

## `I Init And Embed Navigation`

* `1 :Init project`

    ```bash
    npx react-native init [Your_name_Project]
    open folder [Your_name_Project]
    ```
* `2 Add Library`

    ```bash
    yarn add @react-navigation/native react-native-screens react-native-safe-area-context @react-navigation/native-stack @reduxjs/toolkit @shopify/flash-list react-native-fast-image react-native-vector-icons react-redux redux-persist redux-saga redux-logger react-native-logs @react-navigation/bottom-tabs react-native-image-crop-picker axios@0.25 @react-native-community/hooks
    ```

    * `cd ios pod-install `
* `3 Start Simulator, Emulator First`

* `4 Start Project`

    ```bash
    yarn start 
    ```
* `5 Run-ios,android`

* `6 Prepare Structure App`

    * `Create Folder src => folder app`

    * `Trong app`

        * api
            * BaseUrl.js
            * AxiosInstance.js
        * app_store

            * Store.js
            * Root.Saga.js

        * components
            * input

                * InputCus.js
                * StyleInput.js
            * button

                * ButtonCus.js
                * StyleButton.js
            * safe_area
                
                * SafeKeyComponent.js

            * ... another components
        * features
            * user
                
                * login

                    * state
                    * views
                
                * ... another features of user
            * feature1 

                * list

                    * state
                    * views

                * ... another features of feature1 
        
        * images
        * navigation
            * user
            * product
                * Container.js
            * RootNavigation.js
            * Router.js
        * utils
            * Color.js
            * Validate.js
            * Fonts.js
            * Camera.js

* `7 Trong SafeAreaKey run code helper safaPattern `

* `8 Vào App.js bọc View đó lại bằng SafeKeyComponent `

* `9 Tạo file logger.config.js run code helper logPattern`

* `10 Setup Vector Icon`

    * `1 Trong Info.plist IOS copy cái này dô trước thẻ đóng dict`
    ```bash
    <key>UIAppFonts</key>
    <array>
    <string>AntDesign.ttf</string>
    <string>Entypo.ttf</string>
    <string>EvilIcons.ttf</string>
    <string>Feather.ttf</string>
    <string>FontAwesome.ttf</string>
    <string>FontAwesome5_Brands.ttf</string>
    <string>FontAwesome5_Regular.ttf</string>
    <string>FontAwesome5_Solid.ttf</string>
    <string>Foundation.ttf</string>
    <string>Ionicons.ttf</string>
    <string>MaterialIcons.ttf</string>
    <string>MaterialCommunityIcons.ttf</string>
    <string>SimpleLineIcons.ttf</string>
    <string>Octicons.ttf</string>
    <string>Zocial.ttf</string>
    <string>Fontisto.ttf</string>
    </array>
    ```

    * `2 Gỡ app ios chạy lại yarn ios`

    * `3 Vô android/app/build.gradle past thằng này vào `
    ```bash
    apply from: "../../node_modules/react-native-vector-icons/fonts.gradle"
    ```

    * `4 Để dưới dòng enablesHelmes = true`

    ```bash
    project.ext.react = [
    enableHermes: true,  // clean and rebuild if changing
    ```

    * `4 import 1 cái text input dô chạy thử`

    ```bash
    import IconAnt from 'react-native-vector-icons/AntDesign';
    <IconAnt name="check" size={25} />;
    ```
