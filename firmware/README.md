# Firmware

Código del ESP32-C3 SuperMini (en desarrollo).

Funciones previstas:
- Calibración de blanco al presionar SW2 (GPIO6).
- Medición de la muestra al presionar SW1 (GPIO5).
- Lectura del sensor TEMT6000 por ADC (GPIO2) y control del LED (GPIO4).
- Cálculo de la transmitancia relativa (T = I / I0) y despliegue en la pantalla OLED por I2C (SDA GPIO8, SCL GPIO9).
