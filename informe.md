# Práctica No. 1: Comandos de Linux

**Nombre:** Carlos Zhuzhingo

**Fecha:** 12 de octubre de 2026

## 1. Título

Crear carpetas y trabajar con archivos en Linux.

## 2. Tiempo de duración

Aproximadamente 25 minutos.

## 3. Fundamentos

En esta práctica se usan comandos para crear carpetas y trabajar con archivos desde la terminal. La terminal es una ventana donde escribimos lo que queremos que haga el computador. Para esta práctica usé Git Bash en Windows, donde pude trabajar con los comandos que pide la tarea.

Las carpetas ayudan a mantener los archivos ordenados. En este caso, proyecto_comandos es la carpeta principal y dentro se crean documentos, imagenes y scripts. El comando mkdir sirve para crear estas carpetas. Con cd se entra en una carpeta para trabajar dentro de ella. Antes de crear o mover un archivo, hay que revisar en qué carpeta estamos para no guardarlo en otro lugar.

Los archivos de texto sirven para guardar lo que escribimos. Con touch se puede crear un archivo vacío y con echo se pueden escribir líneas de texto. El comando cat permite leer lo que contiene el archivo y revisar si las líneas se guardaron bien. En notas.txt se escribieron tres líneas relacionadas con la práctica.

Para guardar texto se usan los símbolos > y >>. El primero escribe en el archivo, pero reemplaza lo que tenía antes. El segundo agrega texto al final y conserva las líneas anteriores. Esto sirve para crear el resumen y agregar una línea nueva sin perder las notas que ya estaban guardadas.

El comando cp sirve para copiar un archivo sin borrar el original. Al hacer la copia, también se le puede poner otro nombre. El comando mv se usa para mover un archivo de una carpeta a otra. Para borrar un archivo se usa rm. Para borrar una carpeta vacía, se usa rmdir. Por eso, primero se borra el respaldo y después la carpeta imagenes.

Con history se pueden ver los comandos que se usaron. El símbolo |, llamado tubería, pasa la salida de un comando a otro. Al escribir history | tee seguido del nombre del archivo, el historial se muestra en la terminal y también se guarda. En este archivo quedan guardados los comandos que usamos durante la práctica.

![Estructura de las carpetas](evidencias/estructura.png)

*Figura 1. Organización de las carpetas y archivos de la práctica.*

## 4. Conocimientos previos

- Abrir Git Bash y escribir comandos.
- Reconocer archivos y carpetas.
- Subir archivos a un repositorio de GitHub.

## 5. Objetivos a alcanzar

- Crear las carpetas y archivos que pide la tarea.
- Copiar, cambiar de nombre, mover y borrar archivos.
- Guardar texto y agregar líneas sin borrar lo que ya estaba escrito.
- Guardar el historial de comandos usando una tubería.

## 6. Equipo necesario

- Computador con Windows y Git Bash.
- Conexión a Internet y cuenta de GitHub.
- Teléfono o micrófono para grabar el audio.

## 7. Material de apoyo

- Indicaciones de la tarea autónoma de la semana 1.
- [Plantilla del informe](https://github.com/maguaman2/informe-tendencias/blob/main/informe.md).
- Manuales de Bash y de los comandos usados.

## 8. Procedimiento

### Paso 1. Crear las carpetas

Creé la carpeta proyecto_comandos. Dentro de ella creé documentos, imagenes y scripts.

```bash
mkdir proyecto_comandos
cd proyecto_comandos
mkdir documentos imagenes scripts
```

### Paso 2. Crear, copiar y mover el archivo

En documentos creé notas.txt y escribí tres líneas. Después lo copié a scripts con el nombre backup_notas.txt y moví la copia a imagenes.

```bash
touch documentos/notas.txt
echo "Primera linea: aprendo a crear carpetas en Linux." > documentos/notas.txt
echo "Segunda linea: practico la manipulacion de archivos." >> documentos/notas.txt
echo "Tercera linea: utilizo redireccionamiento desde Bash." >> documentos/notas.txt
cat documentos/notas.txt
cp documentos/notas.txt scripts/backup_notas.txt
mv scripts/backup_notas.txt imagenes/backup_notas.txt
```

### Paso 3. Crear el resumen y agregar una línea

Creé resumen.txt en documentos y guardé ahí el texto de notas.txt. Después agregué una cuarta línea usando >> para no borrar las tres primeras.

```bash
touch documentos/resumen.txt
cat documentos/notas.txt > documentos/resumen.txt
echo "Cuarta linea: agrego informacion sin sobrescribir el contenido." >> documentos/resumen.txt
cat documentos/resumen.txt
```

### Paso 4. Borrar el respaldo y la carpeta imagenes

Borré backup_notas.txt. Revisé que imagenes estuviera vacía y después borré la carpeta.

```bash
rm imagenes/backup_notas.txt
ls -A imagenes
rmdir imagenes
```

### Paso 5. Guardar el historial

Guardé el historial con mi nombre usando una tubería. Ejecuté el comando desde proyecto_comandos; ../ permite guardar el archivo fuera de esa carpeta, junto al informe.

```bash
history | tee ../tarea-s1-Carlos_Zhuzhingo.txt
```

El historial está en [tarea-s1-Carlos_Zhuzhingo.txt](tarea-s1-Carlos_Zhuzhingo.txt).

## 9. Resultados esperados

Después de hacer los pasos, notas.txt quedó con tres líneas y resumen.txt con cuatro. El resumen tiene las tres líneas de las notas y la que agregué al final. Borré backup_notas.txt y la carpeta imagenes. La carpeta scripts quedó vacía.

Las carpetas y archivos quedaron así:

```text
proyecto_comandos/
├── documentos/
│   ├── notas.txt
│   └── resumen.txt
└── scripts/ (vacía)
```

![Resultado final de la práctica](evidencias/03-resultado-final.png)

*Figura 2. Resultado final mostrado en el visor del registro de Git Bash.*

El informe y el historial están guardados en el repositorio. También está el [audio de 60 segundos en MP3](tarea-s1-Carlos_Zhuzhingo.mp3), donde explico lo aprendido.

## 10. Bibliografía

- Free Software Foundation. (s. f.). *Bash reference manual*. GNU Project. https://www.gnu.org/software/bash/manual/bash.html
- Free Software Foundation. (s. f.). *GNU Coreutils manual*. GNU Project. https://www.gnu.org/software/coreutils/manual/coreutils.html
- maguaman2. (s. f.). *informe-tendencias* [Plantilla de informe]. GitHub. https://github.com/maguaman2/informe-tendencias
