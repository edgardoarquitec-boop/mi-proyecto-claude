# Oficina de Arquitectura con agentes de Claude

Una oficina virtual con agentes especializados (subagentes de Claude Code) que te ayudan a evaluar, formalizar y presupuestar proyectos de arquitectura.

## Equipo

- **Director de la oficina** (Claude, configurado en `CLAUDE.md`): recibe el encargo, arma la ficha del proyecto y coordina al equipo.
- **Prefactibilidad y viabilidad** (`.claude/agents/prefactibilidad-viabilidad.md`): normativa urbana, cabida, mercado, viabilidad técnica y financiera (VAN, TIR, sensibilidad) y riesgos.
- **Acta de constitución** (`.claude/agents/acta-constitucion.md`): Project Charter según el PMBOK: objetivos, alcance, entregables, hitos, interesados, autoridad y firmas.
- **Asistente de presupuesto** (`.claude/agents/asistente-presupuesto.md`): presupuesto paramétrico, por capítulos o detallado con APU, AIU e impuestos, en Markdown y CSV.

## Cómo usarla

Abre Claude Code en este repositorio y escribe, por ejemplo:

> Tengo un lote de 300 m² en [ciudad] y quiero construir 6 apartamentos para vender. ¿Es viable?

> Haz el acta de constitución del proyecto "edificio-los-pinos".

> Usa el asistente de presupuesto para estimar una casa de 180 m² con acabados medios en [ciudad].

También puedes llamar a un agente directamente: `@prefactibilidad-viabilidad`, `@acta-constitucion` o `@asistente-presupuesto`.

Cada proyecto se guarda en `proyectos/<nombre-del-proyecto>/`:

```
00-ficha.md
01-prefactibilidad.md
02-acta-de-constitucion.md
03-presupuesto.md
03-presupuesto.csv
```

## Agregar más agentes

Crea un archivo `.md` en `.claude/agents/` con este encabezado y luego las instrucciones:

```markdown
---
name: nombre-del-agente
description: Cuándo debe usarse este agente.
tools: Read, Write, Edit
---
```

Ideas: programa arquitectónico, cronograma de obra, memoria descriptiva, gestión de licencias, propuesta de honorarios.
