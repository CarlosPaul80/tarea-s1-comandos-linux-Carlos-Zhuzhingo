# Práctica No. 1: Comandos de Linux

**Nombre:** Carlos Zhuzhingo

**Fecha:** 12 de octubre de 2026

## 1. Título

Creación y manipulación de archivos con comandos de Linux.

## 2. Tiempo de duración

Menos de 1 minuto para ejecutar los comandos. La lectura, elaboración del informe y grabación del audio no se cronometraron.

## 3. Fundamentos

La terminal permite trabajar con el computador escribiendo comandos. Bash interpreta esas instrucciones y ejecuta las acciones indicadas. Para esta práctica se utilizó Git Bash en Windows, una de las opciones de la tarea. Este programa incluye herramientas que también se usan en Linux para crear carpetas, escribir texto y organizar archivos. Cada comando tiene un nombre y puede recibir argumentos, como la ruta del archivo con el que se desea trabajar.

Los directorios sirven para agrupar archivos. Una ruta indica dónde se encuentra cada elemento. Por ejemplo, documentos/notas.txt señala un archivo dentro de la carpeta documentos. El comando pwd muestra la ubicación actual y cd cambia de directorio. Con mkdir se crean carpetas, mientras que touch crea un archivo vacío si todavía no existe. Es importante revisar la ubicación antes de ejecutar una orden, porque las rutas relativas dependen del directorio actual.

El comando echo escribe texto y cat permite consultar el contenido de un archivo. Para guardar la salida se puede utilizar el símbolo >. Este crea el archivo si no existe y sobrescribe su contenido cuando ya existe. En cambio, >> añade información al final sin borrar lo anterior. En la práctica, esta diferencia permitió escribir las tres líneas de notas.txt y luego añadir una cuarta línea al resumen.

Para copiar archivos se utiliza cp. La copia puede recibir otro nombre al indicar su destino. El original permanece en su ubicación. El comando mv permite mover un archivo a otra carpeta o cambiarle el nombre. Por su parte, rm elimina archivos y rmdir elimina carpetas vacías. Antes de usar rmdir conviene revisar el contenido con ls -A, que también muestra archivos ocultos.

Una tubería se representa con | y permite pasar la salida de un comando como entrada de otro. El comando history muestra las órdenes registradas en la sesión de Bash. Al conectarlo con tee, el historial se muestra en la terminal y se guarda en un archivo. Así queda un registro de los pasos realizados que se puede consultar y subir junto con el informe.

![Estructura de las carpetas](evidencias/estructura.png)

*Figura 1. Carpetas y archivos utilizados en la práctica.*

## 4. Conocimientos previos

- Uso básico de la terminal.
- Diferencia entre archivos, carpetas y rutas.
- Manejo básico de GitHub.

## 5. Objetivos a alcanzar

- Crear carpetas y archivos de texto.
- Copiar, mover y eliminar archivos.
- Utilizar redirecciones y tuberías.
- Guardar el historial y presentar los resultados en GitHub.

## 6. Equipo necesario

- Computador con Windows y Git Bash.
- Conexión a Internet y cuenta de GitHub.
- Micrófono o teléfono para grabar el audio.

## 7. Material de apoyo

- Indicaciones de la tarea de la semana 1.
- [Plantilla del informe](https://github.com/maguaman2/informe-tendencias/blob/main/informe.md).
- Manuales de GNU Bash y GNU Coreutils.

## 8. Procedimiento

### Paso 1. Crear las carpetas

Desde el directorio de trabajo se creó proyecto_comandos con tres subcarpetas. Se usó el nombre imagenes, sin tilde, de acuerdo con la estructura inicial de la consigna.

```bash
mkdir proyecto_comandos
cd proyecto_comandos
mkdir documentos imagenes scripts
```

### Paso 2. Crear y manipular notas.txt

Se creó el archivo, se escribieron tres líneas y se copió a scripts con el nombre backup_notas.txt. Luego se movió la copia a imagenes.

```bash
touch documentos/notas.txt
echo "Primera linea: aprendo a crear carpetas en Linux." > documentos/notas.txt
echo "Segunda linea: practico la manipulacion de archivos." >> documentos/notas.txt
echo "Tercera linea: utilizo redireccionamiento desde Bash." >> documentos/notas.txt
cp documentos/notas.txt scripts/backup_notas.txt
mv scripts/backup_notas.txt imagenes/backup_notas.txt
```

### Paso 3. Crear el resumen

Se pasó el contenido de notas.txt a resumen.txt y se añadió una línea sin sobrescribir las anteriores.

```bash
touch documentos/resumen.txt
cat documentos/notas.txt > documentos/resumen.txt
echo "Cuarta linea: agrego informacion sin sobrescribir el contenido." >> documentos/resumen.txt
```

### Paso 4. Eliminar el respaldo y la carpeta vacía

```bash
rm imagenes/backup_notas.txt
ls -A imagenes
rmdir imagenes
```

Después de borrar el respaldo, ls -A no mostró archivos. Por eso se pudo eliminar imagenes con rmdir.

### Paso 5. Guardar el historial

Desde proyecto_comandos se ejecutó:

```bash
history | tee ../tarea-s1-Carlos_Zhuzhingo.txt
```

La tubería pasó el historial a tee, que lo mostró y lo guardó junto al informe. El [archivo del historial](tarea-s1-Carlos_Zhuzhingo.txt) incluye los comandos de la práctica y las comprobaciones realizadas.

## 9. Resultados esperados

Se obtuvieron los resultados solicitados: notas.txt quedó con tres líneas y resumen.txt con cuatro. Las primeras tres líneas del resumen coinciden con las notas. El respaldo y la carpeta imagenes se eliminaron, mientras que scripts quedó vacía.

```text
proyecto_comandos/
├── documentos/
│   ├── notas.txt
│   └── resumen.txt
└── scripts/ (vacía)
```

![Resultado final de la práctica](evidencias/03-resultado-final.png)

*Figura 2. Captura del visor de la salida registrada en Git Bash. El registro completo está en [sesion-terminal.txt](evidencias/sesion-terminal.txt).*

Git no guarda carpetas vacías; por eso scripts aparece en la evidencia, pero no en los archivos del repositorio.

Se adjunta el [audio en MP3 de 60 segundos](tarea-s1-Carlos_Zhuzhingo.mp3) sobre lo aprendido.

## 10. Bibliografía

- Free Software Foundation. (s. f.). *Bash reference manual*. GNU Project. https://www.gnu.org/software/bash/manual/bash.html
- Free Software Foundation. (s. f.). *GNU Coreutils manual*. GNU Project. https://www.gnu.org/software/coreutils/manual/coreutils.html
- maguaman2. (s. f.). *informe-tendencias* [Plantilla de informe]. GitHub. https://github.com/maguaman2/informe-tendencias
