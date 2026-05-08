# ⚙️ Manual de Configuración Avanzada del Sistema

Bienvenido al manual de configuración maestra de **NexusCore v4.2**. Este documento detalla exhaustivamente todos los parámetros, variables de entorno y ajustes internos necesarios para adaptar la plataforma a los requisitos específicos de tu organización.

---

## 📑 Índice de Contenidos

- [⚙️ Manual de Configuración Avanzada del Sistema](#️-manual-de-configuración-avanzada-del-sistema)
  - [📑 Índice de Contenidos](#-índice-de-contenidos)
  - [🎨 1. Configuración Visual y de Accesibilidad](#-1-configuración-visual-y-de-accesibilidad)
    - [Opciones de Interfaz](#opciones-de-interfaz)
  - [🌐 2. Ajustes de Red y Conectividad](#-2-ajustes-de-red-y-conectividad)
- [network-config.yml](#network-configyml)

---

## 🎨 1. Configuración Visual y de Accesibilidad

El panel de administración permite una personalización profunda para garantizar que todos los operadores puedan trabajar cómodamente.

### Opciones de Interfaz
*   **Modo de Color:**
    *   `light`: Activa la paleta de colores de alto brillo.
    *   `dark`: Activa la paleta optimizada para entornos de baja luminosidad.
    *   `system-sync`: Automáticamente cambia según la configuración del sistema operativo del usuario.
*   **Densidad de la Información:**
    *   *Compacta:* Reduce los márgenes para mostrar más filas de datos en las tablas.
    *   *Holgada:* Aumenta el espaciado para pantallas táctiles.
*   **Accesibilidad (a11y):**
    *   Modo de alto contraste para personas con daltonismo.
    *   Soporte nativo para lectores de pantalla (activado por defecto).

> **💡 Recomendación Ergonómica:** Para jornadas de trabajo superiores a 6 horas, recomendamos encarecidamente utilizar el **Modo Oscuro** junto con el filtro de luz azul de su monitor.

---

## 🌐 2. Ajustes de Red y Conectividad

Para modificar los parámetros de conexión del servidor interno, deberá editar el archivo principal `network-config.yml`. 

Aquí tiene un ejemplo de la estructura esperada:

```yaml
# network-config.yml
server:
  host: "0.0.0.0"
  port: 8080
  timeout_ms: 15000
  ssl_enabled: true
  cors:
    allowed_origins:
      - "[https://app.nexuscore.dev](https://app.nexuscore.dev)"
      - "[https://admin.nexuscore.dev](https://admin.nexuscore.dev)"
    methods: ["GET", "POST", "PUT", "DELETE"]

proxy:
  enabled: false
  address: "proxy.empresa.local:3128"