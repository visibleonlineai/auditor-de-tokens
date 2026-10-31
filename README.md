# Auditor de tokens para Claude

Skill gratuita de [Visible Online AI](https://visibleonlineai.com) que revisa tus tareas programadas de Claude y te dice dónde estás quemando tokens de más.

## El problema

Si usás Claude para automatizar, seguro tenés tareas que corren todos los días con el modelo más caro para hacer cosas que no necesitan pensar: leer una planilla, copiar datos de un lado a otro, mandarte un resumen con formato fijo. Y cada una carga conectores que no usa.

Resultado: te quedás sin cuota a mitad de semana y pensás que necesitás el plan más caro.

## Qué hace

Revisa cada tarea programada con 7 chequeos:

1. ¿Necesita criterio o solo mueve datos? → si solo mueve datos, se pasa a **n8n o Make** (cero tokens de Claude).
2. ¿Usa un modelo más grande del que necesita?
3. ¿Carga conectores que no usa?
4. ¿Hay tareas encadenadas o duplicadas?
5. ¿Está fallando y gastando igual?
6. ¿Corre más seguido de lo necesario?
7. ¿El prompt carga cosas "por las dudas"?

Te devuelve una tabla con el ahorro estimado por tarea y las 3 acciones de mayor impacto. **No cambia nada sin tu OK.** Si tenés n8n conectado, puede armarte el flujo de reemplazo, probarlo y recién ahí apagar la tarea de Claude.

## Caso real

En la primera auditoría (la nuestra) encontró:
- Dos tareas diarias con el modelo grande que solo leían datos y armaban un mensaje → pasaron a un flujo de n8n que manda el mismo resumen por mail.
- Una tarea semanal pesada que no necesitaba el modelo grande → pasó al intermedio.
- Conectores de diseño y pizarras cargados en tareas que nunca los usaban.

De ~64 corridas del modelo grande por mes a 0, y 4 corridas del intermedio.

## Instalación

1. Descargá la carpeta `auditor-de-tokens` (o el .zip).
2. En Claude: Configuración → Personalizar → Skills → subir el .zip. (En Claude Code: copiá la carpeta a `~/.claude/skills/`.)
3. Escribile: **"Auditá mis tareas programadas"**.

## ¿Querés que lo hagamos por vos?

Si tu equipo usa Claude, n8n o Make y querés ordenar costos y automatizaciones, hacé el diagnóstico gratis en [visibleonlineai.com/chequeo](https://visibleonlineai.com/chequeo).

Licencia: MIT.
