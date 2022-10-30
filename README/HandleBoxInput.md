# BoxInputCus

# \*\*\*\* `Note: Tips trong xử lý BoxInput`

- `1 Toán tử {}`

  ```bash
  vd {icon} trong BoxInput
  xử lý {icon} để có thể handle truyền icon từ screen vào component

  ```

- `2 Toán tử 2 ngôi ? data : null`

  ```bash
  const [isValid, setIsValid] = useState(false);
  const [isShowIcon, setIsShowIcon] = useState(false);
  xử lý việc show/hide icon, check data trong screen , input

  const removeIcon = () => {
      setEmail(``);
      setIsShowIcon(false);
      alert('Please enter a email');
      setIsValid(false);
  };

  iconShow={
      isShowIcon === false ? null : (
          <TouchableOpacity onPress={removeIcon}>
              <IconMaterial name="close" size={25} />
          </TouchableOpacity>
      )
  }
  ```

# `1 Tạo ra`

## \* `1 import`

    - `1` Tạo file => run code helper :

        ```bash
        inputPattern ,
        styleInputPattern,
        validation.JS_PatternConfig
        ```

## \* `2 handle UI truớc`

- `1` Check UI BoxInput component

        ```bash
        - style có thể chọn styleBox viết trong đó hoặc
        dùng style trong screen truyền dô

        - style trong
        ```

- `2` Check styleBox
- `3` Check lại các props trong BoxInput component

# `2 Solve`

## `1 handle trong BoxInput`

- Check lại pattern, có từng phần đọc lại và xoá những cái không cần
- Thêm props, xoá props
- props quan trọng là : iconShow,icon để thêm icon từ vector icon
- props quan trọng là : secureTextEntry là biến boolean để check và nhấn chyển sang ẩn / hiện pass

  ```bash
  import React, { useState } from "react";
  import { Image, Text, TextInput, View, TouchableOpacity } from "react-native";
  import styleBox from "./StyleBox";

  const BoxInputCus = (props) => {
  const {
      icon,
      iconShow,
      placeholder,
      value,
      title,
      secureTextEntry,
      onChangeText,
      keyboardType,
      returnKeyType,
      onFocus = () => {},
      isShowIcon,
  } = props;

  return (
      <View style={styleBox.box}>
      <View>
          <Text style={styleBox.title}>{title}</Text>
      </View>
      <View style={styleBox.container}>
          <View>{icon}</View>
          <View style={styleBox.inputSize}>
          <TextInput
              style={styleBox.input}
              placeholder={placeholder}
              value={value}
              onFocus={() => {
              onFocus();
              }}
              onChangeText={onChangeText}
              secureTextEntry={secureTextEntry}
              keyboardType={keyboardType}
              returnKeyType={returnKeyType}
          />
          </View>
          <View style={styleBox.iconShow}>{iconShow}</View>
      </View>
      </View>
  );
  };
  export default BoxInputCus;
  ```

## `2 handle trong screen`

- `1 import`

  ```bash
  import IconMaterial from 'react-native-vector-icons/MaterialCommunityIcons';
  import React, { useState} from 'react';

  ```

- `2 state`

  ```bash
  const [isValid, setIsValid] = useState(false);
  const [isShowPass, setIsShowPass] = useState(false);
  const [email, setEmail] = useState();
  const [password, setPassword] = useState();
  ```

- `3 BoxInput`

```bash
            <BoxInput
              icon={<IconMaterial name="email" size={25} />}
              placeholder="Email"
              value={email}
              keyboardType="email-address"
              returnKeyType="next"
              onChangeText={(text) => {
                setEmail(text);
                isInfoEmpty(text) === false ? showEmpty() : null;
                const isValid = emailValidator(text);
                setIsValid(isValid);
              }}
              iconShow={
                email?.length > 0 === false ? null : (
                  <IconMaterial
                    name="close"
                    size={25}
                    onPress={removeIconEmail}
                  />
                )
              }
            />
            {isValid === false ? (
              <View>
                <Text style={styles.error}>* Email isValid</Text>
              </View>
            ) : null}

            <BoxInput
              icon={<IconMaterial name="lock" size={25} />}
              placeholder="Password"
              value={password}
              keyboardType="default"
              returnKeyType="next"
              secureTextEntry={isShowPass}
              onChangeText={(text) => {
                setPassword(text);
                isInfoEmpty(text) === false ? showEmpty() : null;
              }}
              iconShow={
                password?.length > 0 === false ? null : (
                  <IconMaterial
                    name={isShowPass === true ? 'eye-off' : 'eye'}
                    size={25}
                    onPress={() => setIsShowPass(!isShowPass)}
                  />
                )
              }
            />
            {password?.length > 0 === false ? (
              <View>
                <Text style={styles.error}>* Password isValid</Text>
              </View>
            ) : null}

```
