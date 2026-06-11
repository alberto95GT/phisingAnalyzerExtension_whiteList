# Phishing AI Analyzer - Official Whitelist

Bienvenido al repositorio oficial de la lista blanca de dominios de confianza para la extensión **Phishing AI Analyzer**.

## 📖 Sobre este repositorio

Este es un repositorio de datos de solo lectura que aloja el archivo `whitelist.json`. 

**Phishing AI Analyzer** es una extensión de navegador privada impulsada por Inteligencia Artificial (Gemini) diseñada para detectar y bloquear intentos de suplantación de identidad (Phishing) y exfiltración de credenciales en tiempo real a través del análisis estructural del DOM.

Para optimizar el rendimiento, reducir la latencia de navegación del usuario y minimizar el consumo de tokens de la API, la extensión consulta periódicamente este repositorio público.

## ⚙️ ¿Cómo funciona?

El archivo principal de este repositorio (`whitelist.json`) contiene un array de dominios oficiales e históricamente seguros (bancos, instituciones, grandes plataformas tecnológicas).

1. **Sincronización:** La extensión descarga de forma asíncrona este archivo (utilizando la URL `raw` de GitHub) cada 24 horas y lo almacena de forma segura en la memoria caché del navegador (`chrome.storage.local`).
2. **Evaluación de Cortocircuito (Short-Circuit):** Cuando el usuario navega por internet, la extensión intercepta el dominio de destino. Si el dominio se encuentra en esta lista blanca, el sistema de vigilancia lo clasifica automáticamente como "Entorno Seguro".
3. **Ahorro de Recursos:** Al identificar un dominio de la lista blanca, la extensión detiene el análisis heurístico del DOM y evita enviar peticiones innecesarias a la IA, garantizando una navegación fluida (0ms de impacto en el rendimiento).

## 📄 Estructura del JSON

El archivo mantiene una estructura JSON estricta y minimalista:

```json
{
  "dominios_seguros": [
    "bancosantander.es",
    "github.com",
    "google.com"
  ]
}
