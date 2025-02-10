# Linux y Bash Command Cheat Sheet: Lo Básico

## Obtener información

```bash
whoami  # devuelve tu nombre de usuario
id  # return your user and group id  
uname -a  # devolver el nombre del sistema operativo, nombre de usuario y otra información
man top  # display reference manual for a command  
curl --help  # obtener ayuda sobre un comando
date  # devolver la fecha y hora actual
```

## Monitoring performance and status 

```bash
ps  # list selection of or all running processes and their PIDs 
ps -e  # list all running processes and their PIDs
top  # mostrar uso de recursos
df  # list mounted file systems and usage  
```

## Trabajando con archivos

```bash
cp file.txt new_path/new_name.txt  # copiar un archivo
mv this_file.txt that_path/that_file.txt  # change file name or path
rm this_old_file.txt -v  # eliminar un archivo de forma detallada
touch a_new_file.txt  # create an empty file, or update existing file's timestamp  
chmod  +x  my_script.sh  # cambiar/modificar permisos de archivo a ‘ejecutar’ para todos los usuarios
wc  -l table_of_data.csv  # obtener el conteo de líneas en el archivo
wc  -w my_essay.txt  # obtener el conteo de palabras en el archivo
wc  -m some_document.txt  # obtener el conteo de caracteres en el archivo
grep  -iw hello  *.txt  # return lines matching a pattern from files matching a filename pattern - case insensitive and whole words only
grep  -l hello  *.txt  # return file names with lines matching the pattern ‘hello’ from files matching a filename pattern
```

## Navegando y trabajando con directorios

```bash
ls -lrt  # listar archivos y directorios por fecha, más recientes al final
find -name '*.sh'  # find files in directory tree with suffix 'sh'  
pwd  # devolver el directorio de trabajo actual
mkdir new_folder  # make a new directory 
cd ../  # cambiar el directorio actual un nivel arriba
cd ~ o cd  # cambiar al directorio de inicio
cd otro_directorio  # cambiar a otro directorio específico
rmdir temp_directory -v  # eliminar directorio, de manera detallada
```

## Printing file and string contents  

```bash
cat my_shell_script.sh  # print file contents   
more ReadMe.txt  # imprimir el contenido del archivo página por página
head -10 data_table.csv  # imprimir las primeras N líneas del archivo
tail -10 data_table.csv  # print last N lines of file  
echo "No soy un robot"  # imprimir cadena
echo "Soy $USERNAME"  # imprimir el valor de una variable
```

## Compression and archiving  

```bash
tar -cvf my_archive.tar.gz file1 file2 file3  # archive a set of files  
zip my_zipped_files.zip file1 file2  # comprimir un conjunto de archivos
zip my_zipped_folders.zip directory1 directory2  # comprimir un conjunto de carpetas
unzip my_zipped_file.zip  # extract files from a compressed zip archive 
unzip my_zipped_file.zip -d extract_to_this_direcory  # extraer archivos en un directorio específico
```
