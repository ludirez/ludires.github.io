## Prepacion para empezar a programar desde Win 10 con WSL con Git and Github

03-05-2023

El siguiente tutorial te llevara eficazmente a configurar un entorno en windows apto para aprender a programar en local y remoto.

El camino No es corto, asi que disfruta el viaje.

Recomendaciones para el camino
deja todo en ingles.
aprende ingles
si usas traductor, al menos ponle interés en aprender la estructura y frases que estas traduciendo.
no le tengas miedo a la terminal.
lee toda la instrucción y luego ejecuta.
aprende a usar el ataje Alt+Tab. los atajos de teclado son tu mejor amigo ahora.

Recomendaciones para cada dia de trabajo.
no estudies sin haber dormido bien o con sueño.
no estudies con hambre
si no entiendes algo es porque desconoces el significado e alguna palabra, revisa el glosario o investiga y luego continua desde un párroco antes
practica, practica, practica y practica.
no te rindas tan fácilmente

Glosario:
->Windows Subsystem for Linux WSL: característica de windows que termine ejecutar de manera optima, un entorno Linux a través de una terminal, sin salir del entorno windows.

    	->Repositorio: Almacén de cosas

    	->GitHub: repositorio de código versionado en Git y almacenado en la nube

    	->Nube: eso que esta y puedes acceder desde y en cualquier parte del mundo.

    	->Git: software que permite administrar () versiones de código.

1️⃣.-Configuring entorno Windows;
.-Habilitar WSL:
->Panel de control
->Desinstalar un programa
->Activar o desactivar características de Windows:
->Buscar al final de la lista y activar:
✅ Plataforma de maquina virtual
✅ Subsistema de Windows para Linux
Se debe reiniciar el S.O.
Debemos asegurarnos que el el BIOS de el equipo este habilitado la virtualization
google. ¿cómo saber si esta habilitado la visualización en mi pc?

.-Iniciar Cuenta en GitHub
->Importante configurar autenticación de 2 pasos.
->Importante crear, guardar y tener presente los "github-recovery-codes"

.-Descargar VsCode
->Al iniciar, saldrá un aviso para instalar Extension de WSL para VsCode. Install

.-Iniciar sesión en VsCode & sincronizar with Github

.-Instalar Windows PowerShell desde Microsoft store

.-instalar Ubuntu LTS:
-ir a Microsoft Store y buscar la ultima version LTS.
al momento de este tutorial "ubuntu 20.04.06 LTS.

-Ejecutar Ubuntu:
configura, guarda y memoriza: usuario y password
recomendación: nombre corto de usuario
recomendación: cambiar el nombre del Equipo, acorta aun mas el texto en la ruta inicial de la terminal

.-Actualizar WSL a WSL 2. desde la terminal Windows powerShell
:> wsl --list --verbose ->muestra name: nombre de la distribución de Linux instalada. State: NPI. Version: la version actual del WSL
:> wsl --set-version ubuntu-20-04 2 con este actualizamos versión de 1 a 2
comprobamos nuevamente con wsl -l -v

2️⃣.-Configurando entorno trabajo
.-Instalar Extensiones en Vs code:

    			->WSL for microsoft		->se instala automáticamente cuando detecta WSL en el S.O

    			->Material Icon Theme: ayuda a identificar visualmente con un icono los tipos de archivos.

    			->Code Spell Checker: Evitaremos errores en escritura

    			->Spanish - Code Spell Checker Evitaremos errores en escritura en español
    					-copiar la siguiente linea->    ,"cSpell.language": "en,es",
    					-ir a la rueda de configuraciones y entrar en settings
    					-esquina superior derecha, icono de documento que al posar el cursor sombre él, diga: Open Setting (JSON)
    					-pegar lo copiado en la ultima line entre las llaves, Ctrl+s para guardar cambios. esto habilitara la corrección del ingles y del español.
    					-Ctrl+. sobre la palabra resaltada para mostrar lista de corrección.

    			->Live Server: para visualizar App web en tiempo real.

    			->Prettier - Code Formatter
    					>agregar en el Open Setting (JSON) -> "editor.formatOnSave": true,

    			->Auto Rename Tag
    			->code runner .run
    			->git Graph
    			->Palenight Theme
    			->Path Intellisense
    			->HTML CSS Support
    			->JavaScript (ES6) code snippets

3️⃣ Lo siguiente en la ruta:
->Terminal
->Git and Github
->HTML & CSS
->Bootstrap 5
->JavaScript
