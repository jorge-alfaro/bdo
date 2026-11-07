---
version: 1
slug: "src-pages-index-astro"
primary_target: "src/pages/index.astro"
related_targets: []
---

# Surface brief — Panel de Black Desert (index)

## Scope and visitor mode

Operate. Una única página estática (Astro) que reúne el estado personal del jugador de Black Desert: próximo jefe con cuenta regresiva, horarios de jefes, contadores semanales, cuenta regresiva al reset, checklist semanal y notas. El usuario llega a consultar y marcar, no a explorar.

## Audience, job, action, proof

- Audience: el propio jugador, uso personal, en sesiones cortas durante el juego, escritorio y móvil.
- Job: saber qué jefe viene, cuánto falta para el reset, qué tareas semanales quedan, y registrar progreso (marcar jefes, checks, notas).
- Proof: la información debe estar junta y escaneable en una sola vista; nada de navegar entre secciones.

## Chosen direction

Carta náutica / bitácora de barco (dirección asignada por la semilla). Paleta de azul marino profundo con tinta de bitácora y acentos de latón; la semana como un derrotero de navegación. El estado se marca en tinta (validado/anulado), no solo con color. El momento memorable es el timer del "Next Boss" como aguja de brújula que gira hacia el próximo jefe.

## Constraints

- Controles estándar de la web (botones, inputs, tabla). El mundo presta solo type, paleta, densidad y un movimiento firma; nunca sustituye el layout ni los controles por una réplica de carta náutica.
- Persistencia en localStorage (claves `bdo_cnt`, `bdo_weekly`, `bdo_todos`). Comportamiento actual intacto.
- Español de México. Retratos de jefes en `public/assets/`.

## Unresolved decisions

- Ninguna que bloquee el build. (Jefes Karanda y Quint siguen pendientes de horario; no entran en esta superficie todavía.)

## Direction contract

THESIS: un panel de trabajo que se consulta como una carta de navegación: una mirada resuelve qué viene, cuánto falta y qué queda por hacer. Se niega al cliché dark-fantasy de juego con glow morado.

OWN-WORLD: azul marino profundo como fondo de carta, tinta bitácora sobre porcelana, latón para lo vivo y vermellón para lo anulado/crítico. Tipografía de bitácora (serif condensada de display + grotesca de trabajo). Filetes finos y rosa de los vientos como firma; estados en tinta (tachado/sello), no solo color.

STORY: el jugador abre el panel y en segundos lee el próximo jefe, el reset y sus pendientes; marca lo hecho y el estado queda estampado.

FIRST VIEWPORT: cabecera con reloj y cuenta regresiva al reset; bajo ella, el bloque "Next Boss" con la aguja de brújula como foco; la grilla de jefes y la tabla de horarios como el derrotero del día.

FORM: carta náutica / bitácora de barco; seed:95f38ab228afd0d5.

FINISH: unreviewed and undocumented is unfinished; this build ends with the finish review, the verdict, DESIGN.md, and every shipping raster carrying its provenance
