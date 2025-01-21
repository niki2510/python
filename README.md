# python
Proyectos en Python<br>

Para trabajar con los videos o audio a veces hace falta sacar texto de video o audio.<br>

Situaciones: <br>
* Mejorar posicionamiento de nuestro video short en youtube (no existe para short transcripcion de video en modo que podemos sacar el texto)<br>
* Este texto se puede mejorar (sin aumentar cantidad de palabras) con las herramientas de la inteligencia artificial.<br>
* Un vez sacado texto podemos añadirlo en short video de modo manual y activar traduccion automatica a otras idiomas que elegimos.<br>

  Como funciona este codigo:<br>

  * Videos guarda en la carpeta 'video'<br>
  * Codigo analiza el video y saca audio<br>
  * Audio se convierte en el texto (nombre de cada fichero del texto es el mismo nombre que tiene cada video).<br>
  * Ficheros del texto se guarda en la carpeta 'texto'<br>

Solucion:<br>

Querarquia de las carpetas y ficheros:<br>
C:\xampp\htdocs\python\audio-to-text<br>
├── video<br>
│   ├── video1.mp4<br>
│   ├── video2.mp4<br>
│   ├── mi_video_increíble.mp4<br>
│   └── otro_video.mp4<br>
├── text<br>
│   ├── video1.txt<br>
│   ├── video2.txt<br>
│   ├── mi_video_increíble.txt<br>
│   └── otro_video.txt<br>
└── transcribe_video.py<br>
-----------------------------------------------------
Descarga ffmpeg:  https://www.ffmpeg.org/download.html<br>
Copia y pega este archivo comprimido en el directorio: C:\ (o cualquier otro directorio)<br>
Si usas windows: <br>
#inicio -> escribe 'Variables de Entorno -> haz clic en 'varibles de entorno' -> 'Nuevo' -> Nombre de variable  'ffmpeg' -> Valor de la variable: 'C:\ffmpeg-7.1'-> 'Aceptar -> 'Aceptar'<br>
Si usas linux busca como poner path :<br>

ffmpeg -version #(comprueba si tienes ffmpeg y que versión)<br>
sudo apt update<br>
sudo apt install ffmpeg<br>
which ffmpeg #encontrar la ruta de ffmpeg<br>
/usr/bin/ffmpeg #probablemente te devuelve esta ruta<br>
nano ~/.bashrc #vamos a agregar path<br>
export PATH="/usr/bin:$PATH"    #añadimos la ruta<br>
source ~/.bashrc  #Recarga la configuración del shell<br>
ffmpeg -version  #Prueba la Configuración<br>

Tienes que instalar bibliotecas:<br>
pip install openai-whisper<br>
pip install moviepy<br>
pip install --upgrade moviepy  #si hace falta<br><br>









