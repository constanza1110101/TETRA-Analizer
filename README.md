TETRA Analyzer
Herramienta avanzada para análisis de señales TETRA en Rust
SOLO PARA USO EDUCATIVO E INVESTIGACIÓN LEGAL

TETRA Analyzer

Descripción
TETRA Analyzer es una herramienta de análisis de radiofrecuencia implementada en Rust, especializada en la detección, monitorización y análisis de señales TETRA (Terrestrial Trunked Radio). Esta herramienta de alto rendimiento aprovecha la velocidad y seguridad de memoria de Rust para proporcionar análisis en tiempo real de señales digitales profesionales.

Características principales
Alto rendimiento: Implementado en Rust para máxima eficiencia y uso óptimo de recursos
Análisis espectral en tiempo real: Visualización del espectro de radiofrecuencia con FFT optimizado
Escaneo de banda completa: Detección automática de señales en rangos configurables
Clasificación de señales: Identificación de señales TETRA, DMR, PMR y otros sistemas digitales
Análisis de modulación: Detección automática de esquemas de modulación (π/4-DQPSK, QAM, etc.)
Generación de espectrogramas: Visualización de actividad de señal a lo largo del tiempo
Base de datos SQLite: Almacenamiento persistente de señales detectadas
Exportación JSON: Exportación de resultados para análisis posterior
Visualización avanzada: Gráficos de espectro y waterfall de alta calidad
Requisitos del sistema
Rust 1.50+
RTL-SDR, HackRF, o dispositivo SDR compatible
librtlsdr instalado en el sistema
SQLite3
Instalación
Asegúrate de tener Rust y Cargo instalados:

bash

Hide
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
Instala las dependencias del sistema:

bash

Hide
# Ubuntu/Debian
sudo apt install librtlsdr-dev libusb-1.0-0-dev libsqlite3-dev

# Fedora/RHEL
sudo dnf install rtl-sdr-devel libusb1-devel sqlite-devel

# Arch Linux
sudo pacman -S rtl-sdr libusb sqlite
Clona el repositorio:

bash

Hide
git clone https://github.com/usuario/tetra-analyzer.git
cd tetra-analyzer
Compila el proyecto:

bash

Hide
cargo build --release
Uso
Escaneo de banda TETRA
bash

Hide
./tetra-analyzer --scan --start 380 --end 400 --step 0.025 --gain 30
Monitoreo de frecuencia específica
bash

Hide
./tetra-analyzer --monitor --frequency 395.0 --duration 120 --gain 30
Opciones disponibles
--scan: Activar modo de escaneo de banda
--monitor: Activar modo de monitoreo de frecuencia específica
--start: Frecuencia inicial en MHz para escaneo (predeterminado: 380)
--end: Frecuencia final en MHz para escaneo (predeterminado: 400)
--step: Tamaño de paso en kHz (predeterminado: 25)
--frequency: Frecuencia a monitorear en MHz
--duration: Duración del monitoreo en segundos (predeterminado: 60)
--gain: Ganancia en dB (predeterminado: 30)
Estructura de archivos generados
plaintext

Hide
output/
├── scans/                   # Resultados de escaneos
│   ├── tetra_scan_*.json    # Datos de escaneo en formato JSON
│   └── spectrum_plot_*.png  # Gráficos del espectro detectado
├── monitoring/              # Resultados de monitoreo
│   └── waterfall_*MHz_*.png # Espectrogramas de monitoreo
└── database/                # Base de datos SQLite
    └── tetra_analyzer.db    # Almacenamiento persistente
Ejemplo de salida JSON
json

Hide
{
  "start_freq": 380000000,
  "end_freq": 400000000,
  "step_size": 25000,
  "signals": [
    {
      "frequency": 395000000,
      "power": -45.3,
      "bandwidth": 25000,
      "timestamp": "2023-07-15T14:23:45+00:00",
      "classification": "TETRA",
      "modulation": "π/4-DQPSK"
    },
    {
      "frequency": 396025000,
      "power": -52.1,
      "bandwidth": 25000,
      "timestamp": "2023-07-15T14:24:12+00:00",
      "classification": "TETRA",
      "modulation": "π/4-DQPSK"
    }
  ],
  "scan_time": 32.5,
  "device_info": "RTL-SDR device index: 0, gain: 30",
  "timestamp": "2023-07-15T14:25:00+00:00"
}
Limitaciones legales
Esta herramienta:

Solo realiza monitoreo pasivo del espectro radioeléctrico
No implementa capacidades de desencriptación de comunicaciones protegidas
No está diseñada para interferir con sistemas de comunicaciones operativos
El uso de esta herramienta debe cumplir con las regulaciones locales sobre radiocomunicaciones. En muchos países, la interceptación de comunicaciones no autorizadas es ilegal, incluso con fines de investigación.

Rendimiento
TETRA Analyzer está optimizado para un rendimiento superior:

Procesamiento FFT de alta velocidad
Uso eficiente de memoria gracias a Rust
Análisis en tiempo real con baja latencia
Carga CPU optimizada para operación continua
Contribuciones
Las contribuciones son bienvenidas a través de pull requests. Para cambios importantes, abra primero un issue para discutir su propuesta.

Licencia
Este proyecto está licenciado bajo la Licencia MIT - vea el archivo LICENSE para más detalles.

Descargo de responsabilidad
Este software se proporciona "tal cual", sin garantía de ningún tipo. Los autores no son responsables del uso indebido o ilegal de esta herramienta. Este proyecto tiene fines exclusivamente educativos y de investigación en ciberseguridad.

TETRA Analyzer - Desarrollado para investigación y educación en ciberseguridad
