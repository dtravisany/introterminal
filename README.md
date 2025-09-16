# introterminal
## Introducción a Unix y la SHELL

### Resumen

Práctico para utilizar la consola de UNIX/Linux


### Introducción

Unix/Linux es el sistema operativo estándar para cómputo científico. Algo similar sucede con Windows, pero en computadores de escritorio (PC).

Siguiendo esta comparativa, las similitudes entre ambos Sistemas Operativos son:

  - Se encargan de manejar el hardware por ud (redes, discos duros, procesador).

  - Proveen una interfaz para ejecutar aplicaciones y almacenar sus archivos.

  - Ambos poseen interfaces de escritorio que ofrecen casi las mismas prestaciones.


Por otra parte, Unix es seguro, estable y permite la ejecución de tareas con múltiples usuarios. Esto lo ha transformado en el sistema operativo de excelencia para computación de alto rendimiento (HPC: High Performance Computing). Se puede utilizar en diferentes tipos de hardware desde RaspberryPi, celulares y tablets (Android), notebook y PC hasta supercomputadores como Leftraru del [NLHPC](http://www.nlhpc.cl).

### Puesta a punto


Para facilitar este y los demás prácticos, he habilitado una de mis máquinas para la ejecución de tareas en este curso.

Si están en:

  - *Linux/MacOS*, puede utilizar [la terminal](https://help.ubuntu.com/kubuntu/desktopguide/es/terminals.html) (consola).

  - *Windows10* utilice el [Símbolo del sistema](https://es.wikipedia.org/wiki/S%C3%ADmbolo_del_sistema) (`cmd`).

  - Si están en *Windows* (anterior a *Windows 10*) deben instalar un programa llamado [Putty](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html) o [MobaXterm](https://mobaxterm.mobatek.net/)


### La Terminal

  - Es llamada *prompt*, *shell*, *línea de comandos*.

  - Antiguamente, era la única forma de interactuar con los computadores. 
  
  - Es la interfaz que se utiliza para ejecutar comandos/programas o analizar los datos.

  - La mayoría de los programas que utilizamos a diario tienen una [GUI](https://es.wikipedia.org/wiki/Interfaz_gr%C3%A1fica_de_usuario)(Graphical User Interface). Sin embargo, la mayoría de los programas más utilizados en ciencia o Big Data no poseen una interfaz gráfica, esto principalmente porque los servidores donde se ejecutan los programas no tienen GUI.

  - Saber utilizar la terminal nos proveerá de una cantidad sustancial de ventajas en HPC.

### Protocolo SSH

Ahora, en la terminal, utilizaremos el protocolo [SSH](https://web.mit.edu/rhel-doc/4/RH-DOCS/rhel-rg-es-4/ch-ssh.html).

> :warning:  **NOTA**: De ahora en adelante, cada vez que vea `instrucción` se referira a un comando/programa a ejecutar, mientras que:

		esto será código a escribir en la terminal

> :warning: **NOTA**: En *Unix*, la terminal es *case sensitive*, es decir, escribir una `instrucción` es distinto a escribir  una `INSTRUCCIÓN` o `Instrucción` (*Windows* es diferente). Lo mismo pasa con los usuarios y los nombres de archivos. 

> :warning: **NOTA**: La mayoría de las veces, cuando tenga un problema al ejecutar una instrucción, se debe a errores tipográficos (*typos*). 
 
Una vez abierta la terminal (solo en *Win10*, *Linux*, *MacOS*), cada grupo debe escribir lo siguiente:

         ssh  usuario@servidor


> :warning: **NOTA**: Les entregaré las credenciales en la clase.


Mediante el comando SSH podremos entrar al servidor para el curso. 

### Estructura de Directorios

En linux los directorios se organizan en una Jerarquía, es decir hay un directorio raíz y desde ese directorio se accede a sub-directorios.

Recordemos la estructura de directorios en LINUX.

Dentro del servidor podemos ver donde estamos ubicados utilizando `pwd` ([print working directory](https://linux.die.net/man/1/pwd)). 
```bash
pwd
```
Para saber el contenido del directorio donde estamos ubicados utilizamos `ls` ([list](https://linux.die.net/man/1/ls))

```bash
ls
```
Crearemos un directorio con su nombre y apellido:

```bash
mkdir nombreApellido
```

Si tenemos más de un directorio podemos ingresar a ese directorio con el comando `cd` ([change directory](http://linuxcommand.org/lc3_man_pages/cdh.html))

```bash
cd nombreApellido
```

# VIM

## Objetivo
Aprender los comandos básicos y esenciales de VIM para poder **navegar, editar, guardar y buscar en archivos de texto** de forma eficiente.

## 1. Iniciar con VIM
Abrir un archivo nuevo o existente:  

```bash
vim archivo.txt
```

 **Ejercicio:**  
- Abre VIM con `vim prueba.txt`.  
- Observa que entras en **Normal mode** por defecto.  

---

## 2. Modos de VIM
- **Normal (N):** Navegar y ejecutar comandos (modo por defecto).  
- **Insert (I):** Escribir texto.  
- **Visual (V):** Seleccionar texto.  
- **Command (:):** Ejecutar comandos.  

 **Ejercicio:**  
- Pulsa `i` y escribe tu nombre.  
- Pulsa `ESC` para volver a Normal.  
- Pulsa `v` y selecciona tu nombre letra por letra.  

---

## 3. Navegación básica
En **Normal mode**:  
- `h` → izquierda  
- `l` → derecha  
- `j` → abajo  
- `k` → arriba  
- `0` → inicio de línea  
- `$` → final de línea  
- `gg` → inicio del archivo  
- `G` → final del archivo  

 **Ejercicio:**  
- Escribe varias líneas de texto.  
- Mueve el cursor con `h, j, k, l`.  
- Salta al inicio con `gg` y al final con `G`.  

---

## 4. Edición básica
- `i` → insertar antes del cursor  
- `a` → insertar después del cursor  
- `o` → nueva línea debajo  
- `O` → nueva línea encima  
- `x` → borrar un caracter  
- `dd` → borrar línea  
- `yy` → copiar línea  
- `p` → pegar  

 **Ejercicio:**  
- Borra una palabra con `x`.  
- Duplica una línea con `yy` y luego `p`.  
- Inserta una línea en blanco con `o`.  

---

## 5. Guardar y salir
En **Command mode (:)**:  
- `:w` → guardar  
- `:q` → salir  
- `:wq` → guardar y salir  
- `:q!` → salir sin guardar  

 **Ejercicio:**  
- Escribe algo y guarda con `:w`.  
- Sal del archivo con `:q`.  
- Intenta salir sin guardar con `:q!`.  

---

## 6. Buscar y reemplazar
- `/texto` → buscar hacia abajo  
- `n` → siguiente coincidencia  
- `N` → coincidencia anterior  
- `:%s/viejo/nuevo/g` → reemplazar en todo el archivo  

 **Ejercicio:**  
- Escribe varias veces la palabra `dato`.  
- Búscala con `/dato`.  
- Reemplázala por `información` con `:%s/dato/información/g`.  

---

## 7. Visual mode
- `v` → selección por caracteres  
- `V` → selección por líneas  
- `Ctrl+v` → selección por bloques  

**Ejercicio:**  
- Selecciona una línea con `V` y cópiala (`y`).  
- Selecciona varias líneas con `V` y bórralas (`d`).  

---

## 8. Deshacer y rehacer
- `u` → deshacer  
- `Ctrl+r` → rehacer  

**Ejercicio:**  
- Borra una línea con `dd`.  
- Usa `u` para recuperarla.  
- Usa `Ctrl+r` para repetir el borrado.  

---

## Recursos adicionales
- `vimtutor` (ejecutar en consola).  
- [Cheatsheet interactivo](https://vim.rtorr.com/).  
- Juego: [Vim Adventures](https://vim-adventures.com/).  


# Revisar Archivos

Podemos mirar (Read Only) archivos con varios comandos como por ejemplo `more` ([man more](https://linux.die.net/man/1/more)):


		more prueba.txt

También está el comando `less` ([man less](https://linux.die.net/man/1/less)):

		less prueba.txt


¿Hay diferencias?

Otro comando es `cat` ([man cat](https://linux.die.net/man/1/cat)):


		cat prueba.txt

> :warning: **NOTA** `cat` es utilizado para concatenar archivos.



> :star: **HACK**:  Cuando quiere escribir un comando o buscar un directorio o escribir el nombre de un archivo, puede utilizar autocompletar con la tecla tab. [Link](https://i.ytimg.com/vi/KEkrWRHCDQU/hqdefault.jpg)


Probemos con el siguiente comando `head`:

		head prueba.txt

o con el comando `tail`:

		tail prueba.txt

Saber el número de palabras:

		wc prueba.txt

Saber el número de lineas:

		wc -l prueba.txt


# Manual

La mayoria de las aplicaciones en Unix tienen una página en el manual de linux `man`, incluso el comando man tiene us propia página en el manual.

		man man 

Con esto es posible parametrizar su aplicación.


Por ejemplo veamos la página del manual para el comando `head`


		man head


¿Qué le imprimirá el siguiente comando?:

		head -n 1 prueba.txt 

# Comando `screen`
## Objetivo
Aprender a usar `screen` en Linux para **gestionar sesiones persistentes**, permitiendo ejecutar procesos en segundo plano, reanudar sesiones y trabajar de manera eficiente en servidores remotos.

---

## 1. ¿Qué es `screen`?
- `screen` es un **multiplexor de terminal**.  
- Permite:  
  - Mantener sesiones activas aunque cierres la terminal.  
  - Tener múltiples "ventanas" dentro de una sola terminal.  
  - Compartir sesiones con otros usuarios.  

**Ejercicio:**  
- Verifica si lo tienes instalado con:  
  ```bash
  screen --version
  ```  
- Si no está, instálalo (ejemplo en Ubuntu/Debian):  
  ```bash
  sudo apt install screen
  ```

---

## 2. Iniciar una sesión
- Crear una sesión nueva:  
  ```bash
  screen
  ```
- Crear una sesión con nombre:  
  ```bash
  screen -S nombreApellido
  ```

---

## 3. Desconectar y reconectar
Dentro de una sesión:  
- **Desconectar** (dejarla en segundo plano):  
  ```
  Ctrl+a d
  ```
- **Listar sesiones activas**:  
  ```bash
  screen -ls
  ```
- **Reconectar a una sesión**:  
  ```bash
  screen -r nombreApellido
  ```

**Ejercicio:**  
1. Inicia una sesión llamada `tareaApellido`.  
2. Desconéctala con `Ctrl+a d`.  
3. Lista las sesiones con `screen -ls`.  
4. Reconéctala con `screen -r tareaApellido`.  

---

## 4. Múltiples ventanas en una sesión
Dentro de una sesión:  
- Crear nueva ventana: `Ctrl+a c`  
- Cambiar ventana:  
  - `Ctrl+a n` (siguiente)  
  - `Ctrl+a p` (anterior)  
  - `Ctrl+a número` (ej: `Ctrl+a 0`)  
- Ver lista de ventanas: `Ctrl+a "`  

👉 **Ejercicio:**  
1. Crea una sesión.  
2. Abre 3 ventanas (`Ctrl+a c` tres veces).  
3. Navega entre ellas con `Ctrl+a n` y `Ctrl+a p`.  
4. Muestra la lista con `Ctrl+a "`.  

---

## 5. Dividir la pantalla
- Dividir horizontal: `Ctrl+a S`  
- Dividir vertical: `Ctrl+a |`  
- Cambiar entre paneles: `Ctrl+a Tab`  
- Cerrar panel: `Ctrl+a X`  

**Ejercicio:**  
- Divide la pantalla en dos con `Ctrl+a S`.  
- Cambia entre paneles con `Ctrl+a Tab`.  
- Cierra un panel con `Ctrl+a X`.  

---

## 6. Cerrar sesión
- Escribir `exit` en la ventana → cierra la ventana actual.  
- Si todas las ventanas cierran → la sesión termina.  
- También se puede terminar desde fuera con:  
  ```bash
  screen -X -S nombreApellido quit
  ```

**Ejercicio:**  
- Cierra una ventana con `exit`.  
- Luego cierra toda la sesión con el mismo comando.  

---

## 7. Compartir una sesión
Permite que **dos usuarios** vean/controlen la misma sesión:  
- Usuario A:  
  ```bash
  screen -S compartida
  ```
- Usuario B:  
  ```bash
  screen -x compartida
  ```

**Ejercicio (opcional en entorno multiusuario):**  
- Crea una sesión compartida y conéctate desde otra terminal con `-x`.  

---

## Recursos adicionales
- Manual oficial: `man screen`  
- [Guía rápida de comandos](https://www.gnu.org/software/screen/manual/screen.html)  
- Tutorial interactivo: [CheatSheet de Screen](https://www.gnu.org/software/screen/)  
