[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0.0-blue)]()

# 🤖 Botsito · Asistente IA (v1.0 Final)

> **Botsito** es un asistente virtual inteligente para la **UNSIS**, diseñado para guiar a los aspirantes en el proceso de inscripción 2026. Combina una **interfaz inmersiva** con el poder de **Botpress** para ofrecer respuestas precisas, conversaciones contextuales y una experiencia visual atractiva.

---

## 📖 Tabla de Contenidos

1. [Descripción General](#1-descripción-general)
2. [Características Principales](#2-características-principales)
3. [Tecnologías y Herramientas Utilizadas](#3-tecnologías-y-herramientas-utilizadas)
4. [Estructura del Proyecto](#4-estructura-del-proyecto)
5. [Guía de Instalación y Uso](#5-guía-de-instalación-y-uso)
6. [¿Cómo Funciona? (Explicación Técnica)](#6-cómo-funciona-explicación-técnica)
7. [Personalización](#7-personalización)
8. [Limitaciones y Advertencias](#8-limitaciones-y-advertencias)
9. [Cómo Contribuir](#9-cómo-contribuir)
10. [Licencia](#10-licencia)

---

## 1. Descripción General

**Botsito** es un asistente conversacional que integra el motor de **NLU (Natural Language Understanding)** de **Botpress** con una interfaz web moderna y atractiva. Su propósito es resolver las dudas más frecuentes sobre el proceso de inscripción 2026 de la **UNSIS**, como:

- 📅 Fechas clave (entrega de fichas, exámenes, curso propedéutico)
- 📋 Requisitos y documentos necesarios
- 📚 Guías de estudio disponibles
- 📞 Contacto y soporte

La interfaz presenta:
- Una **esfera 3D animada** (red neuronal holográfica) que refuerza la estética de IA.
- Un **chat embebido** de Botpress con diseño personalizado.
- **Diseño responsivo** que se adapta a cualquier dispositivo.
- **Sin sidebar ni distracciones**, enfocado completamente en la conversación.

---

## 2. Características Principales

| Característica | Descripción |
| :--- | :--- |
| **🧠 Motor de IA con Botpress** | Responde preguntas complejas usando NLU, con contexto y memoria de conversación. |
| **🌐 Esfera 3D interactiva** | Animación generada con Three.js que simula una red neuronal, con nodos y conexiones en movimiento. |
| **💬 Chat embebido** | Integración del WebChat de Botpress con diseño transparente para combinar con el fondo. |
| **🎨 Interfaz limpia y moderna** | Colores tecnológicos (azul), sin sidebar, centrado en la conversación. |
| **📱 Diseño responsivo** | Se adapta a móviles, tablets y escritorio. |
| **📦 Código autónomo** | Todo en un solo archivo HTML + iframe de Botpress, fácil de modificar y desplegar. |

---

## 3. Tecnologías y Herramientas Utilizadas

| Herramienta | Propósito |
| :--- | :--- |
| **HTML5** | Estructura de la página. |
| **CSS3** | Estilos y animaciones (variables CSS, Flexbox, keyframes). |
| **JavaScript (Vanilla)** | Configuración de la esfera 3D y lógica de redimensionamiento. |
| **Three.js** | Renderizado de la esfera 3D (cargado desde CDN). |
| **Botpress** | Motor de inteligencia artificial (NLU, flujos conversacionales, WebChat). |
| **Fuentes del sistema** | `Segoe UI`, `system-ui`, sans-serif. |

---

## 4. Estructura del Proyecto

El proyecto consta de un único archivo HTML que integra todos los elementos:
botsito-chatbot/
└── V1.2.html # Archivo principal (HTML + CSS + JS)

**Organización interna:**

1. **CSS:** Estilos definidos en el bloque `<style>`.
2. **HTML:** Estructura de la interfaz (esfera 3D y contenedor del chat).
3. **JavaScript:**
   - **Escena 3D:** Configuración de Three.js (nodos, conexiones, animación).
   - **Redimensionamiento:** Función para ajustar la esfera al contenedor.
   - **Integración con Botpress:** El chat se carga mediante un iframe con la URL del WebChat.

---

## 5. Guía de Instalación y Uso

### 5.1 Requisitos Previos

- Un navegador web moderno (Chrome, Firefox, Edge, Safari).
- Conexión a internet (para cargar Three.js y el WebChat de Botpress desde CDN).

### 5.2 Pasos para Ejecutar

1. **Descarga el archivo** clonando este repositorio:

   ```bash
   git clone https://github.com/tu-usuario/botsito-chatbot.git
   cd botsito-chatbot
2. Abre el archivo en tu navegador con un servidor local (no uses file://).
    ve a http://localhost:80/V1.2.html
3. Comienza a interactuar: Escribe tus preguntas en el chat y Botsito responderá usando la inteligencia de Botpress.

6. ¿Cómo Funciona? (Explicación Técnica)
6.1 Integración con Botpress

El chat se carga a través de un iframe que apunta al WebChat de Botpress:
<iframe
  src="https://cdn.botpress.cloud/webchat/v3.6/shareable.html?configUrl=..."
  allow="microphone; camera;"
></iframe>
