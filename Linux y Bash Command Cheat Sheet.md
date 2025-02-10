Linux y Bash Command Cheat Sheet: Lo Básico
Obtener información
# devuelve tu nombre de usuario

whoami 
\# return your user and group id  
``` bash
id  
# devolver el nombre del sistema operativo, nombre de usuario y otra información

uname -a   
\# display reference manual for a command  
``` bash
man top  
# obtener ayuda sobre un comando

curl --help  
# devolver la fecha y hora actual

date  
### Monitoring performance and status 
---
\# list selection of or all running processes and their PIDs 
``` bash
ps  
ps -e 
# mostrar uso de recursos

top  
\# list mounted file systems and usage  
``` bash
df
Trabajando con archivos
# copiar un archivo

cp file.txt new_path/new_name.txt
# change file name or path

mv this_file.txt that_path/that_file.txt
# eliminar un archivo de forma detallada

rm this_old_file.txt -v
\# create an empty file, or update existing file's timestamp  
``` bash
touch a_new_file.txt  
# cambiar/modificar permisos de archivo a ‘ejecutar’ para todos los usuarios

chmod  +x  my_script.sh
# obtener el conteo de líneas, palabras o caracteres en el archivo

wc  -l table_of_data.csv  
wc  -w my_essay.txt  
wc  -m some_document.txt 
\# return lines matching a pattern from files matching a filename pattern - case insensitive and whole words only
``` bash
grep  -iw hello  \*.txt 
# return file names with lines matching the pattern ‘hello’ from files matching a filename pattern

grep  -l hello  \*.txt
Navegando y trabajando con directorios
# listar archivos y directorios por fecha, más recientes al final

ls -lrt 
\# find files in directory tree with suffix 'sh'  
``` bash
find -name '\*.sh'
# devolver el directorio de trabajo actual

pwd
\# make a new directory 
``` bash
mkdir new_folder  
# cambiar el directorio actual: un nivel arriba, inicio, o alguna otra ruta

cd ../  
cd ~ o cd  
cd otro_directorio
`\# eliminar directorio, de manera detallada`
rmdir temp_directory -v
### Printing file and string contents  
--- 
\# print file contents   
``` bash
cat my_shell_script.sh 
# imprimir el contenido del archivo página por página

more ReadMe.txt  
# imprimir las primeras N líneas del archivo

head -10 data_table.csv
\# print last N lines of file  
``` bash
tail -10 data_table.csv
# imprimir cadena o valor de variable

echo "No soy un robot" 
echo "Soy $USERNAME"  
### Compression and archiving  
---
\# archive a set of files  
``` bash
tar -cvf my_archive.tar.gz file1 file2 file3
# comprimir un conjunto de archivos

zip my_zipped_files.zip file1 file2 
zip my_zipped_folders.zip directory1 directory2
\# extract files from a compressed zip archive 
``` bash
unzip my_zipped_file.zip 
unzip my_zipped_file.zip -d extract_to_this_direcory
Performing network operations
# print hostname

hostname  
# enviar paquetes a la URL y imprimir la respuesta

ping  www.google.com
\# display or configure system network interfaces  
``` bash
ifconfig  
ip 
# mostrar el contenido del archivo en una URL

curl  <url>
\# download file from a URL  
``` bash
wget  <url>
Shebang de Bash
#!/bin/bash

Tuberías y Filtros
# encadenar comandos de filtro utilizando el operador de tubería

ls | sort -r  
\# pipe the output of manual page for ls to head to display the first 20 lines  
``` bash
man ls | head -20  
Shell y Variables de Entorno
# listar todas las variables del shell

set  
\# define a shell variable called my_planet and assign value Earth to it  
``` bash
my_planet=Earth  
# mostrar variable de shell

echo $my_planet  
\# list all environment variables  
``` bash
env
# variables de entorno: definir/extender el alcance de las variables a procesos hijos

export my_planet  
export my_galaxy='Vía Láctea'
 
### Metacharacters  
---
\# comments  
`# The shell will not respond to this message`  
\# command separator  
``` bash
echo 'here are some files and folders'; ls
# expansión de nombre de archivo comodín

ls *.json  
\# single character wildcard   
``` bash
ls file_2021-06-??.json
Citando
# comillas simples - interpretar literalmente

echo 'Mi directorio personal se puede acceder ingresando: echo $HOME'
\# double quotes - interpret literally, but evaluate metacharacters  
``` bash
echo "My home directory is $HOME"
# barra invertida - interpretación del metacaracter de escape

echo "Este signo de dólar debería renderizar: \$"
### I/O Redirection   
---
\# redirect output to file  
``` bash
echo 'Write this text to file x' > x
# agregar salida al archivo

echo 'Agrega esta línea al archivo x' >> x
\# redirect standard error to file 
``` bash
bad_command_1 2> error.log
# agregar error estándar al archivo

bad_command_2 2>> error.log  
\# redirect file contents to standard input  
``` bash
$ tr “[a-z]” “[A-Z]” < a_text_file.txt 
# la redirección de entrada anterior es equivalente a

$cat a_text_file.txt | tr “[a-z]” “[A-Z]”
### Command Substitution    
---
\#  capture output of a command and echo its value  
``` bash
THE_PRESENT=$(date) 
echo "There is no time like $THE_PRESENT"
Argumentos de línea de comandos
./My_Bash_Script.sh arg1 arg2 arg3
### Batch vs. concurrent modes 
---
\#  run commands sequentially  
``` bash
start=$(date); ./MyBigScript.sh ; end=$(date)
# ejecutar comandos en paralelo

./ETL_chunk_one_on_these_nodes.sh  & ./ETL_chunk_two_on_those_nodes.sh 
## Scheduling jobs with Cron
---
\# open crontab editor  
``` bash
crontab -e  
# sintaxis de programación de trabajos

m  h  dom  mon  dow   comando 
_minute, hour, day of month, month, day of week_  
`*` means any    
\# append the date/time to file every Sunday at 6:15 pm   
``` bash
15 18 * * 0 date >> sundays.txt
# ejecutar un script de shell en el primer minuto del primer día de cada mes

1  0 1 * * ./My_Shell_Script.sh
\# back up your home directory every Monday at 3 am  
``` bash
0 3 * * 1  tar -cvf my_backup_path\my_archive.tar.gz $HOME\
# despliega tu trabajo cron
Cierra el editor de crontab y guarda el archivo

# lista todos los trabajos cron

crontab -l
