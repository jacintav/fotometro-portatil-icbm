# Bitácora del proyecto

## Parte I
- Definición de la idea: fotómetro portátil con ESP32 que mide la transmitancia relativa de una muestra líquida.
- Primera propuesta con fotodiodo y etapa de amplificación, e interacción por monitor serial.
- Entrega del informe de la parte I (docs/informes).

## Parte II
- 30/10/2026: creación del repositorio, licencia MIT, README y hojas de datos de los componentes.
- Rediseño según la retroalimentación de los profesores: se agregan la pantalla OLED y dos pulsadores (SW1 medir, SW2 calibrar blanco), y se reemplaza el fotodiodo por el módulo TEMT6000.
- Diseño del esquemático en KiCad.
- 01/11/2026: corrección de footprints y conexiones (LED al GPIO4, orden de pines de la OLED), etiquetas de señales y pines no conectados.
- 02/11/2026: diseño de la PCB (70 x 55 mm, una capa) y exportación de Gerber, perforaciones, BOM e imágenes.
- 03/11/2026: exportación del modelo 3D (STEP).
- 04/11/2026: actualización de los archivos finales del esquemático y la PCB.

## Pendiente
- Fabricación de la placa en la universidad.
- Desarrollo del firmware.
- Armado, caja impresa en 3D y validación funcional.
