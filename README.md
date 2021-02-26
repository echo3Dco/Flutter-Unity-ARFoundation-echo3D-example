# Unity-Flutter-echoAR-example
Starter project to build Android apps using Flutter &amp; Unity with echoAR
## Register
Make sure you have an echoAR API key. If you don't have one yet, register for FREE at [echoAR](https://console.echoar.xyz/#/auth/register).
## Setup
1. Create a new flutter app or clone this repo.
2. [Add a 3D model](https://docs.echoar.xyz/quickstart/add-a-3d-model) to the echoAR console.
3. In your flutter project folder, create a new Unity project or clone our [Unity-ARFoundation-echoAR-example](https://github.com/echoARxyz/Unity-ARFoundation-echoAR-example) and jump to step 6.
4. [Install the echoAR Unity SDK](https://docs.echoar.xyz/unity/installation).
5. Open the sample scence under `echoAR/Examples/sample.unity`.
6. [Set the API key](https://docs.echoar.xyz/unity/using-the-sdk) in the Inspector of the echoAR game object.
## Flutter configuration
* Import the project dependecies by running `flutter pub get` from your terminal
## Unity project build settings
* Follow the instructions for the [flutter_unity](https://pub.dev/packages/flutter_unity#-readme-tab-) plugin
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
