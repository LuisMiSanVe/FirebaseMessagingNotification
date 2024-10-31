> [See in spanish/Ver en español](https://github.com/LuisMiSanVe/FirebaseMessagingNotification/tree/spanish)
# 📲 Firebase Messaging Notification Service
Server and client apps with the required configurations to use a notification service powered by Firebase Messaging.

## 🛠️ Setup
With all functional apps, you just need to power them with the Firebase Messaging service. So, obviously, you'll need to set up a Firebase project.  
To do so, log in to your Google Account (if you haven't already), enter the [Firebase Console](https://console.firebase.google.com/), and create a new project (recommended) or use an old one.  
Inside your Firebase project, go to Settings (⚙️) and add an Android App. Place the same package name that your app has (this repository example is `com.luismisanve.firebasemessagingnotification`).  
Keep following the steps and ignore any that require you to put code into the app, as all the configuration is already made in the apps here.  
Then, download `google-services.json` and place it right into the `apps` folder in your Android project.  
With that, the client side is fully configured.  

Now, to do the same on the server side, in the same Firebase Settings you were in, change to the 'Service Accounts' tab and click on 'Generate new private key'. This will download a .json file that, by default, the REST API searches for by the name `credentials.json`, so change its name or update it in the REST API's code.  
Lastly, place the .json file in the main root of the project, right where `Program.cs` is.

## 🚀 Project Usage Explanation
Now that both apps are configured, you just need to test the service. There are two ways to do this:

- **From Firebase:**
> [!NOTE]
> This is only for testing; for actual implementation, using the REST API server is recommended.
  
  In Firebase, open the 'Execution' dropdown and search for 'Messaging' (if you don't find it there, go to 'All products') and **Start your first campaign**.  
  In the first steps, when you set the notification's title and text, a Test button will be enabled. If you click it, it will request you for a token.  
  To get it, open the Client App, and as it opens, it copies the generated device token to the clipboard. Just paste it into Firebase and press 'Test'.  
  If the app is in the **background** and has **Notification permissions**, the notification should appear.

- **From the REST API Server:**
  Open both apps, fill in the parameters of the REST API's endpoint, paste the token the Android app saved in your clipboard, and click 'Execute' to send the notification.  
  If the same requirements as above have been fulfilled, your notification should come up.  
  > In the Firebase documentation, it recommends using certain methods to save the device token on the server to automate this process instead of pasting it manually. To do that, replace the code that copies the token to your clipboard with methods that save it on the server.

## 💻 Technologies Used
- Programming Language: C#, Java
- Framework/Template: ASP.NET Core (Project made with .NET 8.0 Framework), Empty Views Activity
- NuGets/Libraries:
  - Swashbuckle.AspNetCore NuGet (6.4.0)
  - FirebaseAdmin SDK NuGet (3.0.1)
  - com.google.gms:google-services (4.4.2)
  - libs.firebase.bom
  - libs.firebase.messaging
- Other:
  - Firebase Messaging
- Recommended IDE: Visual Studio 2022, Android Studio (Koala Feature Drop 2024.1.2)
