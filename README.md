> [Ver en inglés/See in english](https://github.com/LuisMiSanVe/FirebaseMessagingNotification/tree/main)
# 📲 Servicio de Notificaciones con Firebase Messaging
Aplicaciones de Servidor y Cliente con toda la configuración necesaria para un servicio de notificaciones impulsado por Firebase Messaging.

## 🛠️ Instalación
Con las apps ya configuradas, solo necesitas añadirles el servicio de Firebase Messaging. Por lo tanto, necesitarás un proyecto de Firebase.
Para crearlo, inicia sesión en Google (si no lo habías hecho ya), entra en la [Consola de Firebase](https://console.firebase.google.com/) y crea un nuevo proyecto (recomendado) o usa uno que ya tengas.  
Dentro de tu proyecto, ve a Configuración (⚙️) y agrega la app de Android. Ponle el mismo nombre de paquete que tiene la app (si usas la de este repositorio, es `com.luismisanve.firebasemessagingnotification`).  
Sigue los pasos e ignora los que piden añadir líneas de código, ya que todo eso ya está configurado.
Luego, descarga `google-services.json` y ponlo dentro de la carpeta [apps](https://github.com/LuisMiSanVe/FirebaseMessagingNotification/tree/main/FirebaseMessagingNotification/app) de tu proyecto de Android.  
Con eso, la app del Cliente ya está vinculada.

Ahora, para hacer lo mismo con el Servidor, en la misma pantalla de Configuración de Firebase, cambia a la pestaña de "Cuentas de servicio" y haz clic en "Generar nueva clave privada". Esto descargará un archivo .json que, por defecto, la REST API del Servidor busca con el nombre `credentials.json`, por lo que debes cambiar el nombre del archivo o el código de la REST API para que coincidan.  
Para finalizar, coloca el .json en la ruta principal del proyecto del Servidor, justo donde está [Program.cs](https://github.com/LuisMiSanVe/FirebaseMessagingNotification/tree/main/FirebaseMessagingNotificationServer).

## 🚀 Cómo usar el proyecto
Ahora que todo está configurado, solo queda probar que funciona el servicio. Esto se puede hacer de dos formas:

- **Desde Firebase:**
> [!NOTE]
> Esto es solo para pruebas; para una implementación real, se recomienda hacerlo desde la REST API del Servidor.

  En Firebase, abre el desplegable "Ejecución" y busca "Messaging" (Si no lo encuentras, ve a "Todos los productos") y **Crea la primera campaña**.  
  En los primeros pasos, cuando añadas el título y el texto de la notificación, se activará el botón "Enviar mensaje de prueba". Si le haces clic, te pedirá que ingreses un token.  
  Para conseguirlo, abre la app del Cliente; al iniciarse, copiará automáticamente al portapapeles el token del dispositivo generado. Pégalo en Firebase y haz clic en "Probar".  
  Si la aplicación está en **segundo plano o cerrada** y tiene **permisos de notificaciones**, debería recibir la notificación.

- **Desde la REST API del Servidor:**
  Abre ambas aplicaciones, rellena los parámetros del endpoint de la REST API, pega el token que la app del Cliente guarda en el portapapeles y haz clic en "Execute" para enviar la notificación.  
  Mientras se cumplan los requisitos mencionados anteriormente, la notificación debería aparecer.  
  > En la documentación de Firebase, se recomienda usar métodos para guardar el token del dispositivo en el servidor para automatizar el proceso, en lugar de copiarlo y pegarlo manualmente. Para esto, reemplaza en el Cliente el código que guarda el token en el portapapeles con métodos que lo guarden en el servidor.

## 💻 Tecnologías usadas
- Lenguajes de programación: C#, Java
- Framework/Plantilla: ASP.NET Core (Creado con .NET 8.0), Empty Views Activity
- NuGets/Librerías:
  - Swashbuckle.AspNetCore NuGet (6.4.0)
  - FirebaseAdmin SDK NuGet (3.0.1)
  - com.google.gms:google-services (4.4.2)
  - libs.firebase.bom
  - libs.firebase.messaging
- Otros:
  - Firebase Messaging
- IDE Recomendado: Visual Studio 2022, Android Studio (Koala Feature Drop 2024.1.2)
