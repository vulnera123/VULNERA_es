# 🛡️ Vulnera

![Vulnera](docs/assets/vulnera_logo.png)

![Estado](https://img.shields.io/badge/estado-en%20desarrollo-E8433F?labelColor=0D0D0F)
![Python](https://img.shields.io/badge/Python-3.12-3776AB?logo=python&logoColor=white&labelColor=0D0D0F)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?logo=fastapi&logoColor=white&labelColor=0D0D0F)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?logo=postgresql&logoColor=white&labelColor=0D0D0F)
![AWS](https://img.shields.io/badge/AWS-232F3E?logo=amazonwebservices&logoColor=white&labelColor=0D0D0F)

## 📄 Descripción

Vulnera es una plataforma en la nube que analiza la seguridad de un sitio web, detecta fallos de configuración y explica cómo corregirlos. El usuario introduce una dirección y recibe un informe en el que cada hallazgo incluye la evidencia encontrada, su gravedad, el motivo del riesgo y una recomendación.

## ❗ Justificación

Muchas empresas pequeñas publican sitios web sin una auditoría de seguridad previa. Esto provoca errores de configuración básicos y evitables: cabeceras de seguridad ausentes, cookies sin los flags adecuados o certificados TLS débiles o caducados.

El problema no es solo la falta de auditorías. Las herramientas profesionales, como Nessus o Qualys, tienen licencias demasiado caras para una pequeña empresa, y las gratuitas, como OWASP ZAP o Nikto, funcionan de forma aislada, sin panel centralizado ni histórico.

## 🎯 Objetivos

Vulnera no pretende sustituir a esas herramientas ni ser la más completa a nivel técnico. Su propósito es ofrecer una capa accesible y centralizada, con un panel web con login, resultados claros y recomendaciones comprensibles. Para ello se plantean los siguientes objetivos:

- 🔍 Detectar al menos seis tipos de fallos de configuración en un sitio web.
- 📝 Generar para cada hallazgo un informe con evidencia, severidad, referencia OWASP/CWE y recomendación.
- 🗄️ Guardar usuarios, proyectos y escaneos en una base de datos y conservar el histórico.
- 🌐 Ofrecer un panel web con login seguro, en inglés con selector de idioma EN/ES.
- ☁️ Desplegar la plataforma en AWS con una red segmentada, HTTPS, copias de seguridad y monitorización.

## 🛠️ Tecnologías

El motor de análisis, la API y el CLI están escritos en **Python**, por su cantidad de librerías para peticiones HTTP, análisis TLS y parseo de HTML. La API usa **FastAPI**, que es rápido de desarrollar y genera su propia documentación. Los datos (usuarios, proyectos, escaneos y hallazgos) se guardan en **PostgreSQL**, elegido por su solidez con las relaciones entre tablas y su soporte de JSON para la evidencia de cada hallazgo. El panel web es ligero, con **HTML, CSS y JavaScript**, e **i18next** para el cambio de idioma entre inglés y español.

La infraestructura se despliega en **AWS** (VPC, EC2, Security Groups y snapshots) sobre **Ubuntu Server**, con **Nginx** como reverse proxy y HTTPS mediante **Let's Encrypt**. En local se trabaja con **VirtualBox** y **Docker**, y las pruebas se hacen contra **DVWA** y **OWASP Juice Shop** en un laboratorio aislado. La instalación, los backups y los escaneos programados se automatizan con **Bash** y **cron**.

El trabajo se organiza con **Git** y **GitHub** (código y documentación), **Jira** (tablero Kanban) y **draw.io** y **Mermaid** (diagramas).

## ✨ Funcionalidades

- 🔎 Análisis de una URL: cabeceras de seguridad, cookies, TLS, banners de servidor, formularios sin protección CSRF y directorios expuestos.
- 📋 Informe por hallazgo con evidencia, severidad, referencia OWASP/CWE y recomendación.
- 🔐 Login seguro, proyectos por usuario e histórico de escaneos en la nube.
- 🔄 Comparación entre dos escaneos de un mismo proyecto.
- 🖥️ Panel web oscuro y minimalista, en inglés con selector EN/ES, y CLI con salida limpia.
- ⏰ Escaneos programados y despliegue en AWS con HTTPS, copias de seguridad y monitorización.

## 📅 Planificación

El proyecto sigue seis fases: planificación inicial, análisis y diseño, desarrollo, pruebas, despliegue y mantenimiento. El trabajo se reparte en tareas semanales y el detalle de cada una está en Jira.

- 🚩 **v0.1 (MVP):** CLI con tres checks, a mediados de diciembre de 2026.
- 🚩 **v0.2:** motor completo con tests, a finales de enero de 2027.
- 🚩 **v0.3:** API con login y base de datos, a principios de marzo.
- 🚩 **v0.4:** panel web con selector de idioma, a finales de marzo.
- 🏁 **v1.0:** despliegue completo en AWS, a mediados de mayo.

## 🚧 Estado actual del proyecto

**Fase 1: planificación inicial.** El anteproyecto está redactado y el tablero de Jira y el repositorio están creados. Quedan por completar la planificación de tareas, el diagrama de AWS, los prototipos y la página web.

## 📐 Diseño técnico

- 🗺️ Modelo Entidad-Relación *(pendiente de enlazar)*
- 🎨 Prototipo de interfaz *(pendiente de enlazar)*
- ☁️ Arquitectura de red en AWS *(en elaboración)*

## 🔗 Enlaces

- 📌 [Tablero de Jira](https://joseantoniomartinezvazquez.atlassian.net/jira/software/projects/VUL/list)
- 🌍 [Web del proyecto](https://ajosmarvaz-cmyk.github.io/VULNERA_es/)

---

> ⚠️ **Aviso legal.** Vulnera solo debe utilizarse sobre sitios web propios o con autorización expresa de su propietario. El autor no se hace responsable del uso indebido de la herramienta.
