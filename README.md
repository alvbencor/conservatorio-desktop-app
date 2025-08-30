# conservatorio-desktop-app

## 1. Objetivo del Proyecto

El proyecto consiste en desarrollar una **aplicación de escritorio** para la gestión integral de un conservatorio de música, abarcando las siguientes funcionalidades principales:

### Funcionalidades Core
- **Gestión académica**: Administración completa de alumnos, profesores, asignaturas y matrículas
- **Infraestructura**: Control de aulas, biblioteca y cabinas de estudio
- **Especialidades**: Gestión de plazas por especialidad e instrumentación
- **Automatización**: Importación de datos desde archivos Excel con validación automática
- **Reportes**: Generación de informes y adjudicación automática de plazas

### Características Clave
> **Aplicación portable, multiplataforma y sin dependencias externas**
> 
> Diseñada para ejecutarse en cualquier ordenador sin necesidad de instalar bases de datos o servicios adicionales.

---

## 2. Stack Tecnológico

### 🎨 Frontend / Interfaz de Usuario

#### Tecnologías Principales
- **Electron** - Plataforma para aplicaciones de escritorio multiplataforma
- **HTML5, CSS3 y JavaScript (ES6+)** - Base de la interfaz aprovechando componentes existentes
- **React con Vite** *(Opcional - Evolución futura)* - Componentización y escalabilidad mejorada

#### 📌 Justificación
- **Portabilidad total**: Electron permite empaquetar como `.exe` (Windows), `.app` (macOS) o binario Linux
- **Curva de aprendizaje mínima**: El equipo ya domina tecnologías web
- **Escalabilidad**: Migración futura a React sin reescribir la base
- **Sin dependencias**: No requiere navegador ni servidor externo

### ⚙️ Backend / Lógica de Negocio

#### Tecnología Core
- **Node.js** (integrado en Electron) - Motor de ejecución de la lógica empresarial

#### Capacidades
- Acceso completo a librerías NPM
- Manipulación de archivos y recursos del sistema
- Procesamiento de datos embebido

#### 📌 Justificación
- **Lógica integrada**: Validación de Excel, adjudicación de plazas y generación de reportes en JavaScript
- **Arquitectura simplificada**: Sin necesidad de levantar servidores independientes
- **Rendimiento**: Toda la lógica embebida en la aplicación

### 💾 Persistencia de Datos

#### Motor de Base de Datos
- **SQLite** con `better-sqlite3`
  - Motor embebido, ligero y portable
  - Almacenamiento en archivo único (`conservatorio.db`)

#### 📌 Justificación
- **Cero configuración**: Sin instalación de servidores adicionales
- **Ideal para educación**: Máxima portabilidad y simplicidad
- **Funcionalidad completa**: Consultas SQL avanzadas y escalabilidad
- **Migración futura**: Fácil transición a MySQL/PostgreSQL si se requiere centralización

### 📊 Importación y Validación

#### Herramientas Especializadas
- **xlsx (SheetJS)** - Procesamiento nativo de archivos Excel
- **Sistema de validación** - Verificación de cabeceras y formatos pre-importación

#### 📌 Justificación
- **Compatibilidad nativa**: Procesamiento directo de datos de alumnos y plazas en Excel
- **Prevención de errores**: Validación temprana garantiza consistencia en base de datos

### 📦 Distribución y Portabilidad

#### Herramientas de Empaquetado
- **electron-builder** / **electron-packager**
  - Generación de instaladores multiplataforma
  - Versiones portables (`.exe`, `.app`, `.deb`)

#### Características de Distribución
- Base de datos SQLite incluida en el paquete
- Instalaciones completamente autónomas

#### 📌 Justificación
- **Independencia total**: Instalación en cualquier ordenador sin configuraciones externas
- **Actualizaciones simplificadas**: Distribución mediante nuevo ejecutable

---

## 3. Resumen de Decisiones Arquitectónicas

| Decisión | Alternativa Descartada | Justificación |
|----------|------------------------|---------------|
| **Electron** | Aplicación web tradicional | Garantiza portabilidad y disponibilidad offline |
| **SQLite embebida** | MySQL/PostgreSQL | Elimina dependencias externas y simplifica gestión |
| **HTML+JS base** | Framework pesado inicial | Mantiene simplicidad con evolución gradual a React |
| **Arquitectura monolítica** | Cliente-servidor | Prioriza simplicidad y portabilidad sobre complejidad distribuida |

### Principios de Diseño
1. **Simplicidad ante todo**: Minimizar dependencias y configuraciones
2. **Portabilidad máxima**: Funcionamiento en cualquier entorno sin instalaciones adicionales  
3. **Escalabilidad gradual**: Arquitectura que permite crecimiento sin reescrituras masivas
4. **Autonomía operativa**: Independencia total de servicios externos o conectividad

---

## Próximos Pasos

1. **Configuración del entorno Electron**
2. **Implementación del esquema de base de datos SQLite**
3. **Desarrollo de módulos de importación Excel**
4. **Creación de interfaces de gestión básicas**
5. **Sistema de validación y reportes**
