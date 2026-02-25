# 🤖 AI Agent: Consultas Conversacionales para Estación Meteorológica IoT

![GitHub stars](https://img.shields.io/github/stars/TU_USUARIO/ai-agent-influxdb-weather?style=social)
![n8n](https://img.shields.io/badge/Orquestador-n8n-FF6D5B?logo=n8n)
![Gemini](https://img.shields.io/badge/LLM-Google%20Gemini-4285F4?logo=google-gemini)

Este proyecto nace como un reto práctico dentro del **Máster en Inteligencia Artificial en Founderz**. El objetivo es democratizar el acceso a los datos técnicos, permitiendo que cualquier usuario pueda "chatear" con una base de datos **InfluxDB** mediante lenguaje natural en lugar de escribir consultas complejas en código.

---

## 🚀 El Reto
¿Y si pudieras preguntarle a tu casa: *"¿Cuál ha sido la temperatura media de esta tarde?"* y recibir una respuesta precisa en segundos? 

Este agente actúa como puente inteligente entre el usuario y los datos recolectados por una estación meteorológica IoT propia, transformando métricas técnicas en información comprensible.

## 🛠️ Tech Stack
- **Cerebro (LLM):** Google Gemini.
- **Orquestación (Workflow):** n8n (Low-Code/Agentic).
- **Base de Datos:** InfluxDB (Series Temporales).
- **Infraestructura de Datos (IoT):** ESP32 + Sensor DHT22 + MicroK8s.

## ⚙️ Arquitectura y Funcionamiento

## 🛠️ Configuración Necesaria para el Despliegue
Para que este flujo funcione, se deben realizar los siguientes ajustes en el archivo JSON tras importarlo a n8n:

1. **Credenciales de IA:** Configurar una API Key válida de **Google Gemini** en el nodo de Chat Model.
2. **Conexión InfluxDB:** En el nodo "HTTP Request", sustituir los placeholders por tus datos reales:
   - `TU_DOMINIO_O_IP`: La dirección de tu servidor.
   - `TU_ORGANIZACION`: El nombre de tu organización en InfluxDB.
   - `TU_BUCKET_NAME`: El nombre del bucket donde se almacenan las métricas del ESP32.
3. **Autenticación:** Configurar un Token de InfluxDB con permisos de lectura en las credenciales del nodo de Header Auth.

1. **Recolección:** Un dispositivo **ESP32** envía datos de temperatura y humedad en tiempo real a una base de datos **InfluxDB** alojada en un cluster local de **MicroK8s**.
2. **Interfaz de Chat:** El usuario interactúa mediante una interfaz de chat.
3. **Procesamiento (n8n + Gemini):** - El agente recibe la consulta en lenguaje natural.
   - Traduce la intención del usuario en una consulta válida para la base de datos.
   - Recupera la información de InfluxDB.
   - Gemini procesa los datos y genera una respuesta conversacional precisa.

## 📊 Visualización en Tiempo Real
Puedes consultar el dashboard de Grafana que alimenta este agente en el siguiente enlace:
🔗 [Dashboard Público - Estación Meteorológica](http://rubius.ddns.net/public-dashboards/304227f5af52407482bd83fd15766d8f?orgId=1&refresh=10s)

---

## 📂 Estructura del Repositorio
- `/workflows`: Archivos JSON del flujo de trabajo en n8n.
- `/iot-firmware`: Código fuente para el ESP32 (C++/Arduino).
- `/k8s-manifests`: Archivos de despliegue para el entorno MicroK8s.

## 🙏 Agradecimientos
Proyecto desarrollado como parte del aprendizaje práctico en **Founderz**. Gracias por el impulso para construir soluciones reales que fusionan el mundo de los Sistemas, IoT e IA.

---
👤 **Marcelo Carlos Hernandez Wrona** 📧 [marcelo_hernandez_12@hotmail.com](mailto:marcelo_hernandez_12@hotmail.com)  
📍 Toledo, España
