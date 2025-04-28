# 2025-1 Programación Movil - Quiz
Este aplicativo móv- [Configuración del Ambiente de Desarrollo](#configuración-del-ambiente-de-desarrollo)
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
  La aplicación debe utilizar el protocolo **HTTPS** para todas las comunicaciones. Las contraseñas deben almacenarse aplicando cifrado básico para evitar su almacenamiento en texto plano.

- **Rendimiento:**  
  El tiempo de respuesta para las principales acciones (**inicio de sesión**, **carga de módulos**, **confirmación de respuestas**) no debe exceder los **7 segundos** bajo condiciones normales de uso.

- **Disponibilidad:**  
  La aplicación debe estar disponible de manera continua, permitiendo **reinicios manuales** en caso de fallas técnicas.

- **Usabilidad:**  
  El proceso de **registro** de un nuevo usuario debe completarse en un tiempo máximo de **3 minutos**, y el usuario debe poder iniciar su primer **quiz** en menos de **6 minutos** sin necesidad de asistencia.

- **Compatibilidad:**  
  La aplicación debe ser compatible con dispositivos Android que utilicen la versión **8.0 (Oreo)** o superior, y adaptarse correctamente a diferentes tipos de pantallas entre **5 y 10 pulgadas**.

- **Recuperación ante errores:**  
  En caso de **errores de conexión** o **fallos de servidor**, la aplicación debe notificar al usuario e intentar restablecer la acción de manera sencilla.



# Diagrama de Casos de Uso:

![img02](imgs/Diagrama%20de%20Casos%20de%20Uso.jpg)

*<b>Figura 3:</b> Diagrama de Casos de Uso*
# Descripción de Casos de Uso:
### 1.**Iniciar Sesión**
Permite al usuario autenticarse ingresando sus credenciales para acceder a su cuenta.
<br><br>
![img04](imgs/inicial.jpeg)
![img05](imgs/login.jpeg)
### 2.**Registrar**
Permite al usuario crear un nuevo registro proporcionando sus datos personales y de acceso.
<br><br>
![img06](imgs/login.jpeg)
![img07](imgs/registro.jpeg)
### 3.**Recuperar Contraseña**
Permite al usuario recuperar el acceso a su cuenta mediante un correo de restablecimiento de contraseña.
<br><br>
![img08](imgs/login.jpeg)
![img09](imgs/recuperar_contraseña.jpeg)
### 3.**Consultar Niveles:**
Permite al usuario ver los niveles o secciones superadas dentro de la aplicación educativa y poder inciar los diferentes niveles en la sección.
<br><br>
![img10](imgs/Principal.jpeg)
![img11](imgs/start_nivel.jpeg)
### 4.**Cambiar Módulos:**
Permite al usuario seleccionar entre diferentes módulos de aprendizaje solo si los tienes debloqueados.
<br><br>
![img12](imgs/Principal.jpeg)
![img13](imgs/cambiar_modulos.jpeg)
### 5.**Responder Cuestionario:**
Permite al usuario seleccionar una respuesta dentro de las evaluaciones o cuestionarios y enviar su respuesta seleccionada y recibir retroalimentación sobre su validez.
<br><br>
![img14](imgs/quiz.jpeg)
![img15](imgs/quiz_correcto.jpeg)
![img16](imgs/quiz_incorrecto.jpeg)
![img17](imgs/quiz_final.jpeg)
### 6.**Avanzar Etapa:**
Permite al usuario avanzar a una sección o modulo bloqueado desarrollando un examen en base a la sección o módulo seleccionado.
<br><br>
![img18](imgs/Principal.jpeg)
![img19](imgs/cambiar_modulos.jpeg)
![img20](imgs/examen.jpeg)
### 6.**Actualizar Datos:**
Permite al usuario modificar sus datos de perfil, como nombre, correo electrónico o foto.
<br><br>
![img21](imgs/perfil.jpeg)
![img22](imgs/editar_usuario.jpeg)
### 7.**Cerrar Sesión:** 
Permite al usuario salir de su cuenta de forma segura, cerrando su sesión actual.
<br><br>
![img23](imgs/perfil.jpeg)
![img24](imgs/cerrar_sesión.jpeg)
### 8.**Consultar Medallas:**
Permite al usuario visualizar las medallas obtenidas por su rendimiento y logros alcanzados.
<br><br>
![img25](imgs/insignias.jpeg)
![img26](imgs/ver_insignia.jpeg)



