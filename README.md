# Criptografía_SSH

SSH o Secure Shell es un protocolo que nos permite gestionar y administrar nuestros equipos de forma remota. Utiliza un sistema criptográfico para asegurarse que todas las comunicaciones entre equipo local y remoto estén cifradas. SSH está disponible en Windows, GNU/Linux y MacOS.

SSH se creó como un reemplazo seguro para Telnet que era sin cifrar y utiliza técnicas criptográficas para garantizar que todas las comunicaciones hacia y desde el servidor remoto sucedan de manera encriptada.

# ¿Cómo funciona SSH?

Un comando de clave SSH indica a un equipo que deseamos abrir una conexión remota cifrada y segura. Dicho comando consta en lo más básico, de tres partes:

`ssh {user}@{host}`

{user} representa la cuenta a la cual deseamos acceder mientras que {host} representa el equipo al cual deseamos ingresar. Este último puede ser representado  por una dirección IP.

Una vez ejecutados estos tres comandos con sus respectivos datos, se nos pedirá que ingresemos las credenciales del usuario al que deseamos ingresar. Si dichas credenciales son correctas, entraremos a la interfaz de SSH.

SSH usa tres tecnologías de cifrado:

1. Cifrado simétrico
2. Cifrado asimétrico
3. Hashing

El cifrado simétrico es la forma de cifrado en la que se utiliza una clave secreta tanto para el cifrado como para el descifrado de un mensaje, para las dos partes de la comunicación, el cliente y el host. En contra, el poseedor de la clave puede descifrar todo el mensaje.
