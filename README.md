# Contadores en PLC – CTU, CTD y CTUD en LAD

Este proyecto muestra el funcionamiento de los tres tipos de contadores disponibles en programación Ladder: **CTU (Count Up), CTD (Count Down) y CTUD (Count Up/Down)**. A través de simulaciones prácticas, se exploran sus diferencias, aplicaciones típicas y cómo se comportan en un entorno de automatización.

---

## Contexto

Los contadores permiten registrar eventos como:

- Cantidad de ciclos completados
- Producción de botellas o cajas
- Fallas ocurridas en un turno

Variables clave:

- **PV (Preset Value)**: límite del contador
- **CV (Current Value)**: valor actual del conteo
- **R (Reset)**: reinicia el conteo actual
- **LD (Load)**: carga el valor inicial en contadores descendentes

A diferencia de los temporizadores, los contadores requieren pulsos de activación (presionar y soltar) para modificar su estado. Esto permite un control más granular sobre eventos discretos.

---

## Capturas

- **CTU – Contador ascendente**
  - Se activa con el botón de inicio (%M0.0) y se resetea con %M0.3.
  - El motor 8 (%M1.7) se enciende al alcanzar el límite de PV = 5.
  - ![CTU](https://github.com/SantiagoBaeza/Uso-de-contadores-en-PLC/blob/main/00%20captura%20CTU.jpg)

- **CTD – Contador descendente**
  - Comienza desde PV = 7 y decrementa con cada pulso.
  - LD (%M0.3) actúa como reset, y el motor 9 (%M2.0) se activa al llegar a cero.
  - ![CTD](https://github.com/SantiagoBaeza/Uso-de-contadores-en-PLC/blob/main/01%20captura%20CTD.jpg)

- **CTUD – Contador bidireccional**
  - CU (%M0.0) incrementa, CD (%M0.4) decrementa.
  - R (%M0.3) y LD (%M0.5) permiten reinicio y carga.
  - QU activa el motor 10 (%M2.1), QD activa el motor 11 (%M2.2).
  - contador en funcionamiento desde el simulador [aca](https://github.com/SantiagoBaeza/Uso-de-contadores-en-PLC/blob/main/03%20funcionamiento%20de%20CTUD%20.gif)
  - ![CTUD](https://github.com/SantiagoBaeza/Uso-de-contadores-en-PLC/blob/main/02%20captura%20CTUD.jpg)

---

## Lección importante

> Los contadores son esenciales para controlar procesos cíclicos y registrar eventos en tiempo real.  
> El uso correcto de PV, CV, R y LD permite diseñar lógica confiable y flexible.  
> El CTUD ofrece control total al permitir conteo ascendente y descendente con salidas independientes.  
> Usar accesos rápidos como Ctrl+F2/F3 para forzar entradas agiliza la simulación y mejora la comprensión del comportamiento lógico.

---

## Simulación realizada en

- Siemens S7-1200 (TIA Portal)
- Lógica en escalera (LAD)

---

## Comentarios finales

El archivo del proyecto se incluye para que cualquier persona con acceso a TIA Portal V16 pueda abrirlo y realizar la simulación. En mi caso, el software fue proporcionado como parte del curso de Udemy. Este ejercicio me permitió comprender mejor la diferencia entre los tipos de contadores y cómo aplicarlos en situaciones reales de automatización.

> 🧩 Este repositorio forma parte de una serie de prácticas que documentan mi avance en programación de PLC.

---
