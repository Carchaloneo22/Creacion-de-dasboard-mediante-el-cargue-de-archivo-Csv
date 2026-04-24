# 📊 Dashboards de la Secretaría del Interior - Bucaramanga

Este repositorio contiene dos dashboards interactivos diseñados para el monitoreo y análisis de:

1. **Actividades Programadas** – Visión integral de actividades de diferentes dependencias.
2. **Prevención de Violencia** – Seguimiento a estrategias de prevención (Somos Familia, Creciendo Seguros, etc.).

Ambos dashboards permiten cargar archivos CSV, aplicar filtros dinámicos y visualizar indicadores clave a través de gráficos, tablas y métricas. Están construidos con tecnologías web estándar (HTML5, CSS3, JavaScript) y librerías como Chart.js, ApexCharts y PapaParse.

---

## 📁 Estructura de Archivos

- `dashboard_actividades.html` – Dashboard de Actividades Programadas.
- `dashboard_prevencion_violencia.html` – Dashboard de Prevención de Violencia.
- `ACTIVIDADESPROGRAMAD_DATA_LABELS_*.csv` – Ejemplo de datos para el primer dashboard.
- `PREVENCINDEVIOLENCIA_DATA_LABELS_*.csv` – Ejemplo de datos para el segundo dashboard.
- `README.md` – Este archivo.

---

## 🎯 Diagramas de Casos de Uso

### Dashboard de Actividades Programadas

```mermaid
graph TD
    A[Usuario] -->|Carga CSV| B(Dashboard Actividades)
    A -->|Aplica Filtros| B
    A -->|Visualiza KPIs| B
    A -->|Explora Tablas| B
    
    B -->|Solicita procesamiento| C[Sistema de Parsing CSV]
    C -->|Devuelve datos estructurados| B
    
    B -->|Genera gráficos| D[Chart.js / ApexCharts]
    B -->|Genera paginación| E[Tabla dinámica]

graph TD
    U[Usuario] -->|Carga CSV| DPV(Dashboard Prevención)
    U -->|Filtra por línea/estado/zona/responsable| DPV
    U -->|Consulta impacto poblacional| DPV
    
    DPV -->|Procesa datos| Parser[PapaParse]
    Parser -->|Datos normalizados| DPV
    
    DPV -->|Actualiza gráficos| Charts[Chart.js / ApexCharts]
    DPV -->|Muestra desglose de género, cobertura| UI[Componentes personalizados]

classDiagram
    class Actividad {
        +string recordId
        +string dependencia
        +date fechaProgramada
        +string horaInicio
        +string horaFin
        +string lineaEstrategica
        +string estado
        +string lugar
        +string zona
        +string responsable
        +string telefono
    }
    class Dashboard {
        +list~Actividad~ actividades
        +filterByDependencia(valor) list
        +filterByEstado(valor) list
        +filterByZona(valor) list
        +getKPIs() object
        +updateCharts()
    }
    Dashboard --> Actividad<img width="4619" height="1772" alt="deepseek_mermaid_20260424_65a940" src="https://github.com/user-attachments/assets/5d8e54ac-1c4b-4ca8-8f14-334fbee3c6d0" />

 Instrucciones de Uso
Para ambos dashboards
Abrir el archivo .html en un navegador moderno (Chrome, Edge, Firefox).

Cargar el CSV haciendo clic o arrastrando el archivo correspondiente al área de carga.

Actividades Programadas → archivo ACTIVIDADESPROGRAMAD_DATA_LABELS_*.csv

Prevención de Violencia → archivo PREVENCINDEVIOLENCIA_DATA_LABELS_*.csv

Aplicar filtros (dependencia, estado, zona, responsable, mes, etc.) para segmentar los datos.

Explorar indicadores clave, gráficos y tablas.

Paginación en la tabla completa para navegar entre registros.


Tecnologías Utilizadas
HTML5 / CSS3 – Estructura y estilos responsivos.

JavaScript (ES6) – Lógica de procesamiento y manipulación del DOM.

Chart.js – Gráficos de barras, líneas, pie y doughnut.

ApexCharts – Gráficos de dona, áreas y personalizados.

PapaParse – Parsing de archivos CSV en el cliente.

Font Awesome 6 – Iconografía.

Google Fonts (Inter, Sora) – Tipografía.
