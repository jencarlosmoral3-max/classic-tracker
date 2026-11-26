# Handoff — Classic Physique Tracker

Documento vivo. Se actualiza al cerrar cada cambio.

## Estado actual
- PWA estática (`index.html` + `sw.js`), datos en `localStorage`. Sin build, sin CI.
- Programa UL/PPL 5 días, objetivo recomposición con enfoque Classic Physique.

## Registro de cambios

### 2026-11-25 — Más deltoide lateral y posterior, menos anterior
**Por qué:** el lateral tenía 7 series directas/semana (prioridad de la categoría) y el posterior solo 1 día/semana, mientras el anterior recibía ~15 series entre press inclinado, plano, militar y Arnold. En recomposición se reparte volumen en vez de sumarlo.

**Cambio:**
- Push: `arnold` (Press Arnold, 2 series) → `yraise` (Y-raise en banco inclinado, 3 × 12–15). Id nuevo a propósito: el historial "la vez anterior" se busca por id.
- Upper: `revcab` (Pájaros en polea cruzada, 2 × 15–20) en superserie B con `latdb`.
- `WU`: `yraise:0`, `revcab:0`. Tabla de volumen del Plan actualizada (lateral 10, posterior 8).
- `sw.js`: `cpt-v18` para que la PWA instalada tome el shell nuevo.

**Decisiones:**
- Trapecio superior sin trabajo directo, a propósito (Classic premia la V; trapecio alto estrecha visualmente el hombro). Medio/inferior cubiertos por remos, face pull, pájaros, Y-raise.
- Sesiones `arnold` viejas quedan en `localStorage` como entradas huérfanas: cuentan en volumen/series del historial, no rompen nada.

**Verificado:** `node --check` del script inline y de `sw.js`; `/code-review` sin hallazgos.
**No verificado:** la app abierta en navegador/teléfono tras el deploy.
**Revertir:** `git revert` del commit de este cambio.
