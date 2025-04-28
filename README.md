# 2025-1 AprendeMath - Grupo 4 ✏️📚 

La aplicación AprendeMath está diseñada para ayudar a los usuarios a aprender matemáticas de manera sencilla y efectiva. A través de lecciones interactivas, ejercicios dinámicos y desafíos adaptados al nivel de cada estudiante, AprendeMath convierte el estudio de las matemáticas en una experiencia accesible y motivadora.

La plataforma integra módulos de práctica 📈, evaluaciones automáticas 🧠, y recursos de apoyo visual 🖼️, permitiendo a los usuarios consolidar conceptos clave de forma práctica y divertida. Además, cuenta con un sistema de retroalimentación instantánea para reforzar el aprendizaje en tiempo real.


# Guía de Desarrollo para la Aplicación AprendeMath
# 🚀 Breve Descripción del Entorno de Desarrollo 💻
El entorno de desarrollo para la aplicación AprendeMath está construido sobre Flutter, una tecnología de desarrollo multiplataforma que permite crear aplicaciones móviles de alto rendimiento para iOS y Android. Además, Android Studio se utiliza para gestionar emuladores, entornos de desarrollo y los SDKs necesarios para la ejecución en dispositivos Android.

> Flutter: [Sitio oficial de Flutter](https://flutter.dev)  
> Android Studio: [Sitio oficial de Android Studio](https://developer.android.com/studio)

# 🛠️ Descarga e Instalación de Android Studio
Para comenzar a desarrollar con Android Studio, sigue estos pasos:

Visita el sitio oficial de Android Studio en: developer.android.com/studio

Descarga el instalador correspondiente a tu sistema operativo (Windows, macOS o Linux).

Ejecuta el instalador y sigue las instrucciones del asistente:

Asegúrate de instalar también el Android SDK y el Android Virtual Device (AVD Manager).

Finalizada la instalación, abre Android Studio y configura el SDK si el asistente lo solicita.

# 📂 Ejemplo de ruta recomendada para el SDK:

> Windows: C:\Android\Sdk\

> macOS/Linux: /Users/tuusuario/Library/Android/sdk/

⚠️ Importante: Evita instalar Android Studio en carpetas con espacios en el nombre, como C:\Program Files\, para prevenir problemas de permisos y ejecución de emuladores.

# 📥 Descarga e Instalación del SDK de Flutter
Para comenzar con Flutter, sigue estos pasos:

Visita el sitio oficial de Flutter en flutter.dev y descarga el archivo ZIP del SDK correspondiente a tu sistema operativo.
Descomprime el archivo en una ubicación sin espacios o caracteres especiales en la ruta.
Ejemplo de ruta recomendada: `C:\flutter\` o `/usr/local/flutter/`.
⚠️ Importante: Evita descomprimir Flutter en directorios como `C:\Program Files\` debido a posibles restricciones de permisos.

# 🛠️ Configuración de Variables de Entorno
Después de instalar Flutter, es necesario configurar las variables de entorno para que el sistema pueda reconocer los comandos de Flutter.

Abre las Propiedades del Sistema:
Ve a Panel de control > Sistema y seguridad > Sistema > Configuración avanzada del sistema.
En la ventana emergente, selecciona Variables de entorno.
Dentro de Variables del sistema, localiza la variable Path y selecciona Editar.
Agrega una nueva entrada con la ruta completa hacia la carpeta flutter/bin (donde descomprimiste Flutter).
Ejemplo: `C:\flutter\bin\` o `/usr/local/flutter/bin`.
💡 Consejo: Asegúrate de que el comando `flutter` esté disponible en tu terminal ejecutando `flutter --version`.

# ✅ Verificación de la Instalación de Flutter
Para asegurarte de que todo está configurado correctamente:

Abre una ventana de Símbolo del sistema, PowerShell o una terminal en tu sistema operativo.

Ejecuta el siguiente comando:

flutter doctor

## Configuración del Ambiente de Desarrollo
![img01](imgs/android.jpg)

*Figura 1: Instalacion de Android Studio*



# Diagrama de Despliegue:

Nuestro Diagrama de despliegue muestra una arquitectura distribuida en donde el usuario interactua en una app movil (AprendeMath) que sera en diapositivos Android, donde se ejecutara un protocolo HTTPS, con un servicio de  con un servicio backend desplegado en Azure App Service, que procesa las solicitudes y ejecuta la lógica de negocio. A su vez, el backend consulta y almacena la información en una base de datos Azure SQL Database denominada "dataPrograMovil", mediante conexiones internas seguras dentro de la nube de Azure. 

![Android Studio](https://www.plantuml.com/plantuml/png/ZPE_ZjD04CRxVOfHA8uhJg0hKb2Wov-BG28YuD2bcTWJtoZh7Mjt7JXG2YHw2f2WeqIKw1hwl0al08_0s76YImGIAsKKx-pyvfjljHSXeezLOSq93CGjEAyyfhovSP0HK8Xi1N9ovD6Qi6HNeiS2KYbASUHY4gyjWQSqeiijtJhYH05l3EZgOxhClLGk6uWL3tSkkwFxezus9puZt-wV3xlzNjUiRs5K7IymZVz2ZPhrdoWlBm_Inydf5QTBHo70kJ6HeuusPCmrZxKTGmgbPSehWZFewT-qjMgykLcnXKwlzEGo6cEywXXpeWKBTbn80Ai_TKI2QNpf33cK4ZZoIfHiuKMeqBF0xoyVli_StPxBl71sZvycfnt008NCsUxyt7kY3Sks-SmTD5yRargfCZtokl84W-RZv-UtltwyRu2esplULb92ViMP-CPZ9QcC6jziftIgqZv-RKhdstnRV2HeyXYUNoRJHQMAjgLSJxY3me5AqBLkOXCoZ3Z7e5hw6Xl7CKgOkUqCoRCdC6oFg9fFxzfPzdL_LLGd9rvoZsDHdtPDrqVtevXK7BrY3S6qTf-TFTnF-q3VHr6v_Pq_caudYNgKKFrau1h8fPxBY1cUcbsH0lRg6e8BbOqOwbbgVo5wN6s-XNfMJncmY-GTGgYXohbGY3xEFm00)



*<b>Figura 2:</b> Diagrama de Despliegue*



# Requerimientos No funcionales:
Los requerimientos no funcionales definen las características de calidad que debe cumplir el aplicativo móvil AprendeMath para garantizar su correcto funcionamiento durante el desarrollo y evaluación académica.

- **Seguridad:**  
  Toda comunicación entre el móvil y el backend deben realizarse mediante el protocolo **HTTPS** garantizando la integridad y confidencialidad de los datos. Las credenciales del usuario, especialmente las contraseñas, serán cifradas. Adicionalmente se implementarán sistemas de autenticación y validación entre sesiones.

- **Rendimiento:**  
  El tiempo de respuesta de operaciones críticas (**inicio de sesión**, **carga de módulos**, **respuestas a cuestionarios**) no debe exceder los **5 segundos** bajo condiciones normales de conectividad. Asimismo, el tiempo de renderizado de las vistas principales no debe exceder **2 segundos** desde la interacción del usuario.


- **Disponibilidad:**  
  La aplicación debe garantizar una disponibilidad de al menos **99%** durante periodos normales. En caso de fallos, se debe tener la opción de realizar **reinicios manuales** en el backend para minimizar el tiempo de inactividad.

- **Usabilidad:**  
  El proceso de registro de un nuevo usuario será intuitivo, completándose en menos de **3 minutos**. Un usuario nuevo debe ser capaz de iniciar y completar su primer cuestionario en menos de **6 minutos** desde el momento de la instalación sin necesidad de asistencia externa. La navegación será fluida y con retroalimentación clara en todas las acciones.

- **Compatibilidad:**  
  La aplicación funcionará en dispositivos móviles con sistema operativo **Android 8.0** o superior. Se adaptará a dispositivos de **5 a 10 pulgadas**, procurando que no haya pérdidas en contenido o errores de diseño visual.

- **Recuperación ante errores:**  
  En caso de fallas en la conexión, la aplicación debe notificar al usuario mediante mensajes amigables e intentar reintentos automáticos de reconexión. En caso de fallas en servidores, se insistirán estos reinicios.

- **Mantenibilidad:**  
  El código fuente de la aplicación debe seguir principios de desarrollo limpio, modular y documentado, permitiendo actualizaciones rápidas y seguras.


# Diagrama de Casos de Uso:

![img02](imgs/image.png)

*<b>Figura 3:</b> Diagrama de Casos de Uso*
# Descripción de Casos de Uso:
### 1.**Iniciar Sesión**
El usuario ingresa su nombre de usuario y contraseña previamente registrados. El sistema valida las credenciales y, en caso de ser correctas, permite el acceso al menú principal de la aplicación.
<br><br>
![img04](imgs/inicial.jpeg)
![img05](imgs/login.jpeg)
### 2.**Registrar**
El usuario proporciona su información personal (nombre de usuario, correo electrónico, contraseña, edad, género). La aplicación verifica que los datos sean válidos y únicos (sin correos repetidos) antes de crear la nueva cuenta.
<br><br>
![img06](imgs/login.jpeg)
![img07](imgs/registro.jpeg)
### 3.**Recuperar Contraseña**
Si el usuario olvida su contraseña, puede solicitar un enlace de recuperación enviado a su correo registrado. Una vez recibido, podrá restablecer su contraseña y volver a acceder normalmente.
<br><br>
![img08](imgs/login.jpeg)
![img09](imgs/recuperar_contraseña.jpeg)
### 4.**Consultar Niveles:**
El usuario accede a un listado de niveles disponibles dentro del módulo de aprendizaje. Puede visualizar tanto los niveles desbloqueados como los completados, y seleccionar uno para comenzar.
<br><br>
![img10](imgs/Principal.jpeg)
![img11](imgs/start_nivel.jpeg)
### 5.**Cambiar Módulos:**
Permite al usuario cambiar entre distintos módulos temáticos de diferentes temas. Solo podrá acceder a módulos que haya desbloqueado previamente cumpliendo los requisitos necesarios.
<br><br>
![img12](imgs/Principal.jpeg)
![img13](imgs/cambiar_modulos.jpeg)
### 6.**Responder Cuestionario:**
Dentro de un nivel o módulo, el usuario responde una serie de preguntas o ejercicios interactivos. Al finalizar cada respuesta, recibe retroalimentación inmediata sobre si fue correcta o incorrecta.
<br><br>
![img14](imgs/quiz.jpeg)
![img15](imgs/quiz_correcto.jpeg)
![img16](imgs/quiz_incorrecto.jpeg)
![img17](imgs/quiz_final.jpeg)
### 7.**Avanzar Etapa:**
Permite al usuario avanzar a una sección o modulo bloqueado desarrollando exitosamente un examen en base a la sección o módulo seleccionado.
<br><br>
![img18](imgs/Principal.jpeg)
![img19](imgs/cambiar_modulos.jpeg)
![img20](imgs/examen.jpeg)
### 8.**Actualizar Datos:**
Desde la sección de perfil, el usuario puede modificar su información personal, como el nombre de usuario, correo electrónico o foto de perfil. Los cambios son guardados en la base de datos de manera segura.
<br><br>
![img21](imgs/perfil.jpeg)
![img22](imgs/editar_usuario.jpeg)
### 9.**Cerrar Sesión:** 
El usuario puede finalizar su sesión actual cerrando su cuenta en el dispositivo. Esto ayuda a proteger su información en caso de usar un dispositivo compartido o público.
<br><br>
![img23](imgs/perfil.jpeg)
![img24](imgs/cerrar_sesión.jpeg)
### 10.**Consultar Medallas:**
El usuario accede a una sección donde puede visualizar las medallas o insignias que ha ganado gracias a su desempeño, participación y logros dentro de la plataforma.
<br><br>
![img25](imgs/insignias.jpeg)
![img26](imgs/ver_insignia.jpeg)



