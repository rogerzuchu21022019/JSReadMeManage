* Tác dụng

    * Lưu Local

    * Nhanh hơn Storage
* Solve

    * `1 import` 

        ```bash
        yarn add redux-persist
        ```
    * `2 add combineReducers`

        * Cần sử dụng thằng `persistReducer` để thay chỗ cho mấy cái ở trong combineReducers. Cần 2 tham số 
            ```bash
            persisConfig
            rootReducer
            ```

        * `1` Quăng hết reducers trong configStore vào trong này

            ```bash
            const rootReducers = combineReducers({
                login: LoginSliceReducer,
                logout: LogoutSliceReducer,
                articles: ArticlesSliceReducer,
                search: SearchSliceReducer,
                register: RegisterSliceReducer,
                my_article: ArticleSliceReducer,
                update: UpdateInfoSliceReducer,
            });
            ```

         * `2 Add persistConfig`

            * `blacklist` dạng array kiểu chuỗi, chứa những reducer trong rootRudercers mà mình ko muốn lưu xuống persist
            * `whitelist` chưa biết

            ```bash
            import AsyncStorage from '@react-native-async-storage/async-storage';

            let persistConfig = {
                key: 'root',
                storage: AsyncStorage,
                whiteList : [],
                blacklist: ['register','update'],
            };
            ```

        * `3 Gom 2 thằng kia lại rồi quăng vô reducers trong configStore`
        
            ```bash
            import persistReducer from 'redux-persist/es/persistReducer';

            let persistReducers = persistReducer(persistConfig, rootReducers);

            export const Store = configureStore({
            reducer: persistReducers,
            middleware: middleware,
            });
            ```
    
    * 3 `qua file App.js config`

        * `1 import`

        ```bash
        import persistStore from 'redux-persist/es/persistStore';
        import {PersistGate} from 'redux-persist/integration/react';
        let persistor = persistStore(Store);
        ```

        * `2 Sau thẻ Provider bỏ thằng PersistGate vô có 2 thuộc tính mặc định`

            ```bash
             <Provider store={Store}>
                <PersistGate loading={null} persistor={persistor}>

                    Trong này vẫn chứa Navigation bt

                 </PersistGate>
            </Provider>
            ```