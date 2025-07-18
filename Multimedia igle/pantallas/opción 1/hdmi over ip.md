# Opción 1 - Distribución por HDMI Over IP

## 🧩 Concepto

HDMI over IP permite enviar señales de video HDMI a través de una red local usando transmisores y receptores dedicados. Es útil para transmitir contenido sincronizado a múltiples TVs o proyectores sin usar PC intermedias.

---

### 🛠 Requisitos

- PC con **múltiples salidas HDMI** (dedicadas por contenido a transmitir).
- 1x **TX HDMI over IP** por cada salida HDMI. 
- 1x **RX HDMI over IP** por cada pantalla receptora.
- 1x **Switch Ethernet Gigabit** (con VLAN o IGMP Snooping si hay muchos dispositivos).
- Cable de red **Cat6 o superior** armado con estándar **TIA/EIA 568B**.
- Software en PC (OBS, Holyrics, etc.) que maneje múltiples monitores extendidos.

---

## 🖥️ Estructura

[[Pantallas 1.canvas|Pantallas 1]]
    PC -->|HDMI| TX1[TX HDMI #1]
    PC -->|HDMI| TX2[TX HDMI #2]
    PC -->|HDMI| TX3[TX HDMI #3]
    
    TX1 -->|CAT6| SW[Switch Gigabit]
    TX2 -->|CAT6| SW
    TX3 -->|CAT6| SW

    SW -->|CAT6| RX1[RX HDMI #1 - TV1]
    SW -->|CAT6| RX2[RX HDMI #2 - TV2]
    SW -->|CAT6| RX3[RX HDMI #3 - TV3]
    SW -->|CAT6| RX4[RX HDMI #4 - TV4]
    SW -->|CAT6| RX5[RX HDMI #5 - Conferencistas]
    SW -->|CAT6| RX6[RX HDMI #6 - Proyector]

## ✅ Ventajas

- Muy estable.
- Sin latencia visible.
- No requiere software en TVs.

## ❌ Desventajas

- Requiere hardware físico específico.
- No permite personalización por pantalla.
- Más costoso si hay muchas pantallas.


## ⚙️ Equipamiento esencial

#### 1. Transmisor HDMI over IP (TX)

[SIIG CE‑H25D11‑S2 HDMI over IP Transmitter]()

Convierte una señal HDMI de tu PC (OBS/letras, countdown, proyector) en IP.

Extiende hasta 120 m por CAT6 de manera confiable.

Necesitarás 3 unidades (una por cada señal diferente).



---

#### 2. Receptor HDMI over IP (RX)

[Lornceng HDMI over IP Receiver]()

Recibe la señal IP y la convierte de nuevo a HDMI para cada pantalla.

Ideal para tus 4 TVs del auditorio, 2 de plataforma y el proyector → 7 unidades.



---

#### 3. Switch Gigabit administrable

Basado en opciones disponibles:

**TP‑Link TL‑SG3210 (8 puertos Gigabit administrable)**  

Perfecto para instalar en cabina: 3 TX + 7 RX = 10 dispositivos (8 puertos + 2 uplinks, o usás uno adicional de 16 puertos bajo presupuesto).

Permite gestión de tráfico IGMP Multicast, ideal para HDMI over IP.



Recomendado: versión de 16 puertos si agregás equipos o PoE en el futuro.


---

### 📑 Resumen del sistema

Componente	Cantidad	Función principal

SIIG CE‑H25D11‑S2 TX	3	Envía señales de tu PC (OBS, countdown, letras) a red IP
Lornceng RX	7	Recibe y convierte la señal IP en HDMI para cada pantalla/proyector
TP‑Link TL‑SG3210 Switch	1	Conecta todos los TX y RX en red local. Permite gestión Multicast
Cable CAT6 (armado)	++	Conecta todos TX/RX al switch (tienes el cable, te explico abajo)
Fichas RJ45 en estándar T–568B	--	Para crimpado correcto según norma —Pon cada par en el orden B estándar.