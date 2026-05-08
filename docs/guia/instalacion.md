# 🚀 Guía de Instalación y Despliegue Local

Bienvenido a la documentación oficial de instalación de **NexusCore v4.2**. Este documento le guiará paso a paso a través del proceso de configuración del entorno de desarrollo o servidor local para ejecutar la plataforma de manera óptima.

---

## 📑 Índice de Contenidos

1. [Requisitos del Sistema](#1-requisitos-del-sistema)
2. [Preparación del Entorno](#2-preparación-del-entorno)
3. [Instalación Paso a Paso](#3-instalación-paso-a-paso)
4. [Despliegue Rápido con Docker](#4-despliegue-rápido-con-docker)
5. [Verificación y Arranque](#5-verificación-y-arranque)
6. [Solución de Problemas Frecuentes (FAQ)](#6-solución-de-problemas-frecuentes-faq)

---

## 💻 1. Requisitos del Sistema

Antes de comenzar, asegúrese de que su máquina o servidor cumple con los requisitos mínimos para compilar y ejecutar NexusCore sin cuellos de botella.

### Requisitos de Hardware

| Componente | Mínimo | Recomendado (Producción) |
| :--- | :--- | :--- |
| **Procesador (CPU)** | 2 Cores (ej. Intel i3 / AMD Ryzen 3) | 4+ Cores (ej. Intel i7 / AMD Ryzen 7) |
| **Memoria (RAM)** | 4 GB | 16 GB |
| **Almacenamiento** | 10 GB de espacio libre (SSD) | 50 GB de espacio libre (NVMe) |
| **Red** | Conexión a internet de banda ancha | Conexión simétrica de 1 Gbps |

### Requisitos de Software

*   **Sistema Operativo:** Ubuntu 22.04 LTS, macOS Monterey (o superior), Windows 11 (usando WSL2).
*   **Node.js:** Versión `18.17.0` (LTS) o superior.
*   **Base de Datos:** PostgreSQL `14.x` o superior.
*   **Gestor de paquetes:** `npm` (v9+) o `yarn` (v1.22+).

---

## 🛠️ 2. Preparación del Entorno

Si aún no tiene Node.js o Git instalados, le recomendamos utilizar un gestor de versiones como `nvm` (Node Version Manager) para evitar conflictos de permisos.

Para verificar que tiene las herramientas correctas, ejecute estos comandos en su terminal:

```bash
node -v
# Esperado: v18.17.0 o superior

npm -v
# Esperado: 9.6.7 o superior

git --version
# Esperado: git version 2.34.1 o superior