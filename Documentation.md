<div align="center">
 
  ## Cyberdefenders - Insider Lab

</div>

### Introducción

El laboratorio “Insider” de CyberDefenders, simula una investigación de amenaza interna en una máquina Linux, usando técnicas de análisis forense sobre una imagen de disco. El objetivo es analizar el comportamiento de una empleada sospechosa tras un incidente relacionado con acceso y uso indebido de la infraestructura de la organización.​

Este laboratorio permite obtener competencias prácticas en análisis forense, investigación de incidentes internos y manejo de imágenes forenses, altamente valorados. Obteniendo la capacidad para extraer información relevante y conectar piezas de evidencia en contextos realistas de ciberseguridad, como de un caso real se tratase.


<img width="863" height="627" alt="image" src="https://github.com/user-attachments/assets/5ecb2580-96b6-46ab-b706-38c8ab35d0f8" />

Para finalizar este laboratorio, es necesario realizar una labor de investigación y responder a las  cuestiones planteadas. (11)

<img width="866" height="915" alt="image" src="https://github.com/user-attachments/assets/0fbc0d30-a3ac-4c34-8448-154fa7037b89" />
<img width="871" height="1132" alt="image" src="https://github.com/user-attachments/assets/cc5788c5-4d91-4bb8-991d-7332a86331bc" />

---

### Comienzo

Para empezar, hemos necesitado instalar la herramienta FTK Imager en una máquina virtual win11 y descargarnos el archivo proporcionado por CyberDefenders para este labs. Una vez preparado el entorno de trabajo, comenzamos el análisis.

Una vez montada la evidencia, podemos explorar los diferentes archivos y fácilmente responder a la primera pregunta al movernos a la carpeta de /boot/grub/.

Donde nos indica que el SSOO usado es un "Kali".

<img width="870" height="172" alt="image" src="https://github.com/user-attachments/assets/4c2bafaf-d6c4-4dfd-9a2a-58bf19cd15e2" />

Para la segunda pregunta, debemos movernos por las carpetas hasta entrar donde se guardan los logs en Kali, que sería en la carpeta log dentro de var (/var/log/). En esta ubicación, buscamos la carpeta del log que queremos, en este caso Apache y el archivo que nos indica.

Como podemos ver, esta herramienta nos facilita el trabajo al indicarnos el MD5 Hash, en el apartado de propiedades.

<img width="875" height="827" alt="image" src="https://github.com/user-attachments/assets/e186def3-7158-44ec-99e4-43a5558240f5" />
"d41d8cd98f00b204e9800998ecf8427e"

<img width="871" height="175" alt="image" src="https://github.com/user-attachments/assets/944f23a4-fba4-4dd7-bb5f-95433f5bd055" />

En la siguiente pregunta, nos pide localizar el archivo que se ha descargado un .zip, que contiene una herramienta para obtener las credenciales.

Con esta información, nos desplazamos a los archivos descargados en el sistema. Esta ubicación es /root/Downloads/. Aquí podemos ver que hay un archivo llamado "mimikatz_trunk.zip".

<img width="870" height="556" alt="image" src="https://github.com/user-attachments/assets/b43ab4d3-a473-45b6-95ee-0fe5b859e62d" />

Con esta información hemos obtenido la respuesta de la tercera pregunta.

<img width="868" height="175" alt="image" src="https://github.com/user-attachments/assets/83972f7b-2ba5-4323-b6c7-a8f2b82aa748" />

Pasamos a la cuarta pregunta, en esta nos indican que localicemos un archivo secreto y digamos cual es su ruta.

Para ello, buscamos el archivo del bash_history, que nos proporcionara la respuesta a dicha cuestión.

<img width="872" height="443" alt="image" src="https://github.com/user-attachments/assets/00b00c51-e38e-4643-aef8-ee2c23736b92" />
/root/Desktop/SuperSecretFile.txt

<img width="872" height="170" alt="image" src="https://github.com/user-attachments/assets/9837f201-d355-4181-95b8-12fe5d11a96e" />

Para la siguiente pregunta nos pide localizar el programa que ha usado **didyouthinkwedmakeiteasy.jpg** en su ejecución.

Si seguimos explorando el historial bash, podemos ver que tras unos comandos, el programa "binwalk", ha ejecutado el archivo "didyouthinkwedmakeiteasy.jpg".

<img width="877" height="621" alt="image" src="https://github.com/user-attachments/assets/34814cce-83ce-4e34-be27-90ad6e2454bd" />
binwalk

<img width="868" height="171" alt="image" src="https://github.com/user-attachments/assets/6fea1c29-da5c-4f8f-8c98-eba83da9161f" />

Por el momento, con solo unos pocos conocimientos en linux y explorando el FTK Imager, hemos obtenido casi la mitad de las respuestas que nos pide este laboratorio.

Con la pregunta seis, debemos saber el tercer objetivo que Karen redactó en su lista de verificación.

Para ello, hemos explorado los principales lugares donde guardar una lista. Y como resultado, Karen almacenó en su escritorio, la lista que necesitamos con los 3 objetivos.

<img width="876" height="637" alt="image" src="https://github.com/user-attachments/assets/a215c38f-e6db-4334-b745-627eb3155e47" />
Profit

<img width="866" height="171" alt="image" src="https://github.com/user-attachments/assets/c8cc83ac-4c0d-436d-b0a8-439e420d6d3d" />

En la pregunta siete, debemos saber las veces que se ejecutó el Apache. Explorando los logs que habíamos localizado anteriormente, vemos que la carpeta de apache2, tiene los documentos creados pero sin contenido aparente, por lo que podríamos decir que el apache se ha ejecutado 0 unidades de veces.

<img width="873" height="468" alt="image" src="https://github.com/user-attachments/assets/e5d854f5-eb29-4ffc-bb46-3dbe12ba5a84" />
0

<img width="867" height="172" alt="image" src="https://github.com/user-attachments/assets/4d98dcd4-c73e-468f-bcc1-60841f73c630" />

Pasamos a la pregunta ocho, nos pide localizar el archivo de prueba en el que se demuestra que la máquina de Karen fue usada para atacar a otra máquina.

Como se muestra en la imagen, tenemos la evidencia con la ejecución.

<img width="875" height="507" alt="image" src="https://github.com/user-attachments/assets/5610c220-ef2f-42c3-af99-7acb4a4af5cb" />
irZLAohL.jpeg

<img width="868" height="172" alt="image" src="https://github.com/user-attachments/assets/df6b42a4-5471-4488-a2a6-a2440f477106" />

Ahora debemos responder a la nueve, que nos pregunta sobre el nombre de usuario, experto en informática y al que Karen se burlaba. 

Esta me ha costado más sacarla, ya que la respuesta se ve muy obvia pero no creía que fuera de verdad Young. Pero tras revisar todo los documentos uno por uno, no conseguí sacar ninguna evidencia que certificara que era otro usuario, por lo que entendí que Karen en este script, se refería a su compañero experto en informática.

<img width="872" height="472" alt="image" src="https://github.com/user-attachments/assets/29c5739a-f95e-48ab-bd2e-7a4b1206897d" />
Young

<img width="867" height="195" alt="image" src="https://github.com/user-attachments/assets/748cda9c-de76-4b5a-a08f-a88340647ba7" />

Continuamos con la pregunta diez. Necesitamos obtener el usuario que accedió a los privilegios de root a las 11:26 en varias ocasiones.

Para ello debemos de irnos donde se almacena todos los logs de ejecución de usuario, "auth.log". Explorando el log y centrandonos en la hora que nos indica, podemos observar que hay un usuario (postgres), que ha accedido a root en varias ocasiones.

<img width="873" height="516" alt="image" src="https://github.com/user-attachments/assets/a29d58bc-6a1f-4499-b546-8b8bf5823411" />
postgres

<img width="868" height="167" alt="image" src="https://github.com/user-attachments/assets/18c78f0a-d54c-4e79-8036-7f37c2844a5d" />

Y para finalizar, debemos responder a la última pregunta, que nos indica que, según el bash history, ¿Cuál es el directorio de trabajo actual?.

Como ya sabemos, el final del archivo es lo último que se escribió, por lo que, empezando desde abajo solo debemos desplazarnos hasta el primer desplazamiento de directorio. una vez localizado, solo sería añadirle el usuario al que pertenece, en este caso root, y así obtendríamos el directorio completo actual que nos pide la última pregunta. 

<img width="872" height="482" alt="image" src="https://github.com/user-attachments/assets/1a220f0a-b353-40a6-b1a1-1166a10f93ec" />
/root/Documents/myfirsthack/

<img width="867" height="172" alt="image" src="https://github.com/user-attachments/assets/077ef1e0-3532-46c5-a77e-102d688fd55d" />


