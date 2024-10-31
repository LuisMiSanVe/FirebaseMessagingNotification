# 📲 Firebase Messaging Notification Service
Server and Client apps with the required configurations to use a notification service powered by Firebase Messaging.
## 🛠️ Setup
With the all functional apps, you just need to power them with the Firebase Messaging service, so, obviously, you'll need to setup a Firebase project.\
To do so, log in your Google Account (if you already haven't), enter to the [Firebase Console](https://console.firebase.google.com/) and create a new project (recomended) or use and old one.\
Inside your Firebase project, go to Settings (⚙️) and Add an Andrtoid App. Place the same package name your App has (this repository example is `com.luismisanve.firebasemessagingnotification
`)\
Keep following the steps and ignore any that implies you to put code into the app, as all the configuration is already made on the apps here.\
Then, download `google-services.json` and place it right into the `apps` folder in your Android project.\
With that, the Client side is fully configured.<br><br>
Now to do so on the Server side, in the same Firebase Setting you were, change to the 'Service Accounts' tab and click on 'Generate new private key'. This will download you a .json file that for default, the REST API searches by the name of `credentials.json`, so change its name or change it on the REST API's code.\
Lastly place the .json file into the main root of the project, right where `Program.cs` is.
## 🚀 Project Usage Explanation
Now that both apps are configured you just need to try the service. There are two ways:
- From Firebase:
In Firebase, open the 'Execution' dropdown and search 'Messaging' (if you don't find it there, go to 'All products') and <b>Start your first campaign</b>.\
On the first steps, when you set the Notification's tittle and text, a Test button will enable. If you click it, it will request you a token.
- From the REST API Server:

## 💻 Technologies used
- Programming Lenguage: C#, Java
- Framework/Template: ASP.NET Core (Project made with .Net 8.0 Framework), Empty Views Activity
- NuGets/Libraries:
  - Swashbuckle.AspNetCore NuGet (6.4.0)
  - FirebaseAdmin SDK NuGet(3.0.1)
  - com.google.gms:google-services (4.4.2)
  - libs.firebase.bom
  - libs.firebase.messaging
- Other:
  - Firebase Messaging
- Recommended IDE: Visual Studio 2022, Android Studio (Koala Feature Drop 2024.1.2)
