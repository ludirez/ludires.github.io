## La terminal.

Buscamos en la lista de programas y ejecutamos ubuntu. solo veremos la terminal con el nombre de usuario que creamos durante la instalación.

Recomendaciones Antes de empezar:
Virgulilla -> ~ -> Atl+126

# Básicos para empezar programar

    0.0 :~$ sudo apt-get update					pedirá el PWord configurado en la instalación.
    											buscará las actualizaciones de ubuntu pendiente a la fecha
    0.1	:~$ sudo apt-get upgrade				Instalara lo que haya listado ne el comando anterior. recomendable hacerlo cada dia

    0.2 :~$ explorer.exe .                      ->si un dia te sientes perdido o puedes y quieres agilizar las cosas.

    1. pwd      	user@desk:~$ pwd				Nos indica la ruta estamos
    2. mkdir    	:~$ mkdir carpeta1				Crea un nuevo directorio (carpeta)
    2.2 touch		:~$ touch readme.txt			crea un documento de la extension que necesites
    3. ls       	:~$ ls							Nos lista lo que hay en la carpeta
    4. Ctrl+l		--								limpia la terminal, permitiendo Scroll al pasado
    5. Clear    	:~$ clear						limpia la terminal y todo el chat
    6. cd			:~$ cd carpeta01				(change directory) Avanzará a la carpeta descrita
    7. cd ..		:~$ cd ..						retrocederá en el directorio
    8. code .       :~$ code .                      Abrirá en VScode la carpeta donde estés en el momento de ejecutarlo.
    												Descargará dependencias necesarias para que sea Vscode de Win10 enlazado con WSL
    												Esto permitirá que cuando uses la terminal de Vscode, se ubique en WSL, nuestro actual entorno de trabajo.
    												las extensiones que se instalaron en la configuración inicial, VScode las reconocerá
    												mas te dará un botón para instalarlas para WSL.

# Avanzados

    #. code . -r				->abre VsCode Reciclando la ventada abierta actualmente
    							->sin el -r abrirá siempre una estancia nueva de vscode
