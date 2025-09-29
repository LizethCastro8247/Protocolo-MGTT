# Resumen de *MQTT & MQTT 5 Essentials (HiveMQ)*
**Nombre:** Lizeth Roxana Castro Reyes - 22211535  
**Materia:** Sistemas Programables  
---

## Parte I: MQTT Essentials (bases del protocolo)

### Qué es MQTT
- Protocolo de mensajería **ligero y eficiente**.
- Diseñado para **IoT y redes poco confiables**.
- Inventado en 1999 para monitoreo de oleoductos vía satélite.

### Modelo Publish/Subscribe (Pub/Sub)
- **Publisher**: envía mensajes.  
- **Subscriber**: recibe mensajes.  
- **Broker**: intermediario que filtra y distribuye mensajes.  

**Ventajas**:
- **Espacio**: no necesitan conocerse entre sí.  
- **Tiempo**: pueden estar activos en momentos distintos.  
- **Sincronización**: no bloquean procesos entre sí.  

### Cliente y Broker
- Un cliente puede publicar, suscribirse o ambas cosas.
- El **broker** administra:
  - conexiones,
  - autenticación,
  - distribución de mensajes.

### Mensajes MQTT
- **Topic**: cadena jerárquica (ej. `casa/sala/temperatura`).  
- **Payload**: contenido (texto, binario, JSON, etc.).  
- **QoS**: nivel de entrega.  
- **Flags**: Retain (guardar último mensaje), DUP (duplicado).

### Topics y mejores prácticas
- Jerárquicos con `/`.  
- **Comodines**:  
  - `+` (un nivel),  
  - `#` (múltiples niveles).  
- Evitar:
  - espacios,
  - barra inicial (`/`),
  - nombres largos.  

### Quality of Service (QoS)
- **QoS 0** → *At most once* (fire and forget).  
- **QoS 1** → *At least once* (puede duplicarse).  
- **QoS 2** → *Exactly once* (más seguro, pero más lento).

### Sesiones persistentes y colas
- El broker guarda suscripciones y mensajes mientras el cliente está desconectado.
- Controlado por la bandera **Clean Session**.

### Retained Messages
- El broker guarda **el último mensaje de un topic**.
- Los nuevos suscriptores lo reciben inmediatamente.

### Last Will & Testament (LWT)
- Notifica desconexiones inesperadas de un cliente.
- Útil para mostrar estados *online/offline*.

### Keep Alive y Client Takeover
- **Keep Alive**: detección de conexiones interrumpidas con PINGREQ/PINGRESP.  
- **Client Takeover**: un cliente nuevo reemplaza al “fantasma” desconectado.

### MQTT sobre WebSockets
- Permite usar MQTT en navegadores web.
- Casos: dashboards en vivo, notificaciones, apps móviles.

---

## Parte II: MQTT 5 Essentials (novedades)

### Motivación
- Publicado en **2019** como estándar OASIS/ISO.  
- Pensado para **cloud, aplicaciones críticas y gran escala**.

### Cambios principales
- **Clean Start & Session Expiry** → más control que Clean Session.  
- **Reason Codes** → mejores códigos de error y retroalimentación.  
- **User Properties** → metadatos personalizados en mensajes.  
- **Shared Subscriptions** → balanceo de carga entre suscriptores.  
- **Request/Response Pattern** → facilita comunicación tipo petición-respuesta.  
- **Topic Aliases** → reduce tamaño de mensajes al reutilizar nombres de temas.  
- **Enhanced Authentication (AUTH)** → métodos modernos como OAuth.  
- **Flow Control y límites configurables** → control de tamaño de mensajes, número de subscripciones, etc.

---

## Conclusión
- **MQTT 3.1.1** → simplicidad y confiabilidad para IoT básico.  
- **MQTT 5** → evolución con más flexibilidad, escalabilidad y control.  

