# fotómetro-portátil-icbm
Proyecto de electrónica biomédica: fotómetro portátil para análisis de muestras. Grupo 8

Equipo: Ivette Avila, Isidora Hernández y Jacinta Vallejos.

Prototipo educativo de bajo costo que ilumina una muestra líquida con un LED, mide la luz que la atraviesa con un sensor TEMT6000 y calcula la transmitancia relativa usando una medición previa de blanco. El resultado se muestra por comunicación serial en el computador. El firmware avisa si el sensor se satura o no detecta señal. Es solo para uso formativo, no para análisis clínico.

## Componentes principales
- ESP32 DevKit (adquisición, cálculo y comunicación serial)
- LED verde 5 mm con resistencia limitadora
- Módulo sensor de luz TEMT6000
- PCB diseñada en KiCad
- Soporte y cámara oscura impresos en 3D
- Alimentación por USB (5 V)

## Contenido del repositorio
- `electronica/kicad/`: proyecto KiCad (esquemático y PCB)
- `electronica/libraries/`: símbolos, footprints y modelos 3D propios
- `firmware/`: código del ESP32
- `mecanica/`: modelos 3D de la cámara oscura

