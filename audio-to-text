import os
import subprocess
import whisper
import warnings

# Supresión de warnings
warnings.filterwarnings("ignore", category=FutureWarning, module="whisper")
warnings.filterwarnings("ignore", message="FP16 is not supported on CPU")

# Directorios
base_dir = "C:\\xampp\\htdocs\\python\\audio-to-text" #cambia por tu ruta
video_dir = os.path.join(base_dir, "video")
text_dir = os.path.join(base_dir, "text")

# Crear el directorio de texto si no existe
os.makedirs(text_dir, exist_ok=True)

# Cargar el modelo de Whisper
model = whisper.load_model("base")

def extract_audio_with_ffmpeg(video_path, audio_path):
    """
    Extrae el audio de un archivo de video usando FFmpeg.
    """
    try:
        # Comando de extracción con FFmpeg
        command = [
            "ffmpeg",
            "-i", video_path,
            "-q:a", "0",
            "-map", "a",
            audio_path,
            "-y"  # Sobrescribir si ya existe
        ]
        subprocess.run(command, stdout=subprocess.PIPE, stderr=subprocess.PIPE, check=True)
        print(f"Audio extraído: {audio_path}")
    except Exception as e:
        print(f"Error al extraer audio con FFmpeg: {e}")

def transcribe_audio(audio_path):
    """
    Transcribe un archivo de audio a texto usando Whisper.
    """
    result = model.transcribe(audio_path, language="es")
    return result['text']

def process_videos():
    """
    Procesa todos los videos en la carpeta de videos.
    """
    for video_file in os.listdir(video_dir):
        if video_file.endswith(".mp4"):
            video_path = os.path.join(video_dir, video_file)
            audio_path = os.path.join(video_dir, video_file.replace(".mp4", ".wav"))
            text_path = os.path.join(text_dir, f"{os.path.splitext(video_file)[0]}.txt")

            print(f"Procesando: {video_file}")
            
            # Extraer audio del video con FFmpeg
            extract_audio_with_ffmpeg(video_path, audio_path)
            
            # Transcribir el audio
            transcription = transcribe_audio(audio_path)
            
            # Guardar la transcripción en un archivo de texto con el mismo nombre que el video
            with open(text_path, "w", encoding="utf-8") as text_file:
                text_file.write(transcription)
            
            # Eliminar el archivo de audio temporal
            os.remove(audio_path)

            print(f"Transcripción guardada en: {text_path}")

if __name__ == "__main__":
    process_videos()

