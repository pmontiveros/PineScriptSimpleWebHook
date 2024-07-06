# PineScriptSimpleWebHook
# SimpleClient y Servidor Webhook,

## Descripción del Proyecto

Este proyecto consiste en un sistema simple de cliente y servidor para recibir y mostrar novedades en tiempo real desde un servidor webhook. El cliente muestra las novedades recibidas de manera visualmente atractiva en una interfaz web, y también monitorea el estado del servidor webhook.

## Servidor Webhook

El servidor webhook está diseñado para recibir alertas de TradingView y transmitirlas al cliente SimpleClient. Utiliza Flask como framework web y puede manejar peticiones POST con datos en formato JSON.

### Funcionalidades del Servidor Webhook:

- **Endpoint `/webhook`:** Recibe datos de alertas de TradingView en formato JSON.
- **Almacenamiento de Novedades:** Guarda las novedades recibidas en memoria para que el cliente las consulte.
- **Endpoint `/health`:** Permite verificar el estado del servidor webhook.

## Cliente Simple (SimpleClient)

El cliente SimpleClient es una interfaz web que muestra las últimas novedades recibidas del servidor webhook. Además, muestra un dashboard con el número total de novedades recibidas y el estado del servidor webhook (vivo o caído).

### Funcionalidades del Cliente Simple:

- **Interfaz de Usuario:** Muestra las últimas novedades en globos de mensajería, similar a aplicaciones de mensajería.
- **Dashboard:** Muestra el número total de novedades recibidas y el estado actual del servidor webhook mediante un semáforo.
- **Actualización Automática:** Permite configurar intervalos de actualización automática (1 segundo, 5 segundos, 30 segundos o 120 segundos).

## Instalación

### Requerimientos Previos

- Python 3.6 o superior
- Flask (`pip install flask`)

### Configuración en TradingView.com

Para configurar el envío de alertas desde TradingView al servidor webhook:

1. **Crear una Alerta en TradingView:**
   - Ve a TradingView y crea una alerta de precio o cualquier otro tipo de alerta que desees enviar al servidor webhook.

2. **Configurar la URL del Webhook:**
   - En la configuración de la alerta en TradingView, configura la URL del webhook para que apunte al endpoint `/webhook` de tu servidor SimpleClient. Asegúrate de configurar el método HTTP como POST y el tipo de contenido como JSON.

## Ejecución

1. **Ejecutar el Servidor Webhook:**
   ```bash
   python servidor_webhook.py
