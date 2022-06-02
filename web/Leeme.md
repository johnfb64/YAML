Con los roles se puede crear una estructura de ficheros y directorios
para separar los elementos, permite ser revisados facilmente y es posible descargar 
roles predefinidos. 


Se crea la siguiente estructura:

carpeta raiz /web
 + Dentro de web se crea el archivo ansible, en este caso instalar.yml
 + A nivel de del playbook en web, se crea la carpeta roles (mkdir roles).
   + En roles se crea la carpeta apache 2 (mkdir apache2)
     + apache2
     - Dentro de apache2 se crean las carpetas (mkdir) files templates tasks handlers
       + files
       - Dentro de files esta el archivo apache2.conf
       + templates
       - Se deja el archivo index.html.j2 con un mensaje.
       + tasks
       - Se define fichero main.yml para instalar apache
       + handlers
       - se define fichero main.yml para reinicar servicio apache. este es un handler. 




Se tiene la siguiente estructura:
find .

./instalar.yml
./Leeme.md
./roles
./roles/apache2
./roles/apache2/files
./roles/apache2/files/apache2.conf
./roles/apache2/handlers
./roles/apache2/handlers/main.yml
./roles/apache2/tasks
./roles/apache2/tasks/main.yml
./roles/apache2/templates
./roles/apache2/templates/index.html.j2

Se puede hacer un chequeo al archivo previamente: ansible-playbook --syntax-check instalar.yml 

Este proceso se ejecuta con: ansible-playbook instalar.yml -k

El proceso se ejecuto sobre un equipo y funciono perfectamente! Ver jpg. 