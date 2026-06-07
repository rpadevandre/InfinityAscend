# Cronjobs reales de Hermes activos — Infinity Ascend

## Propósito

Este documento registra los cronjobs reales de Hermes creados para Infinity Ascend.

Estos cronjobs trabajan solo con texto:

```text
estrategia + copy + lore + planificación + investigación ligera + auditoría de repo
```

No hacen:

```text
imágenes + video + audio + mastering + publicación automática + commits automáticos
```

La idea es que AION funcione como una mini-agencia textual recurrente y entregue outputs útiles a Andre por Telegram/origen.

---

# Estado actual

Fecha de creación inicial: 2026-06-07

Cronjobs creados:

```text
4 cronjobs estratégicos de texto
```

Todos usan:

- Skill: `music-artist-marketing`
- Workdir: `/home/hermes/InfinityAscend`
- Toolsets: `file`, `terminal`
- Delivery: `origin` — este chat de Telegram
- Commits automáticos: no
- Publicación automática: no

---

# 1. ia-weekly-strategy-review

## Job ID

```text
c9e398bc2fa2
```

## Schedule

```text
0 9 * * 1
```

Equivalente:

```text
lunes a las 09:00 UTC
```

## Objetivo

Revisar semanalmente el proyecto y entregar:

- estado del proyecto;
- 3 prioridades;
- bloqueos;
- acciones recomendadas;
- riesgos de dispersión;
- qué debe hacer Andre manualmente;
- qué NO hacer esa semana.

## Output esperado

```text
MDs/Marketing/CronOutputs/WEEKLY_STRATEGY_REVIEW_<fecha>.md
```

## Rol cubierto

- Brand strategist.
- Project manager.
- Content strategist.

---

# 2. ia-content-ideas-daily

## Job ID

```text
f6c362f28242
```

## Schedule

```text
every 48h
```

Equivalente:

```text
cada 2 días
```

## Objetivo

Generar ideas recurrentes de contenido textual:

- hooks para TikTok/Reels/Shorts;
- captions para Instagram;
- ideas de carrusel textual;
- idea de story;
- CTA recomendado;
- plataforma recomendada.

## Output esperado

```text
MDs/Marketing/CronOutputs/CONTENT_IDEAS_<fecha>.md
```

## Rol cubierto

- Content strategist.
- Social media manager.
- Copywriter.

---

# 3. ia-copy-bank-builder

## Job ID

```text
973c301fe8c4
```

## Schedule

```text
0 11 * * 2,5
```

Equivalente:

```text
martes y viernes a las 11:00 UTC
```

## Objetivo

Crear bancos reutilizables de copy:

- 20 hooks;
- 10 captions;
- 10 CTAs;
- 10 frases de lore;
- 5 bios alternativas;
- 5 respuestas cortas a comentarios;
- 5 textos para stories.

## Output esperado

```text
MDs/Marketing/CronOutputs/COPY_BANK_<fecha>.md
```

## Rol cubierto

- Copywriter.
- Brand strategist.
- Community manager textual.

---

# 4. ia-repo-audit-weekly

## Job ID

```text
75ea8c1726a0
```

## Schedule

```text
0 12 * * 5
```

Equivalente:

```text
viernes a las 12:00 UTC
```

## Objetivo

Auditar el repo como sistema operativo del proyecto:

- documentos vacíos o casi vacíos;
- documentos faltantes;
- links internos rotos;
- contradicciones estratégicas;
- próximos pasos confusos;
- documentos que conviene actualizar.

## Output esperado

```text
MDs/Marketing/CronOutputs/REPO_AUDIT_<fecha>.md
```

## Rol cubierto

- Repo/documentation manager.
- Project manager.
- Automation engineer.

---

# Reglas comunes

Todos los cronjobs tienen estas reglas:

1. No inventar métricas, links, canales o lanzamientos.
2. No generar imágenes, videos ni audio.
3. No publicar automáticamente.
4. No hacer commits ni pushes automáticamente.
5. Crear outputs Markdown dentro de `MDs/Marketing/CronOutputs/`.
6. Entregar resumen corto a Andre.
7. Mantener Infinity Ascend como soft futuristic electropop, no EDM/festival/rave.

---

# Cómo gestionarlos en Hermes

## Listar cronjobs

```bash
hermes cron list
```

O desde AION/Hermes:

```text
cronjob action=list
```

## Ejecutar uno manualmente

Ejemplo:

```text
cronjob action=run job_id=c9e398bc2fa2
```

## Pausar uno

```text
cronjob action=pause job_id=<job_id>
```

## Reanudar uno

```text
cronjob action=resume job_id=<job_id>
```

## Eliminar uno

Primero listar para confirmar el ID:

```text
cronjob action=list
```

Luego:

```text
cronjob action=remove job_id=<job_id>
```

---

# Próximos cronjobs posibles

No activados todavía:

1. `ia-lore-transmissions`
2. `ia-trend-research-weekly`
3. `ia-metrics-review-weekly`
4. `ia-release-checklist-weekly`
5. `ia-youtube-seo-planner`
6. `ia-spotify-pitch-helper`
7. `ia-community-response-drafts`
8. `ia-next-actions-brief`

Estos conviene activarlos cuando:

- haya publicaciones reales;
- Andre registre métricas;
- exista un release cercano;
- haya canal de YouTube/Spotify/TikTok listo;
- existan comentarios/DMs que responder.

---

# Nota importante

Hay otro cronjob existente fuera de este paquete:

```text
monitor-investigacion — f1c486fffd33
```

Ese pertenece al sistema de investigación/YouTube y actualmente puede fallar por bloqueo de YouTube desde VPS/datacenter. No forma parte de los cronjobs estratégicos de Infinity Ascend.
