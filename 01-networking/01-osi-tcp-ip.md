# Modelo OSI y TCP/IP

## 1. Objetivo

Comprender cómo se organiza la comunicación entre dispositivos mediante los modelos OSI y TCP/IP, e identificar las funciones de las principales capas y protocolos de red.

## 2. Modelo OSI

El modelo OSI es un modelo de referencia que divide la comunicación de red en siete capas.

| Capa | Nombre | Función principal | Ejemplos |
|---|---|---|---|
| 7 | Aplicación | Proporciona protocolos de comunicación utilizados por las aplicaciones | HTTP, DNS, SSH |
| 6 | Presentación | Representación, codificación y transformación de datos | Formatos y codificaciones |
| 5 | Sesión | Gestión conceptual de sesiones de comunicación | Control de sesiones |
| 4 | Transporte | Comunicación extremo a extremo y transporte de datos | TCP, UDP |
| 3 | Red | Direccionamiento lógico y enrutamiento | IPv4, IPv6 |
| 2 | Enlace de datos | Comunicación dentro de un enlace de red | Ethernet, MAC |
| 1 | Física | Transmisión de bits mediante señales | Cable, fibra, radio |

## 3. Modelo TCP/IP

TCP/IP es el conjunto de protocolos y el modelo práctico que sustenta la comunicación en Internet.

Una representación simplificada contiene cuatro capas:

1. Aplicación.
2. Transporte.
3. Internet.
4. Acceso a la red.

El modelo TCP/IP agrupa algunas funciones que el modelo OSI representa en capas separadas.

## 4. Direcciones IP y MAC

### Dirección IP

Es una dirección lógica utilizada para identificar interfaces y permitir el encaminamiento del tráfico entre redes.

Ejemplo de IPv4: `192.168.1.20`.

### Dirección MAC

Es una dirección utilizada en la comunicación de enlace local. Habitualmente está asociada a una interfaz de red, aunque puede modificarse o falsificarse en determinadas circunstancias.

### Diferencia principal

La IP permite el direccionamiento entre redes; la MAC se utiliza para entregar tramas en un enlace local.

## 5. Transporte y puertos

TCP ofrece mecanismos de comunicación confiable y ordenada. UDP tiene menos mecanismos de control y no establece una conexión TCP.

Un puerto identifica un punto de comunicación asociado a un servicio o aplicación.

Ejemplos:

- TCP 443: puerto habitual de HTTPS.
- TCP 22: puerto habitual de SSH.
- UDP/TCP 53: puertos utilizados habitualmente por DNS.

TCP no proporciona por sí solo cifrado. HTTPS utiliza TLS para proteger la comunicación HTTP.

## 6. Encapsulación

La encapsulación consiste en añadir información de control al transportar datos a través de las capas de red.

Representación simplificada:

```text
Datos de aplicación
        ↓
Segmento TCP o datagrama UDP
        ↓
Paquete IP
        ↓
Trama Ethernet
        ↓
Bits transmitidos
```

Cada capa añade información necesaria para sus funciones.

## 7. Comunicación con un servidor remoto

Cuando una computadora envía tráfico a un servidor que está en otra red:

1. La aplicación prepara los datos.
2. El transporte utiliza TCP o UDP según el protocolo y la aplicación.
3. IP identifica los extremos del recorrido lógico.
4. La computadora prepara una trama para el siguiente salto, normalmente el router local.
5. Los routers reenvían los paquetes hacia su destino.

Las direcciones IP normalmente se mantienen durante el recorrido, salvo transformaciones como NAT. Las direcciones MAC de las tramas cambian en cada enlace enrutado.

## 8. Conclusiones

El modelo OSI permite comprender y diagnosticar las comunicaciones por capas. TCP/IP describe el conjunto de protocolos utilizado en Internet.

Comprender IP, MAC, puertos y encapsulación proporciona una base para estudiar análisis de tráfico con Wireshark, reconocimiento de servicios con Nmap y detección de eventos de red en un entorno SOC.

## 9. Estado de la actividad

- Tipo: documentación de aprendizaje.
- Tema: fundamentos de redes.
- Estado: módulo teórico completado; pendiente ampliar con ejercicios prácticos.
- Próximo tema: TCP y UDP, puertos y establecimiento de conexiones.
