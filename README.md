# Fotómetro portátil (ICBM)

Proyecto de integración de Electrónica Biomédica, Universidad del Desarrollo. Grupo 8.

**Equipo:** Ivette Avila, Isidora Hernández y Jacinta Vallejos.

## Descripción

Prototipo educativo de bajo costo que mide la **transmitancia relativa** de una muestra líquida. Un LED verde ilumina la muestra y un módulo sensor de luz TEMT6000 mide la luz que la atraviesa. El ESP32-C3 calcula la transmitancia como T = I / I₀, donde I₀ es la intensidad medida con el blanco.

El equipo se opera de forma autónoma:
- **SW1 (MEDIR):** inicia la medición de la muestra.
- **SW2 (CALIBRAR):** ejecuta la calibración de blanco.
- **Pantalla OLED 0.96" (I2C):** muestra los resultados y los mensajes de calibración y de error.

Se alimenta por USB-C (5 V). El regulador del módulo ESP32-C3 entrega 3,3 V al sensor y a la pantalla.

> Uso exclusivamente formativo; no es un instrumento para análisis clínico.

## Componentes principales

| Ref. | Componente | Conexión |
|---|---|---|
| J1, J2 | ESP32-C3 SuperMini (montado en zócalos hembra de 9 pines) | — |
| D1 + R1 | LED verde 5 mm + resistencia de 68 Ω | GPIO4 |
| J3 | Módulo sensor de luz TEMT6000 | SIG → GPIO2 (ADC1) |
| J4 | Pantalla OLED 128×64 0.96" (GND, VCC, SCL, SDA) | SDA → GPIO8, SCL → GPIO9 |
| R2, R3 | Pull-up I2C de 4,7 kΩ | SDA, SCL |
| SW1, SW2 | Pulsadores 6×6 mm THT (activos en BAJO) | GPIO5, GPIO6 |
| R4, R5 | Pull-up de los pulsadores de 10 kΩ | GPIO5, GPIO6 |
| C1 | Condensador cerámico de 100 nF (desacoplo de 3,3 V) | 3V3 – GND |

## PCB

- Placa de 70 × 55 mm con 4 agujeros de montaje M3 (3,2 mm).
- Componentes THT; las pistas van en una sola capa (B.Cu) para fabricarla en la ruteadora CNC.
- Plano de tierra en la cara inferior.
- El DRC de KiCad no arroja errores ni conexiones pendientes.

## Estructura del repositorio

```
├── README.md
├── LICENSE
├── docs/
│   ├── datasheets/      Hojas de datos de la OLED y del TEMT6000
│   ├── bitacora.md      Registro de avances del proyecto
│   └── informes/        Informes de la parte I y la parte II
├── electronica/
│   ├── kicad/           Proyecto KiCad (.kicad_pro, .kicad_sch, .kicad_pcb)
│   ├── libraries/       Bibliotecas propias (no se usaron; solo bibliotecas oficiales de KiCad)
│   └── outputs/         PDF del esquemático, Gerber, taladrado, BOM, STEP e imágenes
├── firmware/            Código del ESP32-C3 (en desarrollo)
└── software/            Herramientas complementarias (sin uso por ahora)
```

## Cómo abrir el diseño

1. Instalar [KiCad](https://www.kicad.org/) (versión 9 o superior).
2. Abrir `electronica/kicad/fotometro_portatil_pcb.kicad_pro`.
3. Desde el gestor de proyecto se puede abrir el esquemático y el editor de PCB. Todos los símbolos y footprints son de las bibliotecas oficiales de KiCad, así que no se necesita instalar bibliotecas adicionales.

## Estado del proyecto

- [x] Esquemático
- [x] Layout de PCB y archivos de fabricación
- [ ] Fabricación de la placa
- [ ] Firmware
- [ ] Armado, caja impresa en 3D y validación funcional

## Licencia

Distribuido bajo la licencia MIT. Ver `LICENSE`.
