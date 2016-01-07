# virtual-joystick-android

_I created this library as a learning process and I have been inspired by this project [JoystickView](https://github.com/zerokol/JoystickView) (the author is a genius!)_

This library provides a very simple and **ready-to-use** custom view which emulates a joystick for Android.

![Alt text](/misc/ss_mobile_landscape_joystick.png?raw=true "Double Joystick with custom size and colors")

### Gist
Here is a very simple snippets to use it. Just set the `onJoystickListener` to retrieve its angle and strength.

```java
@Override
protected void onCreate(Bundle savedInstanceState) {
    super.onCreate(savedInstanceState);
    setContentView(R.layout.activity_main);

    ...

    JoystickView joystick = (JoystickView) findViewById(R.id.joystickView);
    joystick.setOnJoystickListener(new JoystickView.OnJoystickListener() {
        @Override
        public void onMove(int angle, int strength) {
            // do whatever you want
        }
    });
}
```
The **angle** follow the rules of a simple **counter-clock** protractor. The **strength is percentage** of how far the button is **from the center to the border**.

![Alt text](/misc/virtual-joystick.png?raw=true "Explanation")

By default the **refresh rate** to get the data is **20/sec (every 50ms)**. If you want more or less just set the listener with one more parameters to set the refresh rate in milliseconds.
```java
joystick.setOnJoystickListener(new JoystickView.OnJoystickListener() { ... }, 17); // around 60/sec
```

### Attributes

You can customize the joystick according to these attributes `buttonColor`, `borderColor`, `backgroundColor` and `borderWidth`

Here is an example for your layout resources
```xml
<io.github.controlwear.virtual.joystick.android.JoystickView
    xmlns:custom="http://schemas.android.com/apk/res-auto"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content"
    custom:buttonColor="#FF0000"
    custom:borderColor="#0000FF"
    custom:backgroundColor="#11000000"
    custom:borderWidth="4dp"/>
```

## Samples
- [Control Wear](https://github.com/controlwear/cw-app-android) is a very simple universal controller (app and library) which implement this virtual joystick on smartwatch.

## Download
### Gradle
```java
compile 'io.github.controlwear:virtualjoystick:0.9.5'
```

## Contributing
If you would like to contribute code, you can do so through GitHub by forking the repository and sending a pull request.
When submitting code, please make every effort to follow existing conventions and style in order to keep the code as readable as possible.

## License
```
Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

## About 44screens
![alt tag](http://www.44screens.com/fr/wp-content/uploads/2014/09/logo_44screens_cmyk-Converted.png "44screens")

**virtual-joystick-android** is an open source project created by Damien Brun (spare time) and partially funded by [44screens](http://www.44screens.com).
44screens is a lovely start-up specialized in augmented reality, mobile and wearable apps.
