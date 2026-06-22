[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0.0-blue)]()

# 🤖 Botsito · Asistente IA (v1.2 Final)

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
   git clone https://github.com/David-DARC/ChatBot-V1.1
   cd botsito-chatbot
2. Abre el archivo en tu navegador con un servidor local (no uses file://).
    ve a http://localhost:80/V1.2.html
3. Comienza a interactuar: Escribe tus preguntas en el chat y Botsito responderá usando la inteligencia de Botpress.


## 6. ¿Cómo Funciona? (Explicación Técnica)
6.1 Integración con Botpress

El chat se carga a través de un iframe que apunta al WebChat de Botpress:
<iframe
  src="https://cdn.botpress.cloud/webchat/v3.6/shareable.html?configUrl=..."
  allow="microphone; camera;"
></iframe>
El iframe se comunica directamente con el bot alojado en Botpress Cloud, el cual utiliza:

    NLU para entender la intención del usuario.

    Flujos conversacionales para guiar la conversación.

    Base de conocimiento (documentos PDF y URL de la UNSIS) para responder preguntas específicas.

6.2 Esfera 3D (Three.js)

    Se crea una escena con una cámara en perspectiva.

    Se distribuyen 220 nodos en la superficie de una esfera usando el método de Fibonacci para una cobertura uniforme.

    Se dibujan conexiones entre nodos cercanos (distancia < 0.7) para simular una red neuronal.

    Se añade un núcleo interior con un efecto de pulsación.

    La escena rota continuamente y se renderiza en el canvas HTML.

6.3 Interfaz de Usuario

    Diseño minimalista: sin sidebar ni distracciones, enfocado en la conversación.

    Responsiva: la esfera y el chat se redimensionan automáticamente.

    Colores tecnológicos: tonos azules que transmiten confianza y modernidad.

## 7. Personalización
Cambiar el nombre del asistente

Modifica el <title> y el texto del hint en el HTML:
<title>Botsito · Asistente IA</title>
<div class="hint">Botsito puede cometer errores. Verifica información importante.</div>

Modificar colores

Edita las variables CSS en :root:
:root {
  --primary: #0066cc;      /* Color principal */
  --primary-dim: #003d99;  /* Color secundario */
  --line: #1a3a5c;         /* Color de bordes */
}

Cambiar el tamaño de la esfera

Ajusta max-width en .orb y finalSize en la función resizeCanvas():
.orb {
  max-width: 600px; /* Cambia este valor */
}
const finalSize = Math.min(size, 600); // Cambia este valor

Actualizar la URL del WebChat

Reemplaza el src del iframe con la URL de tu bot publicada en Botpress.
## 8. Limitaciones y Advertencias

    Dependencia de internet: El chat y la esfera 3D se cargan desde CDN. Sin conexión, la página no funcionará completamente.

    El chat es externo: La lógica conversacional está alojada en Botpress Cloud; cualquier cambio en el comportamiento del bot debe hacerse desde la plataforma Botpress.

    El historial no se guarda localmente: Las conversaciones se gestionan en Botpress, no en el navegador.

## 9. Cómo Contribuir

Las contribuciones son bienvenidas. Si deseas mejorar este proyecto:

    Haz un fork del repositorio.

    Crea una rama para tu función (git checkout -b feature/nueva-funcion).

    Realiza tus cambios y haz commit (git commit -m 'Añade nueva funcionalidad').

    Sube tus cambios (git push origin feature/nueva-funcion).

    Abre un Pull Request.
Si tienes preguntas o sugerencias, puedes abrir un issue en este repositorio.

## ¡Gracias por usar Botsito! 🚀
