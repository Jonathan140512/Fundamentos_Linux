# Fundamentos_Linux

### ¿Por dónde te gustaría que empecemos?

Aquí tienes algunas áreas clave que podríamos explorar para darte una base sólida en Linux:

1.  **Instalación y entornos de trabajo:** ¿Cómo puedes tener Linux funcionando? (Máquina virtual, *dual boot*, subsistema de Windows para Linux - WSL). Esto es lo primero para poder practicar.
2.  **Comandos básicos de la terminal (CLI):** Aprender a navegar por el sistema de archivos, crear y manipular archivos y directorios, y ejecutar programas. ¡La terminal es tu herramienta más potente!
3.  **Sistema de archivos de Linux:** Entender cómo se organiza la información en Linux (directorios comunes como `/home`, `/etc`, `/var`, `/bin`).
4.  **Permisos de archivos y usuarios:** Conceptos cruciales para la seguridad y la administración. ¿Quién puede hacer qué con los archivos y directorios?
5.  **Administración de paquetes:** Cómo instalar, actualizar y desinstalar software en Linux (usando `apt`, `yum` o `dnf`).
6.  **Redirección y tuberías (pipes):** Conectar comandos entre sí para realizar tareas más complejas.
7.  **Conceptos de red básicos:** Configuración de interfaces de red y herramientas básicas para solucionar problemas de conectividad.

---

La **terminal** (o línea de comandos, *CLI* por sus siglas en inglés: *Command Line Interface*) es una interfaz de texto donde escribes comandos para que el sistema los ejecute. Al principio puede parecer un poco intimidante, pero con la práctica verás lo eficiente que es.

### Comandos esenciales para empezar

Vamos a cubrir los comandos más importantes para navegar por el sistema de archivos y manipular archivos y directorios. Imagina que la terminal es como el "Explorador de Archivos" o "Finder" de tu computadora, pero manejado con texto.

1.  **`pwd` (Print Working Directory): ¿Dónde estoy?**
    Este comando te dice la **ruta completa del directorio** en el que te encuentras actualmente.
    * **Uso:** `pwd`
    * **Ejemplo:** Si estás en tu carpeta personal, podría mostrar `/home/tu_usuario`.

2.  **`ls` (List): ¿Qué hay aquí?**
    Muestra el **contenido del directorio actual**. Es como abrir una carpeta y ver lo que hay dentro.
    * **Uso básico:** `ls`
    * **Opciones útiles:**
        * `ls -l`: Muestra una **lista detallada** (permisos, propietario, tamaño, fecha de modificación).
        * `ls -a`: Muestra **todos los archivos**, incluyendo los ocultos (que empiezan con un punto, `.`).
        * `ls -lh`: Muestra la lista detallada con **tamaños legibles para humanos** (KB, MB, GB).
        * Puedes combinar opciones: `ls -la` o `ls -lh`.

3.  **`cd` (Change Directory): ¡Muévete!**
    Te permite **cambiar de directorio** (carpeta). Es uno de los comandos que más usarás.
    * **Uso básico:** `cd nombre_del_directorio`
    * **Ejemplos:**
        * `cd Documentos`: Va al directorio "Documentos" dentro del actual.
        * `cd ..`: Sube un nivel en la jerarquía de directorios (al directorio padre).
        * `cd ~`: Te lleva directamente a tu **directorio personal** (`/home/tu_usuario`). Esto es muy útil.
        * `cd /`: Te lleva al **directorio raíz** del sistema de archivos de Linux.
        * `cd`: Sin argumentos, también te lleva a tu directorio personal.
        * `cd /var/log`: Va a una ruta absoluta específica.

4.  **`mkdir` (Make Directory): Crear carpetas.**
    Crea un **nuevo directorio** (carpeta).
    * **Uso:** `mkdir nombre_del_nuevo_directorio`
    * **Ejemplo:** `mkdir mis_proyectos`

5.  **`touch` (Touch): Crear archivos vacíos o actualizar fechas.**
    Crea un **archivo vacío** o actualiza la fecha de última modificación de un archivo existente.
    * **Uso:** `touch nombre_del_nuevo_archivo.txt`
    * **Ejemplo:** `touch mi_primer_archivo.txt`

6.  **`cp` (Copy): Copiar archivos y directorios.**
    Copia archivos o directorios de un lugar a otro.
    * **Uso para archivos:** `cp origen destino`
    * **Uso para directorios:** `cp -r origen_directorio destino_directorio` (la opción `-r` es para copiar recursivamente, es decir, todo el contenido del directorio).
    * **Ejemplo:** `cp archivo.txt Documentos/` (copia `archivo.txt` al directorio `Documentos`).
    * **Ejemplo:** `cp -r fotos/ backups/` (copia el directorio `fotos` y su contenido a `backups`).

7.  **`mv` (Move): Mover o renombrar archivos y directorios.**
    Mueve archivos o directorios de un lugar a otro. También se usa para **renombrar**.
    * **Uso:** `mv origen destino`
    * **Ejemplo (mover):** `mv reporte.pdf Documentos/informes/` (mueve `reporte.pdf` a `Documentos/informes/`).
    * **Ejemplo (renombrar):** `mv viejo_nombre.txt nuevo_nombre.txt`

8.  **`rm` (Remove): Eliminar archivos y directorios.**
    **¡Cuidado con este comando!** En Linux, una vez que algo se borra con `rm`, generalmente no hay "papelera de reciclaje".
    * **Uso para archivos:** `rm nombre_del_archivo`
    * **Uso para directorios (vacíos):** `rmdir nombre_del_directorio_vacio` (solo para directorios vacíos).
    * **Uso para directorios (no vacíos):** `rm -r nombre_del_directorio` (la opción `-r` es para borrar recursivamente, es decir, el directorio y todo su contenido). **¡MUCHO CUIDADO con `rm -r`!**
    * **Opciones útiles (con precaución):**
        * `rm -i archivo.txt`: Pregunta antes de borrar.
        * `rm -rf directorio/`: Borra el directorio y su contenido de forma **forzada y sin preguntar** (la `f` es de *force*). **¡ESTE COMANDO ES MUY PELIGROSO SI NO SABES LO QUE HACES!**

### ¡Es hora de practicar!

La mejor manera de aprender estos comandos es usándolos. Si ya tienes acceso a una terminal de Linux (ya sea a través de WSL en Windows, una máquina virtual o un sistema Linux real), te animo a que abras una y pruebes cada uno de estos comandos.

1.  Abre tu terminal.
2.  Prueba `pwd`.
3.  Usa `ls` y luego `ls -l` y `ls -a`.
4.  Crea un nuevo directorio: `mkdir mi_primera_carpeta`.
5.  Navega a ese directorio: `cd mi_primera_carpeta`.
6.  Dentro de él, crea un archivo: `touch archivo_prueba.txt`.
7.  Vuelve a usar `ls` para ver el archivo.
8.  Sube un nivel: `cd ..`.
9.  Copia tu archivo a otro nombre: `cp mi_primera_carpeta/archivo_prueba.txt mi_primera_carpeta/copia_archivo.txt`.
10. Mueve y renombra la carpeta: `mv mi_primera_carpeta mi_nueva_carpeta`.
11. Finalmente, si te sientes cómodo, borra el archivo `copia_archivo.txt` dentro de `mi_nueva_carpeta` (primero entra a la carpeta, luego borra) y luego borra la carpeta vacía `mi_nueva_carpeta` con `rmdir`. Si tiene cosas dentro y quieres borrarla con todo y contenido puedes usar `rm -r mi_nueva_carpeta`.

---

---
¡Excelente! Una vez que sabes cómo moverte y manipular archivos, el siguiente paso lógico es entender **dónde están las cosas** y por qué están ahí. Esto es crucial para trabajar eficientemente en Linux.

### 3. Sistema de Archivos de Linux: La Estructura de Directorios

A diferencia de Windows, donde las unidades (`C:`, `D:`, etc.) son puntos de partida separados, Linux tiene una **estructura de árbol unificada** que comienza desde un solo punto: el **directorio raíz (`/`)**. Todo en Linux, incluyendo dispositivos de hardware (discos duros, USBs), se monta como parte de este árbol de directorios.

Aquí te presento los directorios más importantes que encontrarás en un sistema Linux estándar y su propósito. Conocerlos te ayudará a saber dónde buscar programas, configuraciones, archivos de usuario y registros.

* **`/` (Raíz):**
    * Es el **directorio principal** de todo el sistema de archivos. Todo lo demás se encuentra debajo de este directorio.
    * Piensa en él como el "punto de partida" de todo.

* **`/bin` (Binaries):**
    * Contiene **comandos ejecutables esenciales** que son necesarios para que el sistema funcione, incluso en modo de usuario único.
    * Ejemplos: `ls`, `cp`, `mv`, `mkdir`, `rm`, `cat`, `echo`. Estos son los comandos básicos que ya empezamos a ver.

* **`/sbin` (System Binaries):**
    * Contiene **comandos ejecutables esenciales para el administrador del sistema (root)**. Estos comandos suelen ser utilizados para tareas de mantenimiento y administración del sistema.
    * Ejemplos: `fdisk`, `reboot`, `shutdown`, `mount`.

* **`/etc` (Et Cetera / Editable Text Configuration):**
    * Contiene **archivos de configuración** de todo el sistema. Estos archivos son generalmente de texto plano y se pueden editar para cambiar el comportamiento de programas y servicios.
    * Ejemplos: `passwd` (usuarios), `fstab` (montaje de sistemas de archivos), `resolv.conf` (configuración de DNS), archivos de configuración de Apache, Nginx, etc.

* **`/home`:**
    * Contiene los **directorios personales de los usuarios normales**. Cada usuario tiene su propio directorio dentro de `/home` (ej. `/home/tu_usuario`).
    * Aquí es donde los usuarios guardan sus documentos, descargas, configuraciones personales, etc. El símbolo `~` (tilde) es un atajo para tu directorio personal.

* **`/root`:**
    * Es el **directorio personal del usuario `root`** (el superusuario o administrador del sistema). Es similar a `/home/tu_usuario`, pero para el usuario con todos los privilegios.

* **`/var` (Variable):**
    * Contiene **archivos de datos que cambian con frecuencia** (variables). Estos incluyen archivos de registro (logs), bases de datos, archivos de *spool* de correo, etc.
    * Ejemplos:
        * `/var/log`: Archivos de registro del sistema y de aplicaciones.
        * `/var/www`: Directorios de sitios web (si usas un servidor web).
        * `/var/lib`: Información de estado variable de programas.

* **`/tmp` (Temporary):**
    * Contiene **archivos temporales**. El contenido de este directorio se borra generalmente cada vez que el sistema se reinicia.
    * Cualquier usuario puede escribir en este directorio.

* **`/usr` (Unix System Resources):**
    * Contiene la **mayoría de los ejecutables, bibliotecas, documentación y archivos fuente** de los programas instalados por el usuario y el sistema. Es uno de los directorios más grandes.
    * Ejemplos:
        * `/usr/bin`: Ejecutables de programas no esenciales para el arranque del sistema.
        * `/usr/local`: Programas instalados manualmente por el administrador.
        * `/usr/share`: Archivos compartidos por múltiples programas (documentación, iconos, etc.).
        * `/usr/lib`: Bibliotecas compartidas por programas.

* **`/opt` (Optional):**
    * Se utiliza para la instalación de **software opcional de terceros** que no sigue la estructura estándar de `/usr` o `/usr/local`. A menudo, las aplicaciones comerciales se instalan aquí.

* **`/dev` (Devices):**
    * Contiene **archivos especiales que representan dispositivos de hardware**. En Linux, todo es un archivo, incluyendo los dispositivos.
    * Ejemplos: `/dev/sda` (primer disco duro), `/dev/cdrom` (unidad de CD/DVD), `/dev/null` (un dispositivo especial que descarta toda la información que se le envía).

* **`/proc` (Process Information):**
    * Es un **sistema de archivos virtual** que contiene información sobre los procesos en ejecución y el estado del kernel. No son archivos reales en el disco, sino datos generados en tiempo real por el kernel.
    * Ejemplos: `/proc/cpuinfo` (información del CPU), `/proc/meminfo` (información de la memoria).

* **`/mnt` (Mount):**
    * Un punto de montaje temporal para **sistemas de archivos montados manualmente**, como unidades USB o particiones de disco.

* **`/media`:**
    * Punto de montaje para **medios extraíbles automáticamente**, como unidades USB, CDs/DVDs, tarjetas SD, cuando se conectan al sistema.

### ¿Por qué es importante conocer esto?

* **Resolución de problemas:** Si un programa no funciona, saber dónde buscar sus archivos de configuración (`/etc`) o sus registros (`/var/log`) es fundamental.
* **Instalación y desinstalación:** Entender dónde se instalan los programas (`/bin`, `/usr/bin`, `/opt`) te ayuda a gestionar el software.
* **Seguridad:** Saber dónde están los archivos de usuarios y configuraciones te ayuda a proteger tu sistema.
* **Navegación eficiente:** Podrás moverte por el sistema de archivos con confianza usando `cd`.

---

-----

¡Perfecto\! Entender los **permisos de archivos y usuarios** es absolutamente fundamental en Linux. Es la base de la seguridad y el control sobre quién puede hacer qué en el sistema.

### 4\. Permisos de Archivos y Usuarios: Quién puede hacer qué

En Linux, cada archivo y directorio tiene un conjunto de permisos que determinan quién puede leerlo, escribir en él o ejecutarlo. Estos permisos se asignan a tres categorías principales de entidades:

1.  **Usuario (User):** El propietario del archivo o directorio.
2.  **Grupo (Group):** Un grupo de usuarios al que pertenece el propietario.
3.  **Otros (Others):** Todos los demás usuarios del sistema.

Además, hay tres tipos de permisos básicos:

  * **`r` (Read - Lectura):**

      * **Archivos:** Permite ver el contenido del archivo.
      * **Directorios:** Permite listar el contenido del directorio (usar `ls`).

  * **`w` (Write - Escritura):**

      * **Archivos:** Permite modificar o eliminar el archivo.
      * **Directorios:** Permite crear, eliminar o renombrar archivos dentro de ese directorio.

  * **`x` (Execute - Ejecución):**

      * **Archivos:** Permite ejecutar el archivo (si es un programa o script).
      * **Directorios:** Permite entrar o "atravesar" el directorio (usar `cd` para acceder a él). Sin este permiso, no puedes acceder a los archivos dentro, incluso si tienes permisos de lectura en los archivos.

#### ¿Cómo se ven los permisos?

Cuando usas el comando `ls -l`, la primera columna de la salida muestra los permisos de esta manera:

```
-rwxr-xr--  1 tu_usuario tu_grupo  4096 Jul 10 10:30 mi_archivo.txt
drwxr-x---  2 tu_usuario tu_grupo  4096 Jul 10 10:30 mi_directorio/
```

Analicemos la cadena de permisos (`-rwxr-xr--` o `drwxr-x---`):

  * **Primer carácter (`-` o `d`):** Indica el tipo de archivo.

      * `-`: Es un archivo regular.
      * `d`: Es un directorio.
      * Otros caracteres pueden indicar enlaces simbólicos (`l`), dispositivos de bloque (`b`), etc.

  * **Siguientes 9 caracteres:** Se dividen en tres grupos de tres, representando los permisos para:

      * **Propietario (User):** Los primeros tres caracteres.
      * **Grupo (Group):** Los siguientes tres caracteres.
      * **Otros (Others):** Los últimos tres caracteres.

    Dentro de cada grupo, el orden es `rwx`. Si un permiso no está presente, se muestra un guion (`-`).

    **Ejemplo: `-rwxr-xr--`**

      * `-`: Es un archivo.
      * `rwx`: El propietario tiene permisos de lectura, escritura y ejecución.
      * `r-x`: El grupo tiene permisos de lectura y ejecución (pero no escritura).
      * `r--`: Otros usuarios solo tienen permiso de lectura.

    **Ejemplo: `drwxr-x---`**

      * `d`: Es un directorio.
      * `rwx`: El propietario tiene permisos de lectura, escritura y ejecución.
      * `r-x`: El grupo tiene permisos de lectura y ejecución.
      * `---`: Otros usuarios no tienen ningún permiso.

#### Comandos para gestionar permisos y propiedad:

1.  **`chmod` (Change Mode): Cambiar permisos.**
    Este comando se usa para cambiar los permisos de archivos y directorios. Puedes usar notación simbólica (letras) o notación octal (números).

      * **Notación Simbólica (más intuitiva para empezar):**

          * `u`: usuario (propietario)
          * `g`: grupo
          * `o`: otros
          * `a`: todos (all)
          * `+`: añadir permiso
          * `-`: quitar permiso
          * `=`: establecer permisos exactamente

        **Ejemplos:**

          * `chmod u+x mi_script.sh`: Añade permiso de ejecución al propietario.
          * `chmod go-w mi_archivo.txt`: Quita permiso de escritura al grupo y a otros.
          * `chmod a=rw mi_documento.pdf`: Establece permisos de lectura y escritura para todos, quitando cualquier otro.
          * `chmod +x mi_script.sh`: Añade permiso de ejecución para todos (si no se especifica `u`, `g`, `o`, se aplica a todos).
          * `chmod -R g+w mi_directorio/`: Añade permiso de escritura al grupo de forma recursiva (`-R`) para todos los archivos y subdirectorios dentro de `mi_directorio`.

      * **Notación Octal (más compacta y común en scripts):**
        Cada permiso (`r`, `w`, `x`) tiene un valor numérico:

          * `r` = 4
          * `w` = 2
          * `x` = 1
          * `-` = 0

        Sumas los valores para cada grupo (usuario, grupo, otros).

        **Ejemplos:**

          * `rwx` = 4+2+1 = 7
          * `rw-` = 4+2+0 = 6
          * `r-x` = 4+0+1 = 5
          * `r--` = 4+0+0 = 4

        Para el ejemplo `-rwxr-xr--` (754):

          * Propietario: `rwx` = 7
          * Grupo: `r-x` = 5
          * Otros: `r--` = 4
          * Comando: `chmod 754 mi_archivo.txt`

        Para el ejemplo `drwxr-x---` (750):

          * Propietario: `rwx` = 7
          * Grupo: `r-x` = 5
          * Otros: `---` = 0
          * Comando: `chmod 750 mi_directorio/`

2.  **`chown` (Change Owner): Cambiar propietario.**
    Cambia el usuario propietario de un archivo o directorio. Solo el usuario `root` (o con `sudo`) puede usar este comando.

      * **Uso:** `chown nuevo_propietario archivo_o_directorio`
      * **Ejemplo:** `sudo chown otro_usuario mi_archivo.txt` (cambia el propietario a `otro_usuario`).
      * **Cambiar propietario y grupo:** `sudo chown nuevo_propietario:nuevo_grupo archivo_o_directorio`
      * **Recursivo:** `sudo chown -R otro_usuario:otro_grupo mi_directorio/`

3.  **`chgrp` (Change Group): Cambiar grupo.**
    Cambia el grupo propietario de un archivo o directorio.

      * **Uso:** `chgrp nuevo_grupo archivo_o_directorio`
      * **Ejemplo:** `sudo chgrp nuevo_grupo mi_archivo.txt`
      * **Recursivo:** `sudo chgrp -R nuevo_grupo mi_directorio/`

#### Conceptos adicionales:

  * **`sudo` (SuperUser DO):** Este comando te permite ejecutar un comando con privilegios de superusuario (root). Es esencial para tareas administrativas que requieren permisos elevados.

      * **Ejemplo:** `sudo apt update` (actualiza la lista de paquetes del sistema).
      * Cuando usas `sudo`, se te pedirá tu contraseña de usuario (no la de root, si es que tienes una separada).

  * **Propietario por defecto (`umask`):** Cuando creas un nuevo archivo o directorio, se le asignan permisos por defecto. Este comportamiento se controla con el valor de `umask`. No necesitas cambiarlo al principio, pero es bueno saber que existe.

### Importancia de los permisos:

  * **Seguridad:** Evita que usuarios no autorizados lean, modifiquen o ejecuten archivos críticos del sistema o datos sensibles.
  * **Estabilidad:** Protege los archivos del sistema de modificaciones accidentales.
  * **Colaboración:** Permite que múltiples usuarios trabajen en el mismo sistema de forma segura, compartiendo recursos de manera controlada.

-----

-----

¡Excelente\! Pasemos a la **administración de paquetes**, un aspecto crucial para cualquier usuario de Linux, especialmente si buscas oportunidades laborales. Saber cómo instalar, actualizar y eliminar software de manera eficiente es una habilidad muy valorada.

### 5\. Administración de Paquetes: Instalando y Gestionando Software

En Linux, el software se distribuye en "paquetes". Un paquete es un archivo comprimido que contiene todos los archivos necesarios para una aplicación (el programa ejecutable, bibliotecas, archivos de configuración, documentación, etc.), junto con metadatos sobre sus dependencias y cómo instalarlo.

Cada distribución de Linux tiene su propio **sistema de gestión de paquetes** y sus herramientas asociadas. Los más comunes son:

  * **APT (Advanced Package Tool):** Usado en distribuciones basadas en Debian, como **Ubuntu**, Debian, Linux Mint.
  * **YUM (Yellowdog Updater Modified) / DNF (Dandified YUM):** Usados en distribuciones basadas en Red Hat, como **Fedora**, CentOS, RHEL. DNF es la versión más moderna y recomendada sobre YUM.

Dado que Ubuntu es una de las distribuciones más populares para principiantes y en entornos laborales, nos centraremos en **APT**.

#### Conceptos clave de APT:

  * **Repositorios:** Son servidores que almacenan los paquetes de software. Tu sistema Linux está configurado para saber de dónde descargar los paquetes.
  * **`apt update`:** Este comando **actualiza la lista de paquetes disponibles** en tus repositorios. No instala ni actualiza software, solo descarga la información más reciente sobre qué paquetes existen y en qué versiones. **Siempre debes ejecutarlo antes de instalar o actualizar software.**
  * **`apt upgrade`:** Este comando **actualiza todos los paquetes instalados** en tu sistema a sus versiones más recientes, basándose en la lista que obtuviste con `apt update`.
  * **`apt install`:** Este comando instala un nuevo paquete de software.
  * **`apt remove`:** Este comando desinstala un paquete de software, pero mantiene los archivos de configuración.
  * **`apt purge`:** Este comando desinstala un paquete de software y también elimina sus archivos de configuración.
  * **`apt autoremove`:** Elimina paquetes que se instalaron automáticamente para satisfacer dependencias de otros paquetes, pero que ya no son necesarios.
  * **`apt search`:** Busca paquetes en los repositorios.
  * **`apt show`:** Muestra información detallada sobre un paquete.

#### Comandos esenciales con APT (ejemplos):

1.  **Actualizar la lista de paquetes:**

    ```bash
    sudo apt update
    ```

      * `sudo`: Necesitas privilegios de superusuario para modificar la lista de paquetes del sistema.

2.  **Actualizar todos los paquetes instalados:**

    ```bash
    sudo apt upgrade
    ```

      * También requiere `sudo`.

3.  **Instalar un nuevo paquete (ej. `neofetch` para mostrar información del sistema):**

    ```bash
    sudo apt install neofetch
    ```

      * Te preguntará si deseas continuar. Presiona `S` (o `Y` en inglés) y Enter.
      * Después de instalar, puedes ejecutar `neofetch` para ver la información.

4.  **Instalar múltiples paquetes a la vez:**

    ```bash
    sudo apt install htop git curl
    ```

5.  **Buscar un paquete:**

    ```bash
    apt search firefox
    ```

      * Esto te mostrará todos los paquetes que contengan "firefox" en su nombre o descripción.

6.  **Ver información detallada de un paquete:**

    ```bash
    apt show firefox
    ```

      * Te mostrará la versión, dependencias, descripción, etc.

7.  **Desinstalar un paquete (manteniendo configuración):**

    ```bash
    sudo apt remove neofetch
    ```

8.  **Desinstalar un paquete (eliminando configuración):**

    ```bash
    sudo apt purge neofetch
    ```

9.  **Eliminar dependencias no usadas:**

    ```bash
    sudo apt autoremove
    ```

#### ¿Por qué es importante la gestión de paquetes?

  * **Facilidad de instalación:** No tienes que buscar archivos `.exe` o `.dmg` en la web. Los paquetes están centralizados y son fáciles de instalar.
  * **Resolución de dependencias:** El gestor de paquetes se encarga automáticamente de instalar todas las bibliotecas y otros paquetes que un programa necesita para funcionar.
  * **Actualizaciones sencillas:** Mantener tu sistema y tus aplicaciones actualizadas es tan simple como un par de comandos.
  * **Seguridad y estabilidad:** Los paquetes de los repositorios oficiales suelen ser verificados y son menos propensos a contener malware o causar inestabilidad.

-----

---
¡Perfecto! El siguiente paso es comprender cómo los comandos de Linux pueden trabajar juntos de manera inteligente, lo que te permite realizar tareas más complejas con facilidad. Esto se logra mediante la **redirección** y las **tuberías (pipes)**.

### 6. Redirección y Tuberías (Pipes): Conectando Comandos

Normalmente, un comando de Linux toma su **entrada** del teclado y envía su **salida** a la pantalla (la terminal). La redirección y las tuberías te permiten cambiar estos flujos, haciendo que la salida de un comando se convierta en la entrada de otro, o enviándola a un archivo en lugar de la pantalla.

#### a. Redirección de Salida (`>`, `>>`)

Esto te permite enviar la salida de un comando a un archivo en lugar de mostrarla en la terminal.

* **`>` (Redirigir y Sobreescribir):**
    * Envía la salida de un comando a un archivo. **Si el archivo ya existe, su contenido será *borrado* y reemplazado por la nueva salida.**
    * **Uso:** `comando > archivo.txt`
    * **Ejemplo:** `ls -l > lista_archivos.txt`
        * Esto guardará la lista detallada de los archivos del directorio actual en un archivo llamado `lista_archivos.txt`. Si `lista_archivos.txt` ya existía, su contenido anterior se perderá.

* **`>>` (Redirigir y Añadir):**
    * Envía la salida de un comando a un archivo, pero si el archivo ya existe, la **nueva salida se añade al final** del contenido existente. Si el archivo no existe, lo crea.
    * **Uso:** `comando >> archivo.txt`
    * **Ejemplo:** `echo "Este es un mensaje nuevo" >> mi_log.txt`
        * Añade la línea "Este es un mensaje nuevo" al final de `mi_log.txt`. Si `mi_log.txt` no existe, lo crea con esa línea.

#### b. Redirección de Entrada (`<`)

Esto te permite usar un archivo como entrada para un comando, en lugar de que el comando espere la entrada del teclado.

* **Uso:** `comando < archivo.txt`
* **Ejemplo:** `sort < lista_desordenada.txt`
    * El comando `sort` (que ordena líneas de texto) tomará su entrada de `lista_desordenada.txt` en lugar de esperar que escribas líneas en la terminal. La salida ordenada se mostrará en la terminal.

#### c. Tuberías (Pipes - `|`)

Las tuberías son increíblemente poderosas. Permiten **conectar la salida de un comando directamente a la entrada de otro comando**. Piensa en ellas como una "tubería" que lleva el agua (salida de datos) de un grifo (primer comando) a otro grifo (segundo comando).

* **Uso:** `comando1 | comando2 | comando3 ...`
* **Funcionamiento:** La salida estándar de `comando1` se convierte en la entrada estándar de `comando2`, y así sucesivamente.

**Ejemplos prácticos de tuberías:**

1.  **Contar archivos (`ls` + `wc -l`):**
    * `ls -l | wc -l`
    * `ls -l` lista los archivos y directorios con detalles.
    * `|` Envía esa lista como entrada a `wc -l` (word count -l cuenta líneas).
    * **Resultado:** Te dará el número total de líneas (y por lo tanto, el número de archivos/directorios) en el directorio actual.

2.  **Buscar texto en la salida de un comando (`ps aux` + `grep`):**
    * `ps aux | grep firefox`
    * `ps aux` muestra todos los procesos en ejecución en el sistema.
    * `|` Envía esa lista de procesos a `grep firefox`.
    * `grep firefox` filtra las líneas que contienen la palabra "firefox".
    * **Resultado:** Verás solo las líneas de los procesos de Firefox que están corriendo. Esto es muy útil para monitorear servicios o aplicaciones específicas.

3.  **Ver las últimas líneas de un archivo de registro (`cat` + `tail`):**
    * `cat /var/log/syslog | tail -n 10`
    * `cat /var/log/syslog` muestra todo el contenido del archivo de registro del sistema.
    * `|` Envía ese contenido a `tail -n 10`.
    * `tail -n 10` muestra solo las últimas 10 líneas de su entrada.
    * **Resultado:** Obtienes las últimas 10 líneas del archivo de registro, lo cual es útil para revisar eventos recientes sin ver todo el archivo.

4.  **Ordenar una lista y guardarla (`ls` + `sort` + `>`):**
    * `ls | sort > archivos_ordenados.txt`
    * `ls` lista los archivos.
    * `| sort` ordena alfabéticamente esa lista.
    * `> archivos_ordenados.txt` guarda la lista ordenada en el archivo `archivos_ordenados.txt`.

#### ¿Por qué son importantes la redirección y las tuberías?

* **Automatización:** Te permiten encadenar comandos para realizar tareas complejas con una sola línea.
* **Flexibilidad:** Puedes manipular datos de muchas maneras, filtrando, ordenando, combinando información.
* **Eficiencia:** Evitas tener que guardar resultados intermedios en archivos temporales, lo que ahorra tiempo y recursos.
* **Resolución de problemas:** Son esenciales para analizar archivos de registro, monitorear procesos y depurar problemas en el sistema.

---

---
¡Fantástico! Ya hemos cubierto una buena base para interactuar con Linux. Ahora, veamos cómo Linux maneja las conexiones con el mundo exterior.

### 7. Conceptos de Red Básicos en Linux

En el mundo de TI actual, la mayoría de los sistemas Linux están conectados a una red, ya sea Internet, una red local en una oficina o la nube. Entender los conceptos básicos de red en Linux es esencial para la resolución de problemas y la administración de servidores.

Aquí te presento algunos comandos y conceptos clave para empezar:

#### a. Interfaces de Red

Tu computadora Linux se conecta a una red a través de una **interfaz de red**. Estas interfaces pueden ser físicas (como una tarjeta Ethernet, **`eth0`**, o una tarjeta Wi-Fi, **`wlan0`**) o virtuales (como **`lo`** para *loopback*, que es una interfaz de red interna que el sistema usa para comunicarse consigo mismo).

* **`ip a` o `ip addr show` (o el más antiguo `ifconfig`):**
    * Muestra las **direcciones IP y la configuración de todas las interfaces de red** en tu sistema. Este es uno de los primeros comandos que usarás para diagnosticar problemas de red.
    * **Uso:** `ip a`
    * **Salida clave a buscar:**
        * **`lo` (loopback):** Siempre debe estar ahí, con la dirección `127.0.0.1` (IPv4) y `::1` (IPv6). Se usa para comunicaciones internas.
        * **`eth0` o `enpXsX` (Ethernet):** La interfaz de red cableada. Buscarás `inet` para tu dirección IPv4 (ej. `192.168.1.100`) y `inet6` para IPv6.
        * **`wlan0` o `wlpXsX` (Wireless):** La interfaz Wi-Fi.

#### b. Direccionamiento IP y Puerta de Enlace (Gateway)

* **Dirección IP:** Es la identificación única de tu dispositivo en la red (ej. `192.168.1.100`).
* **Máscara de red (Netmask):** Define qué parte de la dirección IP identifica la red y qué parte identifica el host dentro de esa red.
* **Puerta de Enlace (Gateway):** Es la dirección IP del dispositivo (generalmente tu router) que permite a tu sistema comunicarse con otras redes (como Internet). Si tu gateway no está configurado correctamente, no podrás acceder a Internet.

* **`ip r` o `ip route show` (o el más antiguo `route -n`):**
    * Muestra la **tabla de enrutamiento** de tu sistema. Aquí puedes ver cómo se dirige el tráfico de red, incluyendo tu puerta de enlace por defecto.
    * **Uso:** `ip r`
    * **Salida clave a buscar:** Una línea que empieza con `default via` mostrará la dirección IP de tu puerta de enlace.

#### c. Resolución de Nombres (DNS)

Cuando escribes una dirección web como `google.com`, tu sistema necesita convertir ese nombre legible para humanos en una dirección IP numérica que las computadoras puedan entender (ej. `172.217.160.142`). Esto lo hace el **Sistema de Nombres de Dominio (DNS)**.

* **`ping`:**
    * Envía pequeños paquetes a una dirección IP o nombre de host para verificar la conectividad y medir el tiempo de respuesta. Es la primera herramienta para diagnosticar problemas de red.
    * **Uso:** `ping google.com` o `ping 8.8.8.8`
    * **Para detenerlo:** Presiona `Ctrl + C`.

* **`dig` (Domain Information Groper) o `nslookup`:**
    * Herramientas para **consultar servidores DNS** y obtener información sobre nombres de dominio. Útiles para verificar si la resolución de DNS funciona correctamente.
    * **Uso:** `dig google.com`

#### d. Conexiones de Red y Puertos

* **`ss` (Socket Statistics) o `netstat` (el más antiguo):**
    * Muestra información sobre las **conexiones de red activas** (sockets), incluyendo puertos abiertos, conexiones establecidas y procesos asociados. Es fundamental para saber qué servicios están escuchando en qué puertos.
    * **Uso común:** `ss -tuln`
        * `-t`: Muestra conexiones TCP.
        * `-u`: Muestra conexiones UDP.
        * `-l`: Muestra sockets en estado de "escucha" (listening).
        * `-n`: Muestra direcciones y números de puerto numéricos (en lugar de nombres de servicio).
    * **Ejemplo de uso:** Si tienes un servidor web (como Apache o Nginx), `ss -tuln` debería mostrar una línea indicando que hay algo escuchando en el puerto 80 (HTTP) o 443 (HTTPS).

#### e. Firewall (Netfilter / Iptables / UFW)

Linux tiene un potente **firewall** incorporado (basado en Netfilter, gestionado por `iptables` o `nftables`). Muchas distribuciones simplifican su configuración con herramientas como **`ufw` (Uncomplicated Firewall)**, especialmente en Ubuntu.

* **`sudo ufw status`:** Muestra el estado del firewall UFW (activo/inactivo) y las reglas configuradas.
* **`sudo ufw enable` / `sudo ufw disable`:** Habilita o deshabilita el firewall.
* **`sudo ufw allow 80/tcp`:** Permite conexiones entrantes al puerto 80 (HTTP) usando TCP.

#### ¿Por qué es importante saber esto para tus oportunidades laborales?

* **Administración de Servidores:** La mayoría de los servidores son Linux y están conectados a redes. Saber diagnosticar problemas de conectividad es una habilidad básica.
* **DevOps/Cloud:** En entornos de nube, entender cómo se comunican las máquinas virtuales y los contenedores es vital.
* **Ciberseguridad:** Reconocer puertos abiertos, conexiones sospechosas y configurar firewalls es fundamental para proteger sistemas.
* **Desarrollo:** Si desarrollas aplicaciones que se conectan a bases de datos o servicios externos, necesitarás comprender los conceptos de red.

---



---

### Ejercicios Prácticos de Linux para Principiantes

#### Tema 1: Comandos Básicos de la Terminal (`pwd`, `ls`, `cd`, `mkdir`, `touch`, `cp`, `mv`, `rm`, `rmdir`)

1.  **Navegación y Creación:**
    * Abre tu terminal.
    * Usa `pwd` para saber dónde estás.
    * Crea un directorio llamado `mis_ejercicios` en tu directorio personal.
    * Navega dentro de `mis_ejercicios`.
    * Dentro de `mis_ejercicios`, crea dos subdirectorios: `documentos` y `programas`.
    * Crea un archivo vacío llamado `notas.txt` dentro de `documentos`.
    * Crea un archivo vacío llamado `script.sh` dentro de `programas`.
    * Desde `mis_ejercicios`, lista el contenido de `documentos` sin entrar en él (pista: `ls documentos`).
    * Sube un nivel en la jerarquía de directorios.

2.  **Copia y Movimiento:**
    * Desde tu directorio personal, copia el archivo `notas.txt` (que está en `mis_ejercicios/documentos/`) a tu directorio personal.
    * Mueve el archivo `script.sh` (que está en `mis_ejercicios/programas/`) a la carpeta `mis_ejercicios/documentos/`.
    * Renombra el archivo `notas.txt` (el que está en tu directorio personal) a `mis_notas_importantes.txt`.

3.  **Eliminación (¡Con Cuidado!):**
    * Elimina el archivo `mis_notas_importantes.txt` de tu directorio personal.
    * Navega de nuevo a `mis_ejercicios`.
    * Intenta eliminar el directorio `documentos` usando `rmdir`. ¿Qué sucede y por qué?
    * Elimina el directorio `documentos` y todo su contenido utilizando el comando adecuado (¡cuidado!).
    * Finalmente, elimina el directorio `programas` (debería estar vacío ahora).
    * Sube un nivel y elimina el directorio `mis_ejercicios`.

#### Tema 2: Sistema de Archivos de Linux

1.  **Exploración:**
    * Navega al directorio raíz (`/`). Usa `ls` para ver qué hay.
    * Entra en `/etc`. ¿Puedes listar su contenido? ¿Qué tipo de archivos esperas encontrar aquí?
    * Navega a `/var/log`. ¿Qué crees que encontrarás aquí? ¿Puedes listar algunos archivos?
    * Vuelve a tu directorio personal usando el atajo.
    * Explora el contenido de `/usr/bin`. ¿Qué tipo de comandos o ejecutables ves? (Usa `ls | head` para ver solo las primeras líneas, ya que es muy grande).

#### Tema 3: Permisos de Archivos y Usuarios (`ls -l`, `chmod`, `chown`, `chgrp`, `sudo`)

1.  **Inspección de Permisos:**
    * En tu directorio personal, crea un archivo llamado `mi_archivo.txt` y un directorio llamado `mi_carpeta`.
    * Usa `ls -l` para ver los permisos por defecto de `mi_archivo.txt` y `mi_carpeta`. Anota los permisos para el propietario, grupo y otros.
    * Crea un script vacío llamado `mi_script.sh` (`touch mi_script.sh`).
    * Usa `ls -l mi_script.sh` para ver sus permisos. ¿Tiene permiso de ejecución?

2.  **Modificación de Permisos:**
    * Añade permiso de ejecución a `mi_script.sh` solo para el propietario (notación simbólica). Verifica con `ls -l`.
    * Quita el permiso de escritura a `mi_archivo.txt` para el grupo y para otros (notación simbólica). Verifica con `ls -l`.
    * Establece los permisos de `mi_carpeta` para que el propietario tenga lectura, escritura y ejecución (`rwx`), el grupo tenga solo lectura y ejecución (`r-x`), y otros no tengan ningún permiso (`---`). Usa la notación octal. Verifica con `ls -l`.

3.  **Cambio de Propiedad (Requiere `sudo`):**
    * **Nota:** Para estos ejercicios, necesitarás un segundo usuario en tu sistema o simularlo. Si no tienes otro usuario, puedes omitir los comandos `chown` y `chgrp` por ahora, pero entiende su propósito.
    * Si tienes un segundo usuario (ej. `otro_usuario`), intenta cambiar el propietario de `mi_archivo.txt` a `otro_usuario`. (`sudo chown otro_usuario mi_archivo.txt`). Verifica con `ls -l`.
    * Cambia el grupo propietario de `mi_carpeta` a un grupo existente en tu sistema (ej. `users` o `nogroup`). (`sudo chgrp users mi_carpeta`). Verifica con `ls -l`.

#### Tema 4: Administración de Paquetes (`apt update`, `apt upgrade`, `apt install`, `apt remove`, `apt search`)

1.  **Actualización y Búsqueda:**
    * Actualiza la lista de paquetes de tu sistema: `sudo apt update`.
    * Busca un paquete llamado `htop` (un monitor de procesos interactivo): `apt search htop`.
    * Muestra información detallada sobre el paquete `htop`: `apt show htop`.

2.  **Instalación y Desinstalación:**
    * Instala `htop`: `sudo apt install htop`.
    * Después de la instalación, ejecuta `htop` para verlo en acción. Sal de `htop` presionando `F10` o `q`.
    * Desinstala `htop` manteniendo sus archivos de configuración: `sudo apt remove htop`.
    * Vuelve a instalar `htop`.
    * Desinstala `htop` eliminando también sus archivos de configuración: `sudo apt purge htop`.
    * Ejecuta `sudo apt autoremove` para limpiar cualquier dependencia que ya no sea necesaria.

#### Tema 5: Redirección y Tuberías (`>`, `>>`, `|`)

1.  **Redirección de Salida:**
    * Lista el contenido de tu directorio personal y guarda la salida en un archivo llamado `contenido_home.txt`: `ls > contenido_home.txt`.
    * Añade la fecha y hora actual al final de `contenido_home.txt`: `date >> contenido_home.txt`.
    * Verifica el contenido de `contenido_home.txt` usando `cat contenido_home.txt`.
    * Crea un archivo llamado `numeros.txt` con los números del 1 al 5, cada uno en una línea. Puedes usar `echo "1" > numeros.txt` y luego `echo "2" >> numeros.txt`, etc.

2.  **Tuberías (Pipes):**
    * Lista todos los archivos y directorios de tu sistema (`ls -lR /`) y filtra solo las líneas que contengan la palabra "bin" (pista: `ls -lR / | grep bin`).
    * Muestra las últimas 5 líneas del archivo `/var/log/syslog` (o cualquier otro archivo de log que exista en tu sistema, si `syslog` no existe): `cat /var/log/syslog | tail -n 5`.
    * Cuenta el número de líneas en el archivo `/etc/passwd` (que contiene información de usuarios): `cat /etc/passwd | wc -l`.
    * Lista los archivos de tu directorio personal, ordénalos alfabéticamente de forma inversa y guarda el resultado en un nuevo archivo llamado `archivos_orden_inverso.txt`: `ls | sort -r > archivos_orden_inverso.txt`.

#### Tema 6: Conceptos de Red Básicos (`ip a`, `ip r`, `ping`, `dig`, `ss`, `ufw`)

1.  **Información de Red:**
    * Muestra la configuración de tus interfaces de red: `ip a`. Identifica tu dirección IP (IPv4 y/o IPv6) y el nombre de tu interfaz principal (ej. `eth0`, `wlan0`).
    * Muestra tu tabla de enrutamiento y encuentra la dirección IP de tu puerta de enlace por defecto: `ip r`.

2.  **Conectividad y DNS:**
    * Haz ping a `google.com`. ¿Funciona? (Presiona `Ctrl + C` para detener).
    * Haz ping a una dirección IP conocida, como el DNS público de Google: `ping 8.8.8.8`. ¿Funciona? Si `ping google.com` falla pero `ping 8.8.8.8` funciona, el problema podría ser de DNS.
    * Usa `dig google.com` para ver la resolución DNS de Google.

3.  **Conexiones y Puertos:**
    * Muestra los puertos que están "escuchando" en tu sistema: `ss -tuln`. ¿Ves algún puerto conocido como 22 (SSH), 80 (HTTP), 443 (HTTPS)?

4.  **Firewall (si usas Ubuntu/Debian con UFW):**
    * Verifica el estado de tu firewall: `sudo ufw status`.
    * Si está inactivo y te sientes cómodo, actívalo: `sudo ufw enable`. (¡Cuidado si estás conectado remotamente, podrías bloquearte!).
    * Si lo activaste, intenta permitir el tráfico SSH (puerto 22): `sudo ufw allow 22/tcp`.
    * Vuelve a revisar el estado: `sudo ufw status`.
    * Si lo activaste para este ejercicio, puedes deshabilitarlo de nuevo: `sudo ufw disable`.

---
---
