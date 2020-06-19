# Unity-Flutter-echoAR-example
Starter project to build Android apps using Flutter &amp; Unity with echoAR
## Register
Make sure you have an echoAR API key. If you don't have one yet, register for FREE at [echoAR](https://console.echoar.xyz/#/auth/register).
## Setup
* [Add a 3D model](https://docs.echoar.xyz/quickstart/add-a-3d-model) to the console.
* Create a new Unity project.
* [Install the echoAR Unity SDK](https://docs.echoar.xyz/unity/installation).
* Open the sample scence under `echoAR/Examples/sample.unity`.
* [Set the API key](https://docs.echoar.xyz/unity/using-the-sdk) in the Inspector of the echoAR game object.
## Unity project build settings
#### Android
* Open the Build Settings window by clicking **File > Build Settings...**.
* Select Android and click Switch Platform.
* Check **Export Project**
* Open the Player Settings window by clicking **Player Settings...**
* Configure the folowing:
  - Other Settings > Rendering > Graphics APIs: **OpenGLES3**
  - Other Settings > Configuration > Scripting Backends: **IL2CPP**
  - Other Settings > Configuration > Target Architectures: **✔ ARMv7, ✔ ARM64**
* Notice what is your Minimum API Level. You may need it later.
* Close the Player Settings window
* Click **Add Open Scenes**
* Click **Export** and save as unityExport
#### iOS
* Open the Build Settings window by clicking **File > Build Settings...**.
* Select iOS and click Switch Platform.
* Click **Add Open Scenes**
* Click **Export** and save as unityProject



## Flutter configuration
* Import the project dependecies by running `flutter pub get` from your terminal
#### Android
* Copy your **unityExport** folder to `<your_flutter_project>/android/unityExport`
* Run `flutter pub run flutter_unity:unity_export_transmogrify` in your terminal
* Open `<your_flutter_project>/android/app/build.gradle` and make sure your project minSdkVersion equals to the one you defined for your Unity Project as Minimum API Level.
* Open `<your_flutter_project>/android/build.gradle` and, inside `allprojects { repositories {} }`, add the following:
  ```
  flatDir {
      dirs "${project(':unityExport').projectDir}/libs"
  }
  ```
  so it will look something like this:
  ```
          allprojects {
      repositories {
          google()
          jcenter()
          flatDir {
              dirs "${project(':unityExport').projectDir}/libs"
                  }
              }
          }
  ```
* Open  `<your_flutter_project>/android/settings.gradle` and add the following at the end of the file:`include ':unityExport'`
#### iOS
* Copy your **UnityProject** folder to `<your_flutter_project>/iOS/UnityProject`
* Open `<your_flutter_project>/iOS/Runner.xcworkspace` in Xcode
* Go to **File > Add Files to "Runner"**, and add `<your_flutter_project>/ios/UnityProject/Unity-iPhone.xcodeproj`
* Select `Unity-iPhone/Data`, and, in the Inspectors pane, set the Target Membership to *UnityFramework*
* Select `Unity-iPhone`, select PROJECT : Unity-iPhone, and, in the Build Settings tab, configure the following:
  - Build Options > Enable Bitcode: **No**
  - Linking > Other Linker Flags: **-Wl,-U,_FlutterUnityPluginOnMessage**
* Select **Runner**, select **TARGETS : Runner**, and, in the General tab, configure the following:
  - Frameworks, Libraries, and Embedded Content: **UnityFramework.framework	-> Embed & Sign**
* Open `Runner/Runner/Info.plist`, and configure the following:
<table>
  <thead>
    <tr>
      <th>Key
      </th>
      <th>Type
      </th>
      <th>Value
      </th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>io.flutter.embedded_views_preview
      </td>
      <td>Boolean
      </td>
      <td>YES
      </td>
    </tr>
  </tbody>
</table>

## Run
* Open your `main.dart` file
* Find and replace the value `<YOUR-PROJECT-KEY>` with your API key and uncomment the code line
* Find and replace the value `<YOUR-ENTRY-ID>` with your model's entry ID and uncomment the code line
* Save the file and run the project on an andorid phone

## Learn more
Refer to our [documentation](https://docs.echoar.xyz/unity/) to learn more about how to use Unity and echoAR.

This project uses a [third part library](https://pub.dev/packages/flutter_unity#-readme-tab-).

## Support
Feel free to reach out at [support@echoAR.xyz](mailto:support@echoAR.xyz) or join our [support channel on Slack](https://join.slack.com/t/echoar/shared_invite/enQtNTg4NjI5NjM3OTc1LWU1M2M2MTNlNTM3NGY1YTUxYmY3ZDNjNTc3YjA5M2QyNGZiOTgzMjVmZWZmZmFjNGJjYTcxZjhhNzk3YjNhNjE).

## Screenshots
![Flutter with Unity scene screenshot](/images/Flutter%20with%20Unity.jpg)
![echoAR console screenshot](/images/Console.jpg)
