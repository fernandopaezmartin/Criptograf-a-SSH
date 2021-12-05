
# Video demostrativo 
[![Video demostrativo](https://github.com/fernandopaezmartin/Criptografia_SSH/blob/main/imagenes/thumb_crypto_min.png
)](https://youtu.be/ZPLasmX_eUc)


# Criptografía_SSH
![Imagen Portada Cifrado SSh](https://github.com/fernandopaezmartin/Criptografia_SSH/blob/main/imagenes/ssh_portada.jpg)


SSH o Secure Shell es un protocolo que nos permite gestionar y administrar nuestros equipos de forma remota. Utiliza un sistema criptográfico para asegurarse que todas las comunicaciones entre equipo local y remoto estén cifradas. SSH está disponible en Windows, GNU/Linux y MacOS.

SSH se creó como un reemplazo seguro para Telnet que era sin cifrar y utiliza técnicas criptográficas para garantizar que todas las comunicaciones hacia y desde el servidor remoto sucedan de manera encriptada.

# ¿Cómo funciona SSH?

Un comando de clave SSH indica a un equipo que deseamos abrir una conexión remota cifrada y segura. Dicho comando consta en lo más básico, de tres partes:

`ssh {user}@{host}`

{user} representa la cuenta a la cual deseamos acceder mientras que {host} representa el equipo al cual deseamos ingresar. Este último puede ser representado  por una dirección IP.

Una vez ejecutados estos tres comandos con sus respectivos datos, se nos pedirá que ingresemos las credenciales del usuario al que deseamos ingresar. Si dichas credenciales son correctas, entraremos a la interfaz de SSH.

SSH usa tres tecnologías de cifrado:

1. Cifrado asimétrico
2. Cifrado simétrico
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

Con este método solo se autentica la identidad y por eso es muy importante la gestión de claves ya que si una clave se distribuye erróneamente: entonces se podrá comprometer dicha clave.

# Cifrado simétrico
![Cifrado Simétrico](https://github.com/fernandopaezmartin/Criptografia_SSH/blob/main/imagenes/cifrado-simetrico.jpg)

También llamado cifrado de “secreto compartido” (shared key) o cifrado de “clave secreta”, el cifrado simétrico es una de las formas de encriptación que nos ofrece SSH. Se basa en la utilización de una clave secreta tanto para el cifrado como el descifrado, de modo que usuario y host la necesitarán para descifrar el mensaje.

El cifrado simétrico hace que usuario y host compartan una misma clave para descifrar sus mensajes. En su contra a este tipo de cifrado, cualquier persona que tenga la clave puede cifrar y descifrar los mensajes.

Las claves simétricas se utilizan para cifrar toda la comunicación durante una sesión SSH. El proceso de creación de una clave simétrica se lleva a cabo mediante un algoritmo de intercambio de claves.
El token secreto es específico para cada sesión SSH, y se genera antes de la autenticación del cliente. Una vez generada la clave, todos los paquetes entre las dos máquinas deben ser cifrados por la clave privada. Esto incluye la contraseña escrita en la consola por el usuario, por lo que las credenciales siempre están protegidas en la red.

# Cifrado asimétrico

![Cifrado Asimétrico](https://github.com/fernandopaezmartin/Criptografia_SSH/blob/main/imagenes/cifrado-asimetrico.jpg)

El uso tan extendido del cifrado asimétrico radica en su fortaleza porque con la clave privada se puede obtener la clave pública, pero no al revés. Es por esto que  la clave pública puede distribuirse sin problemas.

Para generar las claves públicas se disponen de tres tipos de cifrado:

- RSA : fue utilizado por primera vez en 1978. La criptografía RSA se basa en la creencia matemática de que factorizar grandes números semiprimos es difícil por naturaleza.
- DSA : es un algoritmo más complejo. Tiene en cuenta un número aleatorio que se utiliza con la firma del mensaje, es decir, va un paso más allá que RSA.
- Curvas elípticas: son ECDSA y EdDSA. Estos algoritmos se basan en el supuesto de que no existe una solución eficiente para resolver un problema de logaritmos discretos, igual que DSA. La diferencia está en que DSA utiliza una operación matemática llamada exponenciación modular y los algoritmos de curvas elípticas usan curvas elípticas. Las curvas elípticas que se han usado entre otras cosas para solucionar el Teorema de Fermat se definen mediante ecuaciones cúbicas (de 3º)


# Hash o Hashing

Otra forma de manipulación de datos que SSH aprovecha es el hash criptográfico. Las funciones hash criptográficas son métodos para crear una “firma” o un resumen de un conjunto de datos.

Sus principales atributos distintivos son que nunca deben invertirse, son virtualmente imposibles de influenciar de manera predecible y son prácticamente únicas.

Usar la misma función de hash y el mensaje debería producir el mismo hash; La modificación de cualquier parte de los datos debe producir un hash completamente diferente.

Un usuario no debe ser capaz de producir el mensaje original de un hash dado, pero debe ser capaz de decir si un mensaje dado, produjo un hash dado.

Así, los hashes se utilizan principalmente para propósitos de integridad de datos y para verificar la autenticidad de la comunicación. Éstos garantizan que el texto del mensaje recibido esté intacto y sin modificar.


