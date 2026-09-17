# MoodMeter 📊🎭 — Decodificador de Expresiones Faciales con IA

**MoodMeter** es una aplicación de visión por computadora que utiliza una cámara web o una imagen para analizar expresiones faciales y estimar la distribución de emociones mediante inteligencia artificial.

El proyecto utiliza **FastAPI** como backend, **DeepFace** para el análisis facial y **OpenCV** para el procesamiento de imágenes.

---

## 🧠 ¿Cómo funciona?

El procesamiento de una imagen sigue, de manera general, este flujo:

```text
[ Webcam o imagen ]
        │
        ▼
[ Procesamiento de imagen con OpenCV ]
        │
        ▼
[ Detección y análisis del rostro ]
        │
        ▼
[ DeepFace / modelo de reconocimiento facial ]
        │
        ▼
[ Distribución de emociones ]
        │
        ▼
[ Resultados mostrados en el navegador ]
```

El sistema analiza el rostro detectado y devuelve una distribución de las emociones reconocidas por el modelo.

---

## 📂 Estructura del proyecto

```text
computerV/
├── app/
│   ├── main.py
│   └── templates/
│       ├── index.html
│       └── style.css
├── requirements.txt
├── README.md
└── start.sh
```

### Principales archivos

- `app/main.py`: servidor y API de la aplicación.
- `app/templates/index.html`: interfaz principal.
- `app/templates/style.css`: estilos de la interfaz.
- `requirements.txt`: dependencias necesarias para ejecutar el proyecto.
- `start.sh`: script de inicio disponible para entornos compatibles con Bash.

---

# 🛠️ Instalación

## Requisitos

Antes de comenzar se necesita:

- Python 3.10.
- Git.
- Una cámara web para utilizar la captura en vivo.
- Conexión a Internet para instalar las dependencias y descargar los modelos necesarios de DeepFace durante la primera ejecución.

---

## 1. Clonar el repositorio

Desde una terminal:

```powershell
git clone https://github.com/jonnathanub/computerV.git
```

Entrar al proyecto:

```powershell
cd computerV
```

---

## 2. Crear el entorno virtual

En Windows:

```powershell
python -m venv venv
```

Activar el entorno virtual en PowerShell:

```powershell
venv\Scripts\Activate.ps1
```

Si se utiliza CMD:

```cmd
venv\Scripts\activate
```

Cuando el entorno esté activo, la terminal debe mostrar algo similar a:

```text
(venv) PS C:\...\computerV>
```

---

## 3. Instalar las dependencias

Con el entorno virtual activado:

```powershell
python -m pip install --upgrade pip
```

Después:

```powershell
python -m pip install -r requirements.txt
```

El archivo `requirements.txt` contiene las versiones de las librerías utilizadas para ejecutar y probar el proyecto.

---

# ▶️ Ejecutar la aplicación

Con el entorno virtual activo, ejecutar:

```powershell
python -m uvicorn app.main:app --reload
```

Cuando el servidor se encuentre funcionando, aparecerá un mensaje similar a:

```text
Uvicorn running on http://127.0.0.1:8000
```

Abrir en el navegador:

**http://127.0.0.1:8000**

---

## 🧠 Primera ejecución

Durante la primera ejecución, **DeepFace puede descargar automáticamente los modelos necesarios para realizar el análisis facial**.

Este proceso puede tardar dependiendo de la velocidad de Internet.

Una vez descargados los modelos, las siguientes ejecuciones normalmente no requieren volver a descargarlos.

---

# 📷 Uso de la aplicación

La aplicación permite trabajar con una cámara web o con una imagen.

### Cámara web

1. Abrir la aplicación en el navegador.
2. Permitir el acceso a la cámara cuando el navegador lo solicite.
3. Colocarse frente a la cámara.
4. Ejecutar el análisis.
5. Revisar la distribución de emociones mostrada por la aplicación.

### Imagen

Si no se dispone de cámara web, se puede utilizar la opción para seleccionar una imagen desde el equipo.

---

# 📊 Características

- Captura mediante cámara web.
- Carga de imágenes.
- Detección y análisis facial.
- Distribución de emociones.
- Interfaz web interactiva.
- Visualización de resultados.
- Línea de tiempo para representar los análisis realizados.

---

# ⚙️ Tecnologías utilizadas

- **Python 3.10**
- **FastAPI**
- **Uvicorn**
- **DeepFace**
- **TensorFlow / Keras**
- **OpenCV**
- **NumPy**
- **HTML5**
- **CSS3**
- **JavaScript**

---

# 🔌 API

El proyecto cuenta con un endpoint para realizar el análisis de una imagen:

```text
POST /api/analyze-mood
```

Este endpoint recibe la imagen y procesa el rostro mediante las herramientas de visión por computadora y DeepFace.

---

# ⚠️ Solución de problemas

### La cámara no aparece

Verificar que:

- El navegador tenga permiso para utilizar la cámara.
- Ninguna otra aplicación esté utilizando la cámara.
- El dispositivo tenga una cámara disponible.

También se puede utilizar una imagen cargada desde el equipo.

### Error relacionado con OpenCV

El proyecto utiliza:

```text
opencv-python==4.10.0.84
```

No se debe instalar simultáneamente `opencv-python-headless`, ya que la aplicación utiliza funcionalidades de OpenCV que requieren la instalación completa.

### El servidor no inicia

Comprobar que el entorno virtual esté activo:

```powershell
venv\Scripts\Activate.ps1
```

Después instalar nuevamente las dependencias:

```powershell
python -m pip install -r requirements.txt
```

Y ejecutar:

```powershell
python -m uvicorn app.main:app --reload
```

---

# 👨‍💻 Proyecto

**MoodMeter — Decodificador de Expresiones Faciales con IA**

Proyecto académico de visión por computadora y aprendizaje profundo.
