### Conexion actual de cables
- 1: Proyector
- 2: Monitor plataforma lado audio izquierdo
- 3: Tv Auditorio lado izquierdo
- 4: Monitor plataforma lado derecho
- 5: Tv auditorio lado derecho
- 6: Tv hall Oficina
- NADA: Tv Hall de frente

# 📡 Distribución de Contenidos para Evento

Esta documentación detalla dos arquitecturas para distribuir contenido desde OBS (y otras fuentes) a múltiples pantallas en un evento o auditorio.

## 🖥️ Distribución de contenido

| Pantalla                      | Fuente     | Contenido            |
| ----------------------------- | ---------- | -------------------- |
| TVs (x4)                      | PC 1 (OBS) | Transmisión o letras |
| Pantallas para conferencistas | PC 2       | Countdown            |
| Proyector Principal           | PC 2       | Letras de Holyrics   |

---

## Opciones

1. [HDMI over IP](hdmi%20over%20ip.md)
2. [Transmisión por red local con OBS (NDI, RTMP, etc)](Transmisión%20red%20obs%20ndi.md)



### prompt

necesito organizar los conceptos en un flujo abstracto ya que si no, no comprendo tenemos 

3 partes

### 1 - Transmitir señal
necesito transmitir la señal, el tema es que tengo distintas señales, tengo que pasar letras de holyrics, videos y tambien enviar la señal de lo que se esta transmitiendo en vivo antes de ser procesado (previsualizacion de obs) cual es la mejor opcion teniendo en cuenta mi contexto, y cual es la opcion profesional que se utiliza en estos casos?

### 2- Conexion de pantallas a la red lo ideal
entiendo que es un switcher con igmp snooping para gestionar entradas y salidas (grupos de puertos verdad?) por el momento no tengo un switcher, lo que si tengo son muchos modems de internet que a medida que fui comprando para instalar modems en mi casa me fueron sobrando. puedo conectar los modems entre si para llegar a cubrir la cantidad de puertos que necesito? los modems tienen 3/4 puertos cada uno, y tengo wifi en el auditorio, entonces mi idea es, conectar en cada modem otro modem, y en cada uno conectar todas las pantallas, y la pc que transmite conectarla al wifi para no ocupar otro puerto, esto es viable?

### 3-transmision de las pantallas
en cuanto a las pantallas, tengo 1 proyector (donde se pasa letra), y 6 tvs (son todas smart tv) de las cuales 2 pasan countdown, y letras, 2 del auditorio pasan letras y la previsualizacion de obs, y las 2 del hall pasan anuncios, publicidad, videos, y tambien la previsualizacion del obs el proyector no se es tipo smart, que puedo conectarme a internet, pero las otras 6tvs son todas smart, por lo que entiendo que podria con un browser en cada smart entrar a una url. podria entonces directamente acceder a una url que la pc envie la senal que cada tv necesita? cual es la opcion profesional ?

en base a todo esto comentado, hazme una documentacion con graficos y tablas para comprender en su totalidad el objetivo la dfistribucion de contenidos y la configuracion necesaria. ademas, hazme tambien un prompt para dar el mayor contexto a una IA y no comenzar la conversacion de 0