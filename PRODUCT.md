# Product

<!-- impeccable:product-schema 1 -->

## Platform

web

## Users

Jugador de BDO, México, panel personal.

## Product Purpose

Un panel personal de Black Desert que reúne en una sola vista todo lo que el jugador necesita vigilar durante su sesión: el próximo jefe mundial (con cuenta regresiva), los horarios de jefes de su región, el contador semanal de jefes, la cuenta regresiva al reset semanal, su checklist semanal y sus notas rápidas. Éxito = abrir el panel y obtener toda esa información sin navegar entre secciones ni depender de trackers externos.

## Positioning

"Todo lo mío en una sola vista." Los trackers grandes (bdolytics, garmoth.com y similares) cargan más y separan la información; este panel consolida timers, checklist y notas propias en una superficie rápida y minimalista. La información persistente (checklist, notas, contadores) vive en el navegador del jugador (localStorage), no en un backend.

## Operating Context

- Juego: Black Desert Online.
- Rituales de uso: el jugador revisa el panel durante la sesión para saber qué jefe viene, cuánto falta para el reset, qué tareas semanales tiene pendientes y recordatorios.
- Resets del juego: reset diario a las 6:00 PM; reset semanal los miércoles a las 6:00 PM.
- Jefes mundiales activos en el panel: Garmoth, Laulau, Vell.
- Jefes pendientes (imágenes en `public/assets/` sin horario aún): Karanda, Quint.

## Capabilities and Constraints

- Horario de jefes editable en código (`SCHEDULE`, hora local), con días de la semana por jefe.
- Cuenta regresiva "Next Boss" + "Followed By" agrupando jefes que salen a la misma hora.
- Tabla de horarios con resaltado de la próxima ocurrencia.
- Contadores semanales por jefe (tocar para incrementar, con máximo por jefe y recompensa asociada). Reinicio manual vía botón "Reiniciar semana".
- Cuenta regresiva al reset semanal: formato `XD Xhrs`, y `[HOY] Xhrs` cuando es miércoles.
- Checklist semanal: tareas con título y descripción; persisten entre sesiones; al resetear la semana solo se desmarcan los checks (las tareas se conservan).
- Notas ("Pendientes"): lista libre que persiste y nunca se resetea.
- Persistencia: localStorage (claves `bdo_cnt`, `bdo_weekly`, `bdo_todos`).
- Stack: Astro 7 (sitio estático), pnpm, Node 24. Contenido y copia en español de México.
- Despliegue objetivo: hosteado en internet (sitio estático).

## Brand Commitments

- Nombre del juego y del panel: "Black Desert · Panel personal".
- Retratos de jefes como identidad visual: imágenes `.webp` en `public/assets/` (garmoth, laulau, vell, karanda, quint). El panel ya usa estos retratos en lugar de emojis para los jefes.
- Tono: personal y directo, en español de México.

## Evidence on Hand

- Retratos de jefes: `public/assets/{garmoth,laulau,vell,karanda,quint}.webp`.
- Datos de horario y recompensas actuales en `src/pages/index.astro` (constantes `SCHEDULE` y `BOSSES`).

## Product Principles

1. Una sola vista lo resuelve todo: la información debe estar junta y escaneable, no dispersa.
2. Rápido y ligero por encima de todo: se abre, se ve, se cierra.
3. Lo personal persiste; lo semanal se renueva solo.
4. La información de BDO es la fuente de verdad; el panel no inventa horarios ni recompensas.
