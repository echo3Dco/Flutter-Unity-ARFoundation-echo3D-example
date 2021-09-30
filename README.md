# Unity-Flutter-echo3D-example
Starter project to build Android apps using Flutter &amp; Unity with echo3D.
## Register
Make sure you have an echo3D API key. If you don't have one yet, register for FREE at [echo3D](https://console.echo3D.co/#/auth/register).
## Setup
1. Create a new flutter app or clone this repo.
2. [Add a 3D model](https://docs.echo3D.co/quickstart/add-a-3d-model) to the echo3D console.
3. In your flutter project folder, create a new Unity project or clone our [Unity-ARFoundation-echo3D-example](https://github.com/echo3Dco/Unity-ARFoundation-echo3D-example) and jump to step 6.
4. [Install the echo3D Unity SDK](https://docs.echo3D.co/unity/installation).
5. Open the sample scence under `echo3D/Examples/sample.unity`.
6. [Set the API key](https://docs.echo3D.co/unity/using-the-sdk) in the Inspector of the echo3D game object.
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
Refer to our [documentation](https://docs.echo3D.co/unity/) to learn more about how to use Unity and echo3D.

This project uses a [third part library](https://pub.dev/packages/flutter_unity#-readme-tab-).

## Support
Feel free to reach out at [support@echo3D.co](mailto:support@echo3D.co) or join our [support channel on Slack](https://go.echo3D.co/join).

## Screenshots
![Flutter with Unity scene screenshot](/images/Flutter%20with%20Unity.jpg)
![echo3D console screenshot](/images/Console.jpg)
