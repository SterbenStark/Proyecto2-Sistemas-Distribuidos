# Proyecto2-Sistemas-Distribuidos

#Temas a asignar
* Videos musicales (mp4)

El propósito de este proyecto es crear una aplicación Web que actue como un inventario de contenidos de interés. Cada grupo debe seleccionar un tema para el desarrollo del proyecto.

# Frontend

Se debe desarrollar un front-end utilizando algún ambiente de desarrollo Javascript (Navigo, Angular, React, Vue, etc.) en donde se permita agregar entradas de datos sobre los temas asignados. También, se podrá utilizar cualquier framework CSS.

Dicha aplicación debe permitir crear categorías (o grupos) de elementos, con nombres asignados por el usuario, dentro de las cuales se crearán las entradas de datos (registros). Dependiendo del tema asignado, cada registro contará con contenido binario asociado (pdf, mp3, mp4, etc) que debe ser presentado (reproducido) directamente en la pantalla junto con la información del registro.

![ejemplo](https://distribuidos-una.netlify.app/assets/Proyecto2.5ad99f26.png)

Nótese que la aplicación no debe reproducir el contenido desde el URL sino directamente desde la base de datos.

# Backend

El back-end de la aplicación debe ser desarrollado en MongoDB mediante funciones de Netlify. Este back-end permitirá consultar los datos de las diferentes categorías definidas, así como de cada uno de los registros de datos. Adicionalmente el back-end permitirá crear, actualizar y eliminar categorías y registros.

De cada registro se contará con una serie de campos que definan los datos que se almacenarán en la base de datos. Adicionalmente, cada registro permitirá ingresar un URL de un contenido adjunto. Este URL apuntará a contenido binario (pdf, mp3, mp4, etc.) que debe ser presentado mediante el front-end de la aplicación. Cuando se ingrese un nuevo registro, el sistema debe enviar un mensaje a una cola de RabbitMQ en donde solicitará que dicho contenido se cargue en la base de datos de forma asincrónica.

# Actualización de contenido adjunto

Una cola de RabbitMQ mantendrá la información sobre el contenido externo que debe ser cargado en la base de datos.

Mediante una tarea asincrónica se accederá a los mensajes de dicha cola y de esta forma a los URLs del contenido adjunto. Para cada solicitud se debe recuperar dicho contenido binario y escribirlo directamente en la base de datos Mongo. Dicha tarea será implementada también como una función de Netlify y se deberá ejecutar cada media hora. Note que no se debe confirmar un mensaje específico de la cola hasta que la solicitud individual no haya sido concluida.

Se debe investigar cómo guardar contenido binario (mp3, mp4, pdf, etc) en la base de datos Mongo. Puede asumir que dicho contenido no será mayor a 16MB.

# Datos de prueba

Agregue al menos unos 20 registros de datos a su base de datos (junto con el contenido respectivo) como una forma de probar las diferentes funcionalidades de su aplicación.

# Observaciones

* Aún cuando lo adecuado sería que la aplicación permitiera que diferentes usuarios se autenticaran y mantuvieran su propio conjunto de registros, esta capacidad no se implementará debido a que aún no se estudiado el manejo de autenticación y sesiones en el cliente.
* Este proyecto debe ser desarrollado en grupos de dos estudiantes.
* La aplicación debe quedar ejecutándose en el Web
* Se debe subir a classroom todo el código desarrollado, junto con un archivo readme.md que indique los integrantes del grupo, el tema asignado y el URL en donde queda publicada la aplicación.



