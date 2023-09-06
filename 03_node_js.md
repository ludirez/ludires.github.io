## node.js para desarrollo frontend.

    README_: instalación dirigida a entorno de trabajo en WSL.

    verificamos si hay versión anterior instalada:
    	$ node -v		si la hay. debemos eliminarla
    		como eliminar nodejs de ubuntu (si le llego a intalar)
    			-> ~$ sudo apt-get purge nodejs (tarda unos minutos)
    			-> ~$ sudo apt remove nodejs (este comando es mejor apra desinstalar jodejs)
    			-> ~$ sudo apt autoremove (tarda unos minutos)

debemos instalar node version manager. explicación del porque y todas las instrucciones, acá:
https://learn.microsoft.com/es-mx/windows/dev-environment/javascript/nodejs-on-wsl

    $ cd ~

    instalando CURL para poder instalar cosas desde URLs
    $ curl --version 		->para saber si hay version instalada
    $ sudo apt-get install curl			->para instalar curl

    $ curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.3/install.sh | bash		->instalar nvm

se debe reiniciar la terminal para terminar la instalación. luego ejecutamos
$ command -v nvm ->debe devolver nvm y estará todo bien.

    $ nvm list or $nvm ls	->dan o mismo, lista de versiones de node.js instaladas. no deberia de haber niguna instalada en este momento.
    $ nvm install --lts		->instalara la ultima version estable de nodejs.
    $ nvm ls				-> verificando que nvm esta trabajando bien, mostrando una lista de las posibles versiones para instalar y sus nombre.
    		$ nvm install lts/dubnium		->instalará es version lts/dubnium
    		$ nvm ls-remote					-> mostrara el historial y todas las versiones disponibles.
    $ node --version		-> comprobamos version de nodejs seleccionada para trabajar
    $ npm --version			-> verificamos version de node package manager instalada

Nota, los de Microsoft aconsejan instalar la extension Remote Development en VsCode para mejor experiencia.

# Intercambiar versiones de NodeJS

Cada vez que quieras cambiar la versión de NodeJS que tienes activa lanzarás el comando "nvm use", seguido de la versión que sea o su nombre. Por ejemplo podríamos lanzar el "use" con el nombre "default", que suele ser la última versión más reciente, con el comando siguiente:
$ nvm use default

Podemos usar una versión con un nombre dado:
$ nvm use lts/carbon

O una versión con su número exacto:
$ nvm use v16.3.0

más información util por aca :
https://desarrolloweb.com/home/nvm#track268

instalado y configurado node.js para futuros desarrollos.
