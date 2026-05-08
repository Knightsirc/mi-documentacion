# 🚀 Guía de Despliegue en Producción

Este documento detalla los procedimientos estandarizados para desplegar **NexusCore v4.2** en entornos de producción (Staging y Producción). Siga estas instrucciones rigurosamente para garantizar un despliegue sin tiempo de inactividad (Zero-Downtime) y mantener la máxima seguridad.

---

## 📑 Índice de Contenidos

- [🚀 Guía de Despliegue en Producción](#-guía-de-despliegue-en-producción)
  - [📑 Índice de Contenidos](#-índice-de-contenidos)
  - [🛑 1. Consideraciones Previas](#-1-consideraciones-previas)
  - [🏗️ 2. Compilación del Proyecto (Build)](#️-2-compilación-del-proyecto-build)
- [Limpiar cachés previas e instalar solo dependencias de producción](#limpiar-cachés-previas-e-instalar-solo-dependencias-de-producción)
- [Ejecutar el script de construcción](#ejecutar-el-script-de-construcción)

---

## 🛑 1. Consideraciones Previas

Antes de iniciar cualquier proceso de despliegue, el ingeniero a cargo debe verificar el siguiente *checklist* de seguridad y rendimiento:

- [ ] La rama de Git a desplegar (`main` o `release`) ha pasado todos los tests automatizados.
- [ ] Las variables de entorno de producción están actualizadas y seguras (Vault/AWS Secrets).
- [ ] Se ha realizado un *backup* completo de la base de datos PostgreSQL en la última hora.
- [ ] El equipo de QA ha firmado el *Release Note*.

> **⚠️ ADVERTENCIA CRÍTICA:** Nunca utilice la base de datos o las credenciales de desarrollo/staging en el entorno de producción. Verifique siempre que la variable `NODE_ENV` está estrictamente configurada como `production`.

---

## 🏗️ 2. Compilación del Proyecto (Build)

Para entornos donde no se utilicen contenedores pre-construidos, es necesario compilar el código fuente para optimizar el rendimiento (minificación de *assets*, eliminación de código muerto, etc.).

Ejecute el siguiente comando en el servidor de destino:

```bash
# Limpiar cachés previas e instalar solo dependencias de producción
npm ci --only=production

# Ejecutar el script de construcción
npm run build