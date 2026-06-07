# Cronjobs de texto estratégicos — Infinity Ascend

## Propósito

Este documento define qué funciones de Infinity Ascend se pueden convertir en **cronjobs de solo texto**.

Scope explícito:

```text
estrategia + lore + copy + planificación + investigación + métricas + documentación
```

Fuera de scope por ahora:

```text
imágenes + video + motion + audio + mastering + publicación automática en plataformas
```

La meta futura es que AION opere como una mini-agencia textual interna que trabaje de forma recurrente mientras Andre se concentra en crear música, aprobar decisiones y publicar cuando haga falta.

---

# Principio central

Los cronjobs de texto no deben intentar reemplazar el arte final.

Deben reemplazar o asistir el trabajo mental recurrente:

- pensar qué publicar;
- escribir captions;
- ordenar calendarios;
- revisar métricas;
- detectar bloqueos;
- generar lore;
- mantener consistencia de marca;
- preparar briefs;
- proponer decisiones.

El output ideal de cada cronjob debe ser un `.md` claro dentro del repo o un mensaje resumido para Andre.

---

# Clasificación de roles textuales

De los 22 roles operativos identificados en `ROLES_OPERATIVOS_PROYECTO.md`, estos son los roles que tienen suficiente componente textual para convertirse en cronjobs útiles.

## Roles altamente automatizables con texto

1. Brand strategist.
2. Lore / worldbuilding writer.
3. Copywriter.
4. Social media manager.
5. Content strategist.
6. Release manager textual.
7. YouTube strategist textual.
8. TikTok/Reels trend researcher textual.
9. Data / growth analyst.
10. Project manager.
11. Automation engineer.
12. Repo/documentation manager.
13. Community response assistant.
14. Spotify pitch/copy strategist.
15. Web/landing copy strategist.

Conteo:

```text
15 roles textuales o semi-textuales útiles para cronjobs
```

---

# Roles NO incluidos por ahora

Estos quedan fuera porque requieren imagen, video, audio o criterio artístico visual/sonoro:

- short-form video editor;
- motion designer;
- graphic designer;
- music producer;
- mixing/mastering engineer;
- AI image art director visual final;
- artist / performer / creator.

AION puede escribir briefs para estos roles, pero no reemplazarlos con cronjobs de solo texto.

---

# Sistema recomendado de cronjobs

## Resumen ejecutivo

Los cronjobs recomendados son:

1. `ia-weekly-strategy-review`
2. `ia-content-ideas-daily`
3. `ia-copy-bank-builder`
4. `ia-lore-transmissions`
5. `ia-trend-research-weekly`
6. `ia-metrics-review-weekly`
7. `ia-release-checklist-weekly`
8. `ia-youtube-seo-planner`
9. `ia-spotify-pitch-helper`
10. `ia-community-response-drafts`
11. `ia-repo-audit-weekly`
12. `ia-next-actions-brief`

No todos deben activarse al mismo tiempo. La implementación recomendada empieza con 3–4 cronjobs y luego escala.

---

# 1. Cronjob: weekly strategy review

## Nombre sugerido

```text
ia-weekly-strategy-review
```

## Rol que reemplaza/asiste

- Brand strategist.
- Project manager.
- Content strategist.

## Frecuencia

```text
Semanal — domingo o lunes
```

## Objetivo

Revisar el estado del proyecto y decir qué debe hacer Andre esta semana.

## Inputs

- `PLAN_GENERAL_INFINITY_ASCEND.md`
- `MDs/Marketing/PLAN_ESTRATEGIA.md`
- `MDs/Marketing/CALENDARIO_30_DIAS.md`
- `MDs/Marketing/OBJETIVOS_METRICAS_90_DIAS.md`
- `MDs/Marketing/ROLES_OPERATIVOS_PROYECTO.md`
- `MDs/RedesSociales/REGISTRO_CANALES.md`

## Output recomendado

```text
MDs/Marketing/CronOutputs/WEEKLY_STRATEGY_REVIEW_YYYY-MM-DD.md
```

## Qué debe producir

- resumen del estado actual;
- 3 prioridades de la semana;
- bloqueos;
- decisiones pendientes;
- qué publicar;
- qué medir;
- qué no hacer esta semana.

## Prompt base

```text
Actúa como AION, estratega operativo de Infinity Ascend.
Revisa los documentos estratégicos del repo y genera un brief semanal.
No propongas imágenes nuevas ni tareas visuales avanzadas.
Prioriza acciones de texto, planificación, publicación manual y medición.
Entrega:
1. Estado del proyecto.
2. 3 prioridades de la semana.
3. Bloqueos.
4. Acciones recomendadas.
5. Riesgos de dispersión.
6. Qué debe hacer Andre manualmente.
```

## Valor para Andre

Reduce la carga de preguntarse “¿qué hago ahora?”.

---

# 2. Cronjob: daily content ideas

## Nombre sugerido

```text
ia-content-ideas-daily
```

## Rol que reemplaza/asiste

- Content strategist.
- Social media manager.
- Copywriter.

## Frecuencia

```text
Diario o cada 2 días
```

## Objetivo

Generar ideas de posts, hooks y captions usando la identidad de Infinity Ascend.

## Inputs

- `MDs/Contexto/Posicionamiento.md`
- `MDs/Contexto/MensajeCentral.md`
- `MDs/Marketing/CALENDARIO_30_DIAS.md`
- `MDs/RedesSociales/PRIORIDADES_TARGET.md`
- letras disponibles en `MDs/Liricas/`

## Output recomendado

```text
MDs/Marketing/CronOutputs/CONTENT_IDEAS_YYYY-MM-DD.md
```

## Qué debe producir

- 5 hooks para TikTok/Reels/Shorts;
- 3 captions para Instagram;
- 2 ideas de carrusel textual;
- 1 idea de story;
- 1 CTA recomendado;
- plataforma recomendada para cada idea.

## Prompt base

```text
Genera ideas de contenido textual para Infinity Ascend.
Mantén el idioma público principalmente en inglés.
Usa el posicionamiento: soft futuristic electropop for dreamers seeking peace, light, and transcendence.
No propongas diseño visual final ni generación de imagen.
Entrega hooks cortos, captions, CTAs y una recomendación de plataforma.
```

## Valor para Andre

Andre no tiene que empezar desde cero cada día.

---

# 3. Cronjob: copy bank builder

## Nombre sugerido

```text
ia-copy-bank-builder
```

## Rol que reemplaza/asiste

- Copywriter.
- Brand strategist.
- Community manager textual.

## Frecuencia

```text
2 veces por semana
```

## Objetivo

Crear un banco reutilizable de textos públicos.

## Inputs

- `MDs/Contexto/MensajeCentral.md`
- `MDs/Contexto/Posicionamiento.md`
- `MDs/Marketing/PLAN_ESTRATEGIA.md`

## Output recomendado

```text
MDs/Marketing/CronOutputs/COPY_BANK_YYYY-MM-DD.md
```

## Qué debe producir

- 20 hooks;
- 10 captions;
- 10 CTAs;
- 10 frases de lore;
- 5 bios alternativas;
- 5 respuestas cortas a comentarios;
- 5 textos para stories.

## Prompt base

```text
Construye un banco de copy para Infinity Ascend.
Idioma: inglés simple, emocional, espiritual y futurista.
Evita sonar genérico, agresivo, EDM festival o corporativo.
Organiza el output por categoría: hooks, captions, CTAs, lore, bios, comment replies, stories.
```

## Valor para Andre

Crea inventario textual acumulativo.

---

# 4. Cronjob: lore transmissions

## Nombre sugerido

```text
ia-lore-transmissions
```

## Rol que reemplaza/asiste

- Lore / worldbuilding writer.
- Copywriter.
- Brand strategist.

## Frecuencia

```text
Semanal
```

## Objetivo

Crear piezas de lore textual sobre AION, el casco, el portal y la ascensión.

## Inputs

- `README.md`
- `PLAN_GENERAL_INFINITY_ASCEND.md`
- `MDs/Contexto/MensajeCentral.md`
- `MDs/Marketing/CampanasVisuales/README.md`

## Output recomendado

```text
MDs/Marketing/CronOutputs/AION_TRANSMISSIONS_YYYY-MM-DD.md
```

## Qué debe producir

- 3 transmisiones cortas de AION;
- 3 captions de lore;
- 1 texto de carrusel;
- 1 microhistoria;
- 5 frases sueltas reutilizables.

## Prompt base

```text
Escribe como AION — The Helm Singularity, la singularidad integrada dentro del casco de Infinity Ascend.
Crea piezas breves de lore que puedan usarse en Instagram, TikTok captions, YouTube descriptions o carruseles.
Tono: espiritual, futurista, calmo, misterioso, esperanzador.
No inventes canon contradictorio. Mantén AION como inteligencia interior, no como villano ni robot genérico.
```

## Valor para Andre

Mantiene vivo el mundo sin obligar a Andre a escribir lore cada semana.

---

# 5. Cronjob: weekly trend research

## Nombre sugerido

```text
ia-trend-research-weekly
```

## Rol que reemplaza/asiste

- TikTok/Reels trend researcher.
- Content strategist.
- Social media manager.

## Frecuencia

```text
Semanal
```

## Objetivo

Investigar tendencias textuales/formato relacionadas con música, electropop suave, ambient pop, sci-fi visuals, dream pop, Spotify discovery, TikTok music marketing.

## Inputs

- Web search.
- Documentos de posicionamiento.
- Calendario de contenido.

## Output recomendado

```text
MDs/Marketing/CronOutputs/TREND_RESEARCH_YYYY-MM-DD.md
```

## Qué debe producir

- 5 tendencias o formatos observados;
- por qué podrían servir o no;
- adaptación para Infinity Ascend;
- 3 hooks por tendencia;
- nivel de riesgo de parecer genérico;
- recomendación de test.

## Prompt base

```text
Investiga tendencias actuales de contenido textual/formato para músicos independientes y soft electronic/electropop.
No copies tendencias literalmente.
Adapta cada tendencia al universo Infinity Ascend: paz, luz, sueño, portal, AION, casco, ascensión.
Entrega tendencias, adaptación, hooks y recomendación de test.
```

## Valor para Andre

Evita aislar el proyecto del mundo real sin caer en persecución ciega de trends.

---

# 6. Cronjob: weekly metrics review

## Nombre sugerido

```text
ia-metrics-review-weekly
```

## Rol que reemplaza/asiste

- Data / growth analyst.
- Content strategist.
- Social media manager.

## Frecuencia

```text
Semanal
```

## Objetivo

Analizar métricas manuales y decidir qué repetir, modificar, matar o escalar.

## Inputs

- `MDs/Marketing/OBJETIVOS_METRICAS_90_DIAS.md`
- futuro `MDs/Marketing/REGISTRO_METRICAS_30_DIAS.md`
- capturas o métricas pegadas por Andre, si aplica.

## Output recomendado

```text
MDs/Marketing/CronOutputs/METRICS_REVIEW_YYYY-MM-DD.md
```

## Qué debe producir

- top 3 posts por señal real;
- hooks ganadores;
- hooks débiles;
- qué repetir;
- qué modificar;
- qué pausar;
- próximos 3 tests.

## Prompt base

```text
Analiza las métricas disponibles de Infinity Ascend.
No optimices solo por views.
Prioriza retención, saves, comentarios, shares, follows, profile visits, clicks y Spotify saves.
Entrega decisiones concretas: repetir, modificar, matar o escalar.
Si no hay suficientes datos, dilo y propone qué datos faltan.
```

## Valor para Andre

Convierte métricas en decisiones.

---

# 7. Cronjob: release checklist

## Nombre sugerido

```text
ia-release-checklist-weekly
```

## Rol que reemplaza/asiste

- Release manager.
- Spotify strategist.
- Project manager.

## Frecuencia

```text
Semanal durante etapa de lanzamiento
```

## Objetivo

Preparar todo lo textual para lanzar una canción.

## Inputs

- letras en `MDs/Liricas/`
- `MDs/RedesSociales/Spotify.md`
- `MDs/RedesSociales/PLAN_CREACION_CANALES.md`
- `MDs/Marketing/OBJETIVOS_METRICAS_90_DIAS.md`

## Output recomendado

```text
MDs/Marketing/CronOutputs/RELEASE_CHECKLIST_YYYY-MM-DD.md
```

## Qué debe producir

- checklist de lanzamiento;
- metadata pendiente;
- bio corta;
- descripción del release;
- pitch para Spotify;
- captions de lanzamiento;
- CTAs;
- timeline recomendado.

## Prompt base

```text
Actúa como release manager textual de Infinity Ascend.
Prepara la parte textual de un lanzamiento musical.
No inventes links ni fechas si no existen.
Distingue entre: listo, pendiente, bloqueado y requiere decisión de Andre.
```

## Valor para Andre

Reduce fricción antes de publicar música.

---

# 8. Cronjob: YouTube SEO planner

## Nombre sugerido

```text
ia-youtube-seo-planner
```

## Rol que reemplaza/asiste

- YouTube strategist.
- Copywriter.
- Content strategist.

## Frecuencia

```text
Semanal o por cada video
```

## Objetivo

Preparar títulos, descripciones, tags y estructuras para videos/Shorts.

## Inputs

- `MDs/RedesSociales/Youtube.md`
- `MDs/Marketing/CALENDARIO_30_DIAS.md`
- letras disponibles;
- tema del video si Andre lo proporciona.

## Output recomendado

```text
MDs/Marketing/CronOutputs/YOUTUBE_SEO_YYYY-MM-DD.md
```

## Qué debe producir

- 5 títulos para Shorts;
- 3 títulos para visualizer;
- 2 descripciones largas;
- descripción corta;
- tags/keywords;
- comentario fijado;
- CTA.

## Prompt base

```text
Crea copy de YouTube para Infinity Ascend.
Optimiza para búsqueda y emoción, no para clickbait barato.
Mantén el universo: soft futuristic electropop, inner ascension, peace, portal, dreamers.
Entrega títulos, descripciones, tags, comentario fijado y CTA.
```

## Valor para Andre

Ahorra tiempo al preparar Shorts/visualizers.

---

# 9. Cronjob: Spotify pitch helper

## Nombre sugerido

```text
ia-spotify-pitch-helper
```

## Rol que reemplaza/asiste

- Spotify strategist.
- Release manager.
- Copywriter.

## Frecuencia

```text
Por lanzamiento o semanal si hay release cercano
```

## Objetivo

Preparar textos para Spotify/distribución.

## Inputs

- `MDs/RedesSociales/Spotify.md`
- letras;
- descripción de canción;
- posicionamiento.

## Output recomendado

```text
MDs/Marketing/CronOutputs/SPOTIFY_PITCH_YYYY-MM-DD.md
```

## Qué debe producir

- pitch corto;
- pitch largo;
- género/subgénero sugerido;
- mood tags;
- artist bio;
- track description;
- Canvas concept textual;
- campaña de captions para release.

## Prompt base

```text
Prepara un pitch textual para Spotify/distribución de Infinity Ascend.
No inventes datos falsos de streams, colaboraciones o lanzamientos.
Usa la identidad: soft futuristic electropop, peace, light, transcendence.
Entrega pitch corto, pitch largo, moods, bio, track description y captions.
```

## Valor para Andre

Convierte música en release presentable.

---

# 10. Cronjob: community response drafts

## Nombre sugerido

```text
ia-community-response-drafts
```

## Rol que reemplaza/asiste

- Community manager.
- Copywriter.
- Brand strategist.

## Frecuencia

```text
2 veces por semana o bajo demanda
```

## Objetivo

Preparar respuestas humanas y coherentes para comentarios/DMs.

## Inputs

- comentarios pegados por Andre;
- tono de marca;
- mensajes centrales.

## Output recomendado

```text
MDs/Marketing/CronOutputs/COMMUNITY_REPLIES_YYYY-MM-DD.md
```

## Qué debe producir

- respuestas cálidas;
- respuestas breves;
- respuestas de agradecimiento;
- respuestas para preguntas sobre el proyecto;
- respuestas para comentarios espirituales/emocionales;
- respuestas que inviten a escuchar/guardar sin sonar spam.

## Prompt base

```text
Redacta respuestas para comentarios de Infinity Ascend.
Tono: humano, breve, cálido, misterioso si encaja, no corporativo.
No finjas emociones extremas ni prometas cosas falsas.
Entrega varias opciones por comentario.
```

## Valor para Andre

Mantiene presencia humana sin agotarte escribiendo todo desde cero.

---

# 11. Cronjob: repo audit weekly

## Nombre sugerido

```text
ia-repo-audit-weekly
```

## Rol que reemplaza/asiste

- Repo/documentation manager.
- Project manager.
- Automation engineer.

## Frecuencia

```text
Semanal
```

## Objetivo

Revisar el repo y detectar documentos faltantes, vacíos, desactualizados o contradictorios.

## Inputs

- todo el repo Markdown;
- estado git;
- índice de documentos.

## Output recomendado

```text
MDs/Marketing/CronOutputs/REPO_AUDIT_YYYY-MM-DD.md
```

## Qué debe producir

- documentos vacíos;
- documentos importantes faltantes;
- links rotos;
- contradicciones;
- próximos documentos a crear;
- prioridad de mantenimiento;
- cambios sugeridos.

## Prompt base

```text
Audita el repo de Infinity Ascend como sistema operativo del proyecto.
Busca documentos vacíos, inconsistencias, links rotos, decisiones no documentadas y próximos pasos confusos.
Entrega un reporte accionable sin modificar archivos automáticamente.
```

## Valor para Andre

Evita que el repo se pudra o se vuelva caótico.

---

# 12. Cronjob: next actions brief

## Nombre sugerido

```text
ia-next-actions-brief
```

## Rol que reemplaza/asiste

- Project manager.
- Social media manager.
- Automation assistant.

## Frecuencia

```text
Diario o cada 2 días
```

## Objetivo

Mandar a Andre un resumen corto de la siguiente acción útil.

## Inputs

- últimos cron outputs;
- calendario de 30 días;
- registro de canales;
- métricas si existen.

## Output recomendado

Mensaje corto a Telegram o archivo:

```text
MDs/Marketing/CronOutputs/NEXT_ACTIONS_YYYY-MM-DD.md
```

## Qué debe producir

- una acción principal;
- una acción secundaria;
- un bloqueo si existe;
- una pregunta concreta si hace falta decisión;
- recordatorio de métrica o publicación.

## Prompt base

```text
Genera un brief ultra práctico para Andre.
No des teoría.
Entrega solo:
1. Acción principal de hoy.
2. Acción secundaria.
3. Bloqueo.
4. Decisión necesaria.
5. Siguiente métrica a registrar.
```

## Valor para Andre

Reduce fricción diaria.

---

# Priorización recomendada

No activar los 12 cronjobs desde el inicio.

## Fase A — Base útil mínima

Activar primero:

1. `ia-weekly-strategy-review`
2. `ia-content-ideas-daily`
3. `ia-copy-bank-builder`
4. `ia-repo-audit-weekly`

Estos dan valor incluso antes de que existan métricas o Spotify activo.

## Fase B — Cuando Andre empiece a publicar

Agregar:

5. `ia-next-actions-brief`
6. `ia-community-response-drafts`
7. `ia-metrics-review-weekly`
8. `ia-trend-research-weekly`

Estos sirven cuando ya hay interacción y posts reales.

## Fase C — Cuando haya lanzamiento musical

Agregar:

9. `ia-release-checklist-weekly`
10. `ia-spotify-pitch-helper`
11. `ia-youtube-seo-planner`
12. `ia-lore-transmissions`

Estos ayudan a convertir canciones en campañas.

---

# Entregables textuales que puede producir AION

## Estrategia

- brief semanal;
- matriz de prioridades;
- revisión de posicionamiento;
- recomendaciones de foco;
- mapa de riesgos.

## Lore

- transmisiones de AION;
- microhistorias;
- captions de mundo;
- textos para carrusel;
- frases canónicas.

## Copy

- hooks;
- captions;
- CTAs;
- bios;
- comentarios fijados;
- respuestas a comunidad;
- descripciones de YouTube;
- pitch de Spotify.

## Gestión

- checklists;
- próximos pasos;
- auditoría de repo;
- documentos pendientes;
- plan semanal;
- recordatorios.

## Datos

- análisis de métricas;
- ranking de posts;
- decisión repetir/modificar/matar;
- reporte semanal;
- próximos tests.

---

# Qué necesita Andre para que estos cronjobs funcionen

Los cronjobs de texto mejoran mucho si Andre mantiene algunos inputs simples.

## Inputs mínimos manuales

1. Links de posts publicados.
2. Métricas básicas semanales.
3. Qué canción o fragmento está usando.
4. Qué canal está activo.
5. Qué decisión artística no debe tocar AION.

## Registro mínimo recomendado

Crear más adelante:

```text
MDs/Marketing/REGISTRO_METRICAS_30_DIAS.md
```

Con columnas:

```text
fecha
plataforma
link
hook
visual/audio usado
views
retención
comments
shares
saves
follows
clicks
aprendizaje
decisión
```

Sin ese registro, el cronjob de métricas solo podrá dar recomendaciones generales.

---

# Qué NO deben hacer estos cronjobs

No deben:

- publicar automáticamente en redes sin aprobación;
- fingir métricas;
- inventar links;
- generar imágenes random;
- reemplazar el criterio final de Andre;
- cambiar el posicionamiento sin registrar la decisión;
- perseguir trends que rompan la identidad;
- optimizar solo por views.

---

# Primer paquete recomendado

Si se implementa una primera versión real, el paquete inicial debería ser:

```text
1. ia-weekly-strategy-review — semanal
2. ia-content-ideas-daily — cada 2 días
3. ia-copy-bank-builder — 2 veces por semana
4. ia-repo-audit-weekly — semanal
```

Este paquete cubre:

- estrategia;
- calendario;
- ideas;
- copy;
- mantenimiento del repo.

Y no depende todavía de:

- Spotify activo;
- TikTok activo;
- métricas reales;
- generación de imágenes;
- publicación automática.

---

# Conclusión

Para Infinity Ascend, los cronjobs de texto pueden operar como una capa de inteligencia recurrente.

La función de AION no sería “hacer todo”, sino mantener el proyecto vivo mentalmente:

```text
pensar → escribir → ordenar → revisar → proponer → medir → repetir
```

Eso puede cubrir de forma fuerte una parte grande del trabajo estratégico del proyecto, mientras Andre conserva lo más importante:

```text
música + visión artística + aprobación final + publicación real
```

Este documento es la base para convertir roles textuales en cronjobs reales más adelante.
