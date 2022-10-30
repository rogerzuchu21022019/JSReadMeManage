



![Logo](https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcTaEZAzoql-TNKAwwk4zBHCS65HlBXqmprnKQ&usqp=CAU)


# Project Title

A brief description of what this project does and who it's for


# Init and Step Project React-native

A brief description of what this project does and who it's for


## Tech Stack

**Client:** React-native, Redux Toolkit, Redux Saga

**Server:** Node, Express


## API Reference

#### Get all items

```http
  GET /api/items
```

| Parameter | Type     | Description                |
| :-------- | :------- | :------------------------- |
| `api_key` | `string` | **Required**. Your API key |

#### Get item

```http
  GET /api/items/${id}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Id of item to fetch |

#### add(num1, num2)

Takes two numbers and returns the sum.

## Color Reference

| Color             | Hex                                                                |
| ----------------- | ------------------------------------------------------------------ |
| Primary Color | ![#0a192f](https://via.placeholder.com/10/0a192f?text=+) #0a192f |
| Secondary Color | ![#f8f8f8](https://via.placeholder.com/10/f8ff8?text=+) #f8f8f8 |
| Thirdary Color | ![#00b48a](https://via.placeholder.com/10/00b48a?text=+) #00b48a |


# Project Title

A brief description of what this project does and who it's for


# Project Title

A brief description of what this project does and who it's for


## Environment Variables

To run this project, you will need to add the following environment variables to your .env file

`API_KEY`

`ANOTHER_API_KEY`


## Features

- Light/dark mode toggle
- Live previews
- Fullscreen mode
- Cross platform


## Demo

Insert gif or link to demo


## Installation

Step 1 :Init project

```bash
  npx react-native init [Your_name_Project]
  open folder [Your_name_Project]
```



Step 2 :Install navigation

* Stack Navigation
```bash
  yarn add @react-navigation/native
  yarn add react-native-screens react-native-safe-area-context
  yarn add @react-navigation/native-stack
  cd ios pod-install ios

  or faster with 
  yarn add @react-navigation/native
  react-native-screens react-native-safe-area-context
  @react-navigation/native-stack
  cd ios pod-install ios
```

Step 3 : Install Tab Navigation
* Tab Navigation
```bash
  yarn add @react-navigation/bottom-tabs
```

Step 4 : Start Simulator, Emulator First


Step 5 :Start Project

```bash
  yarn start 
```


Step 6 : Run-ios,android

```bash
  yarn ios --verbose 
  yarn android --verbose 
```

Step 7 : Prepare Structure App
* Create Folder src => app

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
            
            * SafeAreaCus.js

        * ... another components

    * utils
    * images
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

Step 7 : Prepare SafeAreaPattern
* Create Folder safe_area
* 1 safeAreaPattern

Step 7 : Prepare Screens
* Use Screen Pattern
* 1

Step 8 : Prepare Route Navigation
* Create Folder route
* 1: Create Route.js
* 2: use routerNavPattern

Step 7 : Add Stack config in  file :

* App.js
```bash
  appPattern
  container
```




    