# tfm_call_optimizer
Ponganle wendy!

# Proyecto de Optimización de Audios

Este proyecto está diseñado para procesar y optimizar archivos de audio. El código incluye varias etapas de procesamiento de audios, como la normalización de volumen, la eliminación de silencios, la conversión de formatos y el filtrado de archivos según su duración.

## Estructura del Proyecto

El proyecto está organizado en varias carpetas y un notebook:

/Audios_prueba1 # Carpeta con los archivos de audio de entrada (formato .WAV o .MP3) 
/Audios_mp3 # Carpeta donde se guardarán los archivos convertidos o procesados (formato .MP3) 
/Audios_respaldo # Carpeta donde se moverán los archivos de audio que no cumplen con los umbrales de duración /Limpieza_Audios.ipynb # Notebook que contiene los pasos de procesamiento y limpieza de los audios

## Requisitos

Para ejecutar el proyecto correctamente, debes instalar las siguientes librerías:

- `pydub` - Para manipulación y conversión de archivos de audio.
- `os` - Para operaciones del sistema de archivos.
- `shutil` - Para mover los archivos a diferentes carpetas.
- `ffmpeg` - Utilizado por `pydub` para convertir archivos de audio de un formato a otro.
- `librosa` (si se necesita análisis avanzado de audio).
- `soundfile` (si se manipula audio sin comprimir como WAV).
- `pyaudio` (si se requiere grabación o reproducción en tiempo real, aunque no se usa en este proyecto).
- `ffmpeg-python` - Interfaz de Python para `ffmpeg`, usado para la conversión de archivos WAV a MP3.

Puedes instalar las dependencias necesarias utilizando `pip`:

```bash
pip install pydub librosa soundfile pyaudio ffmpeg-python

Uso
Preparación de las carpetas:

Coloca tus archivos de audio en la carpeta Audios_prueba1.

El código procesará estos archivos, los convertirá a MP3 (si es necesario), y los guardará en la carpeta Audios_mp3.

Si algún archivo no cumple con los criterios de duración (menos de 50 segundos o más de 300 segundos), será movido a la carpeta Audios_respaldo.

Ejecuta el notebook:

Abre el archivo Limpieza_Audios.ipynb para revisar y ejecutar los pasos de procesamiento. Este notebook incluye:

Conversión de archivos de audio de WAV a MP3.

Normalización del volumen de los archivos MP3.

Eliminación de silencios en los archivos de audio.

Filtrado de archivos según su duración.

Flujo de trabajo del código:

Paso 1: Los archivos de audio de la carpeta Audios_prueba1 son procesados. Si son archivos WAV, se convierten a MP3.

Paso 2: Se normaliza el volumen de los archivos MP3.

Paso 3: Se eliminan los silencios innecesarios de los archivos MP3.

Paso 4: Los archivos con duraciones fuera del rango especificado (menos de 50 segundos o más de 300 segundos) se mueven a la carpeta Audios_respaldo.

Paso 5: Los archivos que cumplen con el rango de duración se mantienen en Audios_mp3.

Funciones del Código
Conversión de formato (WAV a MP3):

Utiliza ffmpeg para convertir archivos de audio de formato WAV a MP3, asegurándose de que el formato de archivo sea uniforme para un procesamiento posterior.

Normalización de volumen:

Los archivos MP3 son normalizados para ajustar el volumen al nivel de referencia, mejorando la consistencia en el volumen entre diferentes archivos.

Eliminación de silencios:

Utiliza la librería pydub para eliminar silencios al principio, en medio y al final de los archivos MP3, mejorando la calidad y el contenido del audio.

Filtrado por duración:

Los archivos de audio son filtrados según su duración. Si un archivo es demasiado corto o largo, se mueve a una carpeta de respaldo Audios_respaldo.

Notebooks
El archivo Limpieza_Audios.ipynb contiene los siguientes pasos:

Carga de los archivos de audio.

Conversión de los archivos de formato WAV a MP3.

Normalización del volumen.

Eliminación de silencios de los audios.

Filtrado de los archivos según su duración.

