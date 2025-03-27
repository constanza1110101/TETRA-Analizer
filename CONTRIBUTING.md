Contribuyendo a TETRA Analyzer
¡Gracias por tu interés en contribuir a TETRA Analyzer! Este documento proporciona las directrices para contribuir al proyecto de manera efectiva y consistente.

Consideraciones Éticas y Legales
Antes de contribuir, recuerda que este proyecto está destinado exclusivamente para uso educativo e investigación legal. Todas las contribuciones deben:

No facilitar la interceptación ilegal de comunicaciones privadas
No implementar capacidades de desencriptación de sistemas protegidos
Mantener el enfoque educativo y de investigación en ciberseguridad y radiocomunicaciones
Entorno de Desarrollo
Prerrequisitos
Rust 1.50+ y Cargo
librtlsdr-dev y dependencias
SQLite3
Git
Configuración del Entorno
Clona el repositorio:

bash

Hide
git clone https://github.com/usuario/tetra-analyzer.git
cd tetra-analyzer
Instala las dependencias del sistema:

bash

Hide
# Ubuntu/Debian
sudo apt install librtlsdr-dev libusb-1.0-0-dev libsqlite3-dev

# Fedora/RHEL
sudo dnf install rtl-sdr-devel libusb1-devel sqlite-devel

# Arch Linux
sudo pacman -S rtl-sdr libusb sqlite
Compila el proyecto:

bash

Hide
cargo build
Flujo de Trabajo de Contribución
1. Crear un Issue
Para cambios significativos, comienza creando un issue que describa:

El problema o mejora propuesta
La solución que planeas implementar
Cualquier consideración de diseño relevante
2. Bifurcar (Fork) y Clonar
Haz un fork del repositorio en GitHub
Clona tu fork localmente:
bash

Hide
git clone https://github.com/TU-USUARIO/tetra-analyzer.git
3. Crear una Rama
Crea una rama específica para tu contribución:

bash

Hide
git checkout -b feature/nombre-descriptivo
Usa prefijos como feature/, bugfix/, docs/ según corresponda.

4. Desarrollo
Durante el desarrollo:

Sigue las convenciones de código Rust
Escribe pruebas unitarias para tu código
Asegúrate de que todas las pruebas existentes sigan pasando
Documenta tu código con comentarios y docstrings
Mantén un historial de commits limpio y descriptivo
5. Pruebas
Ejecuta las pruebas antes de enviar tu contribución:

bash

Hide
cargo test
Asegúrate de probar tu código con diferentes configuraciones de hardware SDR si es posible.

6. Enviar un Pull Request
Empuja (push) tus cambios a tu fork:

bash

Hide
git push origin feature/nombre-descriptivo
Crea un Pull Request en GitHub

Describe detalladamente los cambios realizados

Referencia cualquier issue relacionado

Convenciones de Código
Estilo de Código Rust
Sigue el estilo de código Rust estándar (rustfmt)
Ejecuta cargo fmt antes de enviar tu código
Usa cargo clippy para detectar problemas comunes
Convenciones de Nombrado
Usa snake_case para nombres de funciones y variables
Usa CamelCase para nombres de tipos y estructuras
Usa SCREAMING_SNAKE_CASE para constantes
Documentación
Documenta todas las funciones públicas con comentarios ///
Incluye ejemplos en la documentación cuando sea útil
Mantén actualizado el README con cualquier nueva funcionalidad
Estructura del Proyecto
Familiarízate con la estructura del proyecto:

plaintext

Hide
src/
├── main.rs              # Punto de entrada principal
├── analyzer/            # Módulo principal de análisis
│   ├── mod.rs           # Exportaciones del módulo
│   ├── spectrum.rs      # Análisis espectral
│   └── signal.rs        # Procesamiento de señales
├── database/            # Gestión de base de datos
│   └── mod.rs           # Operaciones de base de datos
├── visualization/       # Visualización de datos
│   ├── mod.rs           # Exportaciones del módulo
│   ├── spectrum.rs      # Gráficos de espectro
│   └── waterfall.rs     # Gráficos de espectrograma
├── sdr/                 # Interfaz con hardware SDR
│   └── mod.rs           # Abstracción de dispositivos
└── utils/               # Utilidades generales
    └── mod.rs           # Funciones de utilidad
Áreas de Contribución
Estas son algunas áreas específicas donde las contribuciones son especialmente bienvenidas:

Mejoras de Rendimiento: Optimizaciones para el procesamiento de señales
Detección de Señales: Algoritmos mejorados para identificar señales TETRA
Análisis de Protocolos: Implementación de decodificación de estructuras de trama
Soporte de Hardware: Ampliar compatibilidad con más dispositivos SDR
Visualización: Mejoras en la visualización de datos y espectrogramas
Documentación: Tutoriales, ejemplos y mejoras en la documentación existente
Proceso de Revisión
El proceso de revisión de código incluye:

Revisión automatizada (CI) para comprobar estilo y pruebas
Revisión por pares de la implementación y diseño
Verificación de que la contribución cumple con los objetivos del proyecto
Pruebas en diferentes entornos cuando sea relevante
Comunicación
Para discusiones sobre el desarrollo:

Utiliza los issues de GitHub para preguntas específicas
Para discusiones más amplias, utiliza las Discusiones de GitHub
Mantén un tono respetuoso y constructivo en todas las comunicaciones
Versiones y Changelog
Seguimos Versionado Semántico
Cada contribución significativa debe documentarse en CHANGELOG.md
Las versiones principales se etiquetan en Git
Reconocimiento
Los contribuyentes serán reconocidos en:

El archivo CONTRIBUTORS.md
Las notas de la versión
La documentación del proyecto cuando sea apropiado
Al contribuir a este proyecto, confirmas que tus contribuciones se ajustan a los propósitos educativos y legales del proyecto, y que no tienes la intención de facilitar actividades no autorizadas o ilegales.

Gracias por ayudar a mejorar TETRA Analyzer y por tu compromiso con el desarrollo ético de herramientas de ciberseguridad.
