# Proyecto2_SistemaDeTelevigilancia
En este repositorio se encuentran las dos meta-layers personalizadas que se crearon para incluir en una imagen una aplicacion de OpenCV en python que es capaz de detectar personas en videos e imagenes. 
La meta-layer meta-proyecto1 es en la que se incluye la aplicacion con su respectiva receta y una imagen que es utilizada para ejemplificar su uso. 
En la meta-layer meta-libimutils se incluye la receta para que el sistema sea capaz de incluir la libreria imutils, ya que esta es importada en la aplicacion de python utilizada. 
Los pasos a seguir para desarrollar para construir esta imagen se pueden observar a continuación: 
1. Ejecutar en terminal: $ sudo apt-get install gawk wget git-core diffstat unzip texinfo gcc-multilib \build-essential chrpath socat cpio python python3 python3-pip python3-pexpect \ xz-utils debianutils iputils-ping libsdl1.2-dev xterm
2. Ejecutar en terminal: $ git clone -b warrior git://git.yoctoproject.org/poky.git poky-warrior
3. Ejecutar en terminal: 
$ git clone -b warrior git://git.openembedded.org/meta-openembedded
$ git clone -b warrior https://github.com/meta-qt5/meta-qt5
4. Clonar este repositorio dentro de la carpeta de poky-warrior creada con los pasos anteriores. 
5. Ajustar bblayers de las dos meta-layers agregadas con el repositorio. 
6. Ejecutar en terminal: $ source oe-init-build-env
7. Ejecutar en terminal: $ bitbake core-image-sato
8. Con el paso anterior ya se tiene la imagen cocinada por lo que ejecutando el comando en la terminal: runqemu qemux86-64 
se completa el proceso. 
9. En el caso de querer instalarla en máquina virtual se realiza el mismo procedimiento pero en vez de definir la MACHINE TARGET como qemux86-64, se define como genericx86-64 para que así sea capaz de soportar máquinas con procesadores como el intel i-core. 
10. Una vez definido lo anterior se procede de igual forma a hacerle build al environment y utilizar bitbake core-image-sato. Se debe buscar en: ../poky-warrior/build/tmp/deploy/genericx86-64/genericx86.iso
11. Ese archivo .iso se puede incluir en la máquina virtual de Virtual Box y configurar su ejecución para que la imagen sea instalada en esa máquina. 

En el directorio build se encuentra el directorio conf con los archivos local.conf, bblayers.conf y templateconf.cfg tal y como debe ir segun el resto de meta-layers obtenidas.
