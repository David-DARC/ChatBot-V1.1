[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Version](https://img.shields.io/badge/version-1.0.0-blue)]()

# 🧠 ORÁCULO · Asistente IA (v1.0 - Prototipo)

> **Nota:** Esta es la **versión 1.0 (prototipo)** del asistente. La versión final será desarrollada sobre la plataforma **Botpress** para ofrecer una experiencia más robusta, escalable y con inteligencia artificial avanzada.

---

## Tabla de Contenidos

1. [Descripción General](#1-descripción-general)
2. [Estado del Proyecto y Hoja de Ruta](#2-estado-del-proyecto-y-hoja-de-ruta)
3. [Características Actuales](#3-características-actuales)
4. [Tecnologías y Herramientas Utilizadas](#4-tecnologías-y-herramientas-utilizadas)
5. [Estructura del Proyecto](#5-estructura-del-proyecto)
6. [Guía de Instalación y Uso](#6-guía-de-instalación-y-uso)
7. [¿Cómo Funciona? (Explicación Técnica)](#7-cómo-funciona-explicación-técnica)
8. [¿Por qué migrar a Botpress?](#8-por-qué-migrar-a-botpress)
9. [Cómo Contribuir](#9-cómo-contribuir)
10. [Licencia](#10-licencia)

---

## 1. Descripción General

**ORÁCULO** es un asistente virtual interactivo diseñado para resolver dudas sobre el proceso de inscripción 2026 de la UNSIS. En su versión actual, es un prototipo funcional construido como una sola página HTML que combina:

- Un **motor de respuestas básico** basado en palabras clave.
- Una **interfaz de usuario inmersiva** con temática futurista.
- Una **esfera 3D animada** (simulando una red neuronal) para reforzar la estética de inteligencia artificial.

El objetivo principal de este prototipo es validar el concepto, la interfaz y el flujo de información antes de embarcarse en el desarrollo de una versión profesional sobre **Botpress**.

---

## 2. Estado del Proyecto y Hoja de Ruta

- **Estado Actual (v1.0):** Prototipo funcional para validación de concepto.
- **Próximos Pasos (v2.0):** Migración completa a la plataforma **Botpress**.
  - **Motivación:** La versión actual, aunque útil para pruebas, es limitada. No mantiene contexto de conversación, su "inteligencia" es puramente estática y no es escalable.
  - **Plan:** Reconstruir el asistente en Botpress para aprovechar su motor de NLU (Natural Language Understanding), su capacidad de integración con APIs y su facilidad de despliegue.

---

## 3. Características Actuales

| Característica | Descripción |
| :--- | :--- |
| **🧠 Base de conocimiento integrada** | Responde preguntas sobre fechas, requisitos, exámenes, curso propedéutico, guías de estudio y contacto de la UNSIS. |
| **💬 Interfaz conversacional** | Mensajes con burbujas diferenciadas para usuario y bot, indicador de escritura y scroll automático. |
| **🌐 Esfera 3D interactiva** | Animación generada con Three.js que simula una red neuronal, con nodos y conexiones en movimiento, dando una sensación de "IA" avanzada. |
| **📱 Diseño responsivo** | Se adapta a diferentes tamaños de pantalla. |
| **📦 Código autónomo** | Todo en un solo archivo HTML, fácil de modificar y desplegar. |

---

## 4. Tecnologías y Herramientas Utilizadas

| Herramienta | Propósito |
| :--- | :--- |
| **HTML5** | Estructura de la página. |
| **CSS3** | Estilos y animaciones (variables CSS, Flexbox, Grid, keyframes). |
| **JavaScript (Vanilla)** | Lógica del chatbot, manejo del DOM, eventos. |
| **Three.js** | Renderizado de la esfera 3D (cargado desde CDN). |
| **Fuentes del sistema** | `Segoe UI`, `system-ui`, sans-serif. |

No se utilizan frameworks ni librerías adicionales.

---

## 5. Estructura del Proyecto

El proyecto es extremadamente simple y consta de un único archivo:
oraculo-chatbot/
└── jarvis-chatbot.html # Archivo principal que contiene HTML, CSS y JavaScript.


Dentro de este archivo, el código se organiza de la siguiente manera:

1. **CSS:** Estilos definidos en el bloque `<style>`.
2. **HTML:** Estructura de la interfaz (sidebar, área de chat, entrada de texto, contenedor 3D).
3. **JavaScript:**
   - **Base de conocimiento:** Un array de objetos con palabras clave y respuestas.
   - **Lógica de mensajes:** Funciones para enviar, mostrar mensajes y el indicador de escritura.
   - **Escena 3D:** Configuración de la escena de Three.js (esfera, nodos, conexiones, animación).

---

## 6. Guía de Instalación y Uso

### 6.1 Requisitos Previos

- Un navegador web moderno (Chrome, Firefox, Edge, Safari).
- Conexión a internet (para cargar Three.js desde el CDN la primera vez).

### 6.2 Pasos para Ejecutar

1. **Descarga el archivo** clonando este repositorio o descargando el archivo `jarvis-chatbot.html` directamente.

   ```bash
   git clone https://github.com/tu-usuario/oraculo-chatbot.git
   cd oraculo-chatbot
2. Abre el archivo en tu navegador: Haz doble clic en jarvis-chatbot.html o arrastra el archivo a una ventana del navegador.

3. Comienza a interactuar: Escribe tus preguntas en el campo de texto y presiona Enter o haz clic en el botón de enviar.

6.3 Ejecución local con servidor (opcional)

Si prefieres un entorno de desarrollo local con recarga automática, puedes usar cualquier servidor HTTP estático, por ejemplo:
# Con Python 3
python -m http.server 8000

# Con Node.js (http-server)
npx http-server

Luego abre http://localhost:8000 en tu navegador.

7. ¿Cómo Funciona? (Explicación Técnica)
7.1 Motor de Respuestas (Basado en Palabras Clave)

El chatbot utiliza un array de objetos donde cada uno define un conjunto de palabras clave y una respuesta asociada.
const knowledgeBase = [
  {
    keywords: ['fecha', 'fechas', 'cuando', 'cuándo'],
    answer: 'La entrega de fichas para el Curso Propedéutico Corto 2026 es del <b>13 de febrero al 26 de junio de 2026</b>.'
  },
  // ...
];

Cuando el usuario envía un mensaje, el texto se convierte a minúsculas y se busca si contiene alguna de las palabras clave. La primera coincidencia encontrada determina la respuesta. Si no hay coincidencia, se devuelve un mensaje genérico.
7.2 Interfaz de Usuario

    CSS: Usa variables para mantener una paleta de colores consistente y un diseño "oscuro" con acentos dorados.

    Eventos: El envío se activa con el botón o con la tecla Enter (sin Shift).

    Indicador de escritura: Muestra tres puntos animados mientras el bot "procesa" la respuesta.

    Scroll automático: El área de chat se desplaza hacia abajo con cada nuevo mensaje.

7.3 Esfera 3D (Three.js)

    Se crea una escena con una cámara en perspectiva.

    Se distribuyen 220 nodos en la superficie de una esfera usando el método de Fibonacci para una cobertura uniforme.

    Se dibujan conexiones entre nodos cercanos (distancia < 0.45) para simular una red neuronal.

    Se añade un núcleo interior con un efecto de pulsación.

    La escena rota continuamente y se renderiza en el canvas HTML.

8. ¿Por qué migrar a Botpress?

La versión actual, aunque útil como prueba de concepto, tiene limitaciones significativas que se solucionarán con la migración a Botpress.
| Característica | Prototipo (HTML) | Botpress (Futuro) |
| :--- | :--- | :--- |
| **Inteligencia** | Basada en palabras clave (estática). | **NLU** (Natural Language Understanding) para entender el contexto y la intención del usuario. |
| **Mantenimiento** | El código y la base de conocimiento están en un solo archivo. | **Interfaz visual** (Botpress Studio) para diseñar flujos conversacionales sin necesidad de programar. |
| **Escalabilidad** | Limitada a preguntas predefinidas. | Puede integrarse con **APIs externas**, **bases de datos** y **múltiples canales** (web, WhatsApp, Messenger, etc.). |
| **Mejora Continua** | Requiere editar el código HTML. | Permite **entrenar el modelo de NLU** y mejorar el bot basándose en interacciones reales. |

En resumen, Botpress nos permitirá construir un asistente realmente inteligente, fácil de mantener y preparado para el futuro.
