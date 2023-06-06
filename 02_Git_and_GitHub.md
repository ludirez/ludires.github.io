# GitHub

    Crear una cuenta en github y luego configurar git en el PC, reduce la probabilidad que que se generen errores en la configuración .
    por tal motivo empezaremos por ahí.

    1.- Instalar git en la terminal. Ubuntu 20.04	\\wsl$\Ubuntu-20.04\home\username
    	pwd para confirmar el directorio

    	:~$ sudo apt-get install git
    	:~$ git --version       ->a la fecha: 2.25.1

    * Support for password authentication was removed on August 13, 2021.
    	para poder enlazar repositorio local con remoto, anteriormente se podia hacer mediante HTTPS. eso se acabo
    	la forma mas segura es por llaves SSH

->Creando llave SSH. en terminal WSL

    cd ~			->nos llevará de donde estemos al home del WSL
    ssh-keygen -t rsa -b 4096 -C "x"
    	lease asi:
    		ssh-keygen  ->comando
    		-t          ->algoritmo de cifrado de Llave
    		rsa         ->algoritmo usado ene sta ocasión
    		-b          ->tamaño de la llave en bites
    		4096        ->el tamaño asignado en esta ocasión
    		-C "x"      ->frase de codificación donde X es el correo asociado a github
    	muestra la ruta donde se va a guarda la llave, le damos enter
    	pedirá clave adicional. enter en vacío omitirá
    	pedirá reescribir la anterior clave adicional, enter para omitir nuevamente.
    	se ha creado la llave privada y publica.

->configurando llave privada

    cd .shh     					->desplaza a ruta
    ls              				->muestra id_rsa (privada) y id_rsa.pub (publica)
    eval "$(ssh-agent -s)"          ->comprobación. puerto de servidor corriendo nativo en Linux que se encargar encriptar y gestionar als llaves. debe arrojar "agent pid xxxx" donde X es un puerto. si lo muestra, todo ok.
    ssh-add id_rsa           ->identificación privada agregada

    de arrojar error “Could not open a connection to your authentication agent”, procedemos
    exec ssh-agent bash
    ssh-add					->arrojara Identity added

->configurando llave publica en github

    	cat id_rsa.pub

    	->mostrará la key.pub en consola, copiar y pegar en GitHub: Settings ->SSH and GPG keys -> Add New SSH key.

Creamos repositorio y el mismo nos dará la opcion de copiar una ruta SSH. buscamos ese URL y copiamos
vamos a la terminal WSL y donde tengas pensado guardar y mantener tus proyectos:

    git clone xxx@xxx.xxx.git

enseguida se copiará el repo remoto al local.

Para iniciar el flujo de trabajo, se debe tener al menos 1 archivo creado.
/.. $ touch readme.txt con un txt vacío es suficiente.

    - Flujo de trabajo

    	Local: modificaciones de los archivos que están en el equipo
    		git status                      ->lista y muestra en rojo los archivos que se han modificado y guardado en local mas no en git

    	Staging: area virtual previa antes de guardar en git
    		git add x                   ->agrega y muestra en verde el archivo X para ser guardados en git
    		git add .                   ->lo mismo que el anterior, solo que este agrega todos los archivos que estén actualizados en el directorio
    		git status                  ->para verificar nuevamente la lista
    		git rm --cached x           ->para quitar de la lista de staging mas no borra el archivo del dir


    	Commit: Acción que guarda y crea un NumCommit de seguimiento de los cambios en el archivo/proyecto
    		git commit -m "x"           ->donde X es un mensaje descriptivo de lo que se esta actualizando (lleva comillas)

Cada commit es una version de el archivo. con "checkout" se trae devuelta la version que necesitemos con en código de números largos de cada log. ejemplos próximos

Subiendo al Repositorio github:
git push -u origin main

git nos dirá: "tell me how you are" y nos dará instrucciones

Configurar git para enlazarle con github
git config --list --show-origin ->para mostrar usuario configurado
git config --global user.name "NombreDeUsuarioGithub" (incluye comillas)
git config --global user.email CorreoElectrónicoRegistradoEnGithub
git config --list --show-origin ->verificamos lo configurado

    	git config --global --unset 		->comando avanzado para corregir errores en configuraciones

Luego de esta configuración volvemos a hacer push

## iniciando proyecto desde repositorio local:

    2.- Creamos y nos movemos a la carpeta para un nuevo proyecto
    	mkdir nuevoProyecto
    	cd nuevoProyecto

    3.- En consola /...nuevoProyecto$  git init
    	iniciara el seguimiento para todo lo que se haga en la actual carpeta

    4.- Configurar git para enlazarle con github - omitir si ya se ha configurado
    	git config --list --show-origin     ->para mostrar usuario configurado
    	git config --global user.name "NombreDeUsuarioGithub" (incluye comillas)
    	git config --global user.email CorreoElectrónicoRegistradoEnGithub
    	git config --list --show-origin     ->verificamos lo configurado

    	git config --global --unset 		->comando avanzado para corregir errores en configuraciones

    4.1 Para iniciar el flujo de trabajo, se debe tener al menos 1 archivo creado.
    	ya que al se debe hacer un commit antes de empezar el desarrollo para asegurarse que todo esta bien configurado.
    	/.. $ touch readme.txt      con un txt vacío es suficiente.

    5.- Flujo de trabajo

    	Local: modificaciones de los archivos que están en el equipo
    		git status                      ->lista y muestra en rojo los archivos que se han modificado y guardado en local mas no en git

    	Staging: area virtual previa antes de guardar en git
    		git add x                   ->agrega y muestra en verde el archivo X para ser guardados en git
    		git add .                   ->lo mismo que el anterior, solo que este agrega todos los archivos que estén actualizados en el directorio
    		git status                  ->para verificar nuevamente la lista
    		git rm --cached x           ->para quitar de la lista de staging mas no borra el archivo del dir


    	Commit: Acción que guarda y crea un NumCommit de seguimiento de los cambios en el archivo/proyecto
    		git commit -m "x"           ->donde X es un mensaje descriptivo de lo que se esta actualizando (lleva comillas)


    		Cada commit es una version de el archivo. con "checkout" se trae devuelta la version que necesitemos con en código de números largos de cada log. ejemplos próximos

    	Repositorio:
    		git push

## Ramas (branches)

Las Ramas son lineas de desarrollo que se crean para organizar el trabajo en el equipo.
habiendo siempre una linea principal (main o master) y alternas donde se pueden ir desarrollando partes diferentes del proyecto.(dev, debug, footer, etc.)
luego deben unirse lo que se desarrollo en las ramas a la sagrada linea del tiempo principal.
por convención la rama principal default llamada master, se debe renombrar a main.

    	git branch                      ->para ver las ramas creadas y en la que estas parado.
    	git branch branchName           ->Crea nueva rama
    	git checkout branchName         ->para moverse entre ramas. con un git log después del checkout se verá hacia donde apunta el HEAD-> entiéndase,en la rama que estas posicionado.
    	git branch -M NewNameBrach      ->renombra la rama en la que se esta posicionado.
    	git merge branchName			->fusiona la mara actual con la rama que definimos en el comando. siempre nos vamos a traer una copia de la rama que queremos a la rama donde estamos posicionados.

## Repositorio remoto

->Subiendo a repositorio remoto

    	hay que ir a github y crear un repositorio con el mismo nombre del proyecto que vamos a subir.
    git brach -m main
    	->cambiar la rama del repo local de nombre a main. para que coincida con la del repo remoto

    git remote add origin git@github.com:nombreDelRepositorio.git
    	->diciéndole a git que hay un repo remoto llamado origen.

    git remote -v
    	->mostrara direction para hacer "fetch" (subir cosas)
    	->mostrara direction para hacer "push" (enviar cosas)

->Si se debe cambiar o renombrar a donde apunta el origen: unset borra, set sobrescribe.

    git remote set-url origin git@github.com:xxx/xxx.git

## avanzado

    .- Configuración avanzada de git
    	git config --global --unset nombreDelComandoMalEscrito      ->elimina lo que se haya copiado mal en la configuración para ser nuevamente configurado
    																	se puede modificar los parámetros según sea el caso.

    .- Más comandos para git
    	git help                                  ->mostrará más los comandos git y su explicación.
    	git log x                                 ->mostrara el historial de cambios de el archivo X
    	git show x                                ->sin comillas, mostrara lo que se ha cambiado
    	git diff                                  ->Muestra los cambios hechos en el ultimo commit
    	git diff "NumCommit-A" "NumCommit-B"      ->compara a vs b
    	git commit -amend                         ->se usa después de haber hecho un commit y darse cuenta que no se fue un archivo y queremos "reparar" el commit
    												entonces, se hace un git add y luego  el git commit --amend
    												actualizara el ultimo commit y su mensaje sin generar un nuevo NumCommit
    												después de actualizar el mensaje, para salir del editor con las instrucciones del editor, sales y guardas y ya.
    	git reset HEAD                            ->saca los cambios de staging, pero no los borra. Es lo opuesto a git add.

    .- Volver en el tiempo

    .- Más comandos para Ramas
    		git branch -D branchName			-> para eliminar rama
    		git checkout -                 		->te devuelve a la rama anterior activa
    		git show-branch               		->muestra las ramas que hay y el ultimo commit de cada una
    		git show branch --all         		->igual anterior pero con mas detalles
