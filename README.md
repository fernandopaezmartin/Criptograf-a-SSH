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

SSH se basa en la Infraestructura de clave pública, conocida por sus siglas en inglés PKI (Public Key Infrastructure) y los algoritmos criptográficos asimétricos más utilizados en el mundo PKI son RSA, DSA, ECDSA y EdDSA.

# Autenticación SSH

Una vez que las máquinas a establecer conexión verifiquen la versión de SSH tienen que negociar una clave simétrica para cifrar toda la conexión.

La clave simétrica para cifrar la conexión no es lo mismo que las claves utilizadas para la autenticación, sino que se genera una clave compartida a través del intercambio de claves.

Para generar la clave compartida se utilizan las claves públicas del cliente y la privada del servidor, de esta forma el cliente ya ha autenticado al servidor.

En cuanto a la autenticación se desarrolla una vez que el canal es confiable, en el punto en el que el cliente ha autenticado al servidor, pero el servidor aún no ha autenticado al cliente

Normalmente se utiliza la autenticación de clave pública y esto implica una clave pública y una privada.
Así cuando la máquina A encripta un mensaje con la clave pública de B, el mensaje sólo lo podrá desencriptar B con su clave privada.
