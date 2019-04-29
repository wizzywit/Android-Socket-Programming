# Client-Server Communication app

This APPLICATION have two projects here. it makes use of Socket Programming in android development
to demonstrate communication between different applications on different devices.

## Installation
* Clone this repository and import into two instances of **Android Studio**
  ```bash
   git clone git@github.com:wizzywit/Android-Socket-Programming.git
  ```
### On the server-side project of the **Android Studio**
  * Connect the android device to your PC
  * Click Run
  * Click the Run app
  * Select the connected device you plan to install the app and click enter
  
### On the Client-side project of the **Android Studio**
  * Change the SERVER_IP of the Code snippet bellow to the installed server device
    ```java
    public class MainActivity extends AppCompatActivity {
    //initialize to any specified port between 1024 to 65535
    public static final int SERVER_PORT = ;
    
    //get the IP of the server Device and replace below
    public static final String SERVER_IP = "Replace IP Address here";
    private ClientThread clientThread;
    private Thread thread;
    private LinearLayout msgList;
    private Handler handler;
    private int clientTextColor;
    private EditText edMessage;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        setTitle("Client");
        clientTextColor = ContextCompat.getColor(this, R.color.green);
        handler = new Handler();
        msgList = findViewById(R.id.msgList);
        edMessage = findViewById(R.id.edMessage);
    }
    ```
  * Connect the client android device
  * Click Run
  * Click the Run app
  * Select the connected device you plan to install the app and click enter
  
## Usage
* Connect both device to the same network
* Click on the start server button of the server app
* CLick the connect to server button on the Client-side app 
* You can now send and recieve messages between both apps

## Configuration
### Keystores:
Create `app/keystore.gradle` with the following info:
```gradle
ext.key_alias='...'
ext.key_password='...'
ext.store_password='...'
```
And place both keystores under `app/keystores/` directory:
- `playstore.keystore`
- `stage.keystore`


## Build variants
Use the Android Studio *Build Variants* button to choose between **production** and **staging** flavors combined with debug and release build types


## Generating signed APK
From Android Studio:
1. ***Build*** menu
2. ***Generate Signed APK...***
3. Fill in the keystore information *(you only need to do this once manually and then let Android Studio remember it)*

## Maintainers
This project is mantained by:
* [Wisdom Praise](http://github.com/wizzywit)
* [Diretnan Domnan](http://github.com/deven96)


## Contributing

1. Fork it
2. Create your feature branch (git checkout -b my-new-feature)
3. Commit your changes (git commit -m 'Add some feature')
4. Push your branch (git push origin my-new-feature)
5. Create a new Pull Request
