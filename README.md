# Mastermind · Ideas que Suman (Silban360)

App web (pensada para móvil) para gamificar un centro de entrenamiento personal: los socios envían sugerencias para mejorar el centro y facturar más, y ganan puntos, niveles, insignias y premios.

## Funcionalidades

**Socios**
- Enviar ideas (título, descripción, categoría e impacto estimado en €/mes)
- Ver y votar las ideas de otros socios
- Puntos, niveles (Bronce → Leyenda) e insignias
- Ranking mensual e histórico
- Catálogo de premios canjeables con puntos

**Administración del centro**
- Revisar ideas: aprobar, marcar como implantada, descartar, bonus y mensaje al socio
- Gestionar entregas de premios canjeados
- Resumen con ingresos estimados de las ideas implantadas
- Editar premios, puntos por acción y nombre del centro
- "Reto del mes": multiplicador de puntos para una categoría

## Sistema de puntos (por defecto, editable)

| Acción | Puntos |
|---|---|
| Enviar una idea | +10 |
| Idea aprobada | +50 |
| Idea implantada | +150 |
| Bonus por impacto | a criterio del centro |
| Voto recibido | +2 |
| Voto dado | +1 |

Los puntos se calculan a partir de las ideas, revisiones, votos y canjes (no se guarda un saldo editable).

## Estructura

- `index.html` — app completa (HTML + CSS + JS, sin dependencias de build).

## Almacenamiento

Usa una capa `store` con dos implementaciones:
- **live**: base de datos compartida de Claude Artifacts (`claude.use("db")`).
- **demo**: `localStorage` con datos de ejemplo, si no hay base de datos.

Colecciones: `members`, `suggestions`, `reviews`, `votes`, `redemptions`, `deliveries`, `config`.

## Próximos pasos

Para usarla con socios reales: desplegar en un hosting propio (p. ej. Vercel) y sustituir `makeDbStore` por un backend con login (p. ej. Supabase o Firebase).

## Identidad visual (Silban360)

- Color principal: `#018792` (verde azulado) · oscuro `#015F67`
- Texto: `#383D3D` (gris antracita)
- Acento: `#D00023` (rojo)
- Tipografías: **Bebas Neue** (titulares y botones) y **Source Sans** (texto)
