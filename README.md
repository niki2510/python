# python
Proyectos en Python

Para trabajar con los videos o audio a veces hace falta sacar texto de video o audio.

Situaciones: 
* Mejorar posicionamiento de nuestro video short en youtube (no existe para short transcripcion de video en modo que podemos sacar el texto)
* Este texto se puede mejorar (sin aumentar cantidad de palabras) con las herramientas de la inteligencia artificial.
* Un vez sacado texto podemos añadirlo en short video de modo manual y activar traduccion automatica a otras idiomas que elegimos.

  Como funciona este codigo:

  * Videos guarda en la carpeta 'video'
  * Codigo analiza el video y saca audio
  * Audio se convierte en el texto (nombre de cada fichero del texto es el mismo nombre que tiene cada video).
  * Ficheros del texto se guarda en la carpeta 'texto'

Solucion:

Querarquia de las carpetas y ficheros:<br>
C:\xampp\htdocs\python\audio-to-text
├── video
│   ├── video1.mp4
│   ├── video2.mp4
│   ├── mi_video_increíble.mp4
│   └── otro_video.mp4
├── text
│   ├── video1.txt
│   ├── video2.txt
│   ├── mi_video_increíble.txt
│   └── otro_video.txt
└── transcribe_video.py
-----------------------------------------------------
Descarga ffmpeg:  https://www.ffmpeg.org/download.html
Copia y pega este archivo comprimido en el directorio: C:\ (o cualquier otro directorio)
Si usas windows: inicio -> escribe 'Variables de Entorno -> haz clic en 'varibles de entorno' -> 'Nuevo' -> Nombre de variable  'ffmpeg' -> Valor de la variable: 'C:\ffmpeg-7.1'-> 'Aceptar -> 'Aceptar'
Si usas linux busca como poner path :

ffmpeg -version #(comprueba si tienes ffmpeg y que versión)
sudo apt update
sudo apt install ffmpeg
which ffmpeg #encontrar la ruta de ffmpeg
/usr/bin/ffmpeg #probablemente te devuelve esta ruta
nano ~/.bashrc #vamos a agregar path
export PATH="/usr/bin:$PATH"    #añadimos la ruta
source ~/.bashrc  #Recarga la configuración del shell
ffmpeg -version  #Prueba la Configuración

Tienes que instalar bibliotecas:
pip install openai-whisper
pip install moviepy
pip install --upgrade moviepy  #si hace falta









