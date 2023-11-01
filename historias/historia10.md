# Historia de usuario de inicio de sesión

Yo: como usuario de la aplicación,
Quiero: iniciar sesión en la aplicación con una cuenta de Google,
Para: poder acceder a las funcionalidades de la aplicación.

## Criterios de aceptación

- El usuario debe poder iniciar sesión con una cuenta de Google existente.
- El usuario debe poder cerrar sesión.

## Análisis y diseño

<img src="../assets/historia10.png" alt="Historia de usuario de inicio de sesión" width="500px" ><br/>

- El usuario debe iniciar sesion con una cuenta de Google existente porque se utilizará 0Auth2 para la autenticación.
- El usuario debe poder cerrar sesión porque es una funcionalidad básica de cualquier aplicación.

#### Descripción de la interfaz de usuario

Esta interfaz permitirá al usuario iniciar sesión con una cuenta de Google existente. Al momento de apretar el botón de inicio de sesión el usuario será redirigido a 0Auth2 para que inicie sesión con su cuenta de Google. Una vez que el usuario inicie sesión, será redirigido a la la página de inicio de la aplicación y podrá acceder a las funcionalidades de la aplicación.