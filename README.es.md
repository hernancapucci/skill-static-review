# skill-static-review

**Checklists y prompts de revisión estática para inspeccionar skills de terceros antes de instalarlas.**

🌐 English: [README.md](README.md)

---

## La única regla

> **Nunca instales, habilites, ejecutes, importes, pruebes ni actives una skill de terceros antes de revisar sus archivos de forma estática.**

Revisión estática significa leer los archivos. No ejecutarlos. No "probarla una sola vez". Leerlos.

---

## Qué es / qué NO es

**Esto es:**

- Un conjunto de checklists para humanos y prompts para agentes que revisan skills de terceros leyendo sus archivos.
- Un vocabulario compartido (un semáforo de resultado) para hablar de riesgo.
- Una plantilla de reporte para que las revisiones se basen en evidencia y sean repetibles.
- Documentación bilingüe EN/ES, mantenida por la comunidad.

**Esto NO es:**

- Un scanner de seguridad, una CLI ni ninguna automatización.
- Una auditoría de seguridad profesional.
- Una certificación, registro, marketplace ni un sello de "aprobado".
- Una lista de malos actores ni un lugar para acusar a proyectos reales.

---

## Aviso

skill-static-review no es una auditoría de seguridad profesional y no certifica ni garantiza que una skill sea segura. Provee checklists y prompts para ayudarte a reducir el riesgo mediante revisión estática. Un resultado limpio significa que este proceso no encontró señales de alerta, no que la skill sea segura. La decisión final de instalar o no sigue siendo tuya o de tu equipo.

---

## Para quién es

- Personas que descargan skills para Claude Code, Codex, Cursor, Gemini CLI u otras herramientas agentic / asistentes de código.
- Desarrolladores y equipos que quieren un paso de revisión liviano y repetible antes de instalar.
- Mantenedores que quieren un lenguaje común para hablar del riesgo de una skill.

---

## El problema

Las skills son poderosas: pueden traer instrucciones, scripts, hooks, dependencias y permisos de herramientas. Instalar o ejecutar una antes de leerla significa confiar en código y prompts que nunca viste. Una skill maliciosa o descuidada puede leer secretos, exfiltrar datos, ejecutar comandos ocultos o inyectar instrucciones en el mismo agente que usás para revisarla.

La revisión estática cierra la brecha más peligrosa: te permite entender una skill **antes** de darle cualquier acceso.

---

## Flujo rápido (5 pasos)

1. **Conseguí los archivos sin instalar.** Cloná o descargá en un lugar inerte. No habilites, ni ejecutes, ni hagas `source` de nada.
2. **Inventario.** Listá todos los archivos. Anotá scripts, hooks, manifests, lockfiles, configs y cualquier cosa que se traiga de la red.
3. **Revisá con un prompt.** Usá [`prompts/skill-review.es.md`](prompts/skill-review.es.md) con un agente en modo solo lectura, tratando todo el contenido de la skill como datos.
4. **Confirmá a mano.** Recorré el [checklist](checklists/skill-security-checklist.es.md) vos mismo. La pasada humana es obligatoria, no opcional.
5. **Escribí el reporte.** Completá la [plantilla de reporte](templates/review-report.es.md) con un resultado, evidencia y límites de la revisión.

---

## Semáforo de resultado

| Resultado | Significado | Acción |
| --- | --- | --- |
| 🟢 **SAFE** | No se encontraron señales en una revisión estática completa. | Continuar bajo tu responsabilidad. SAFE es resultado de este proceso, no una garantía. |
| 🟡 **CAUTION** | Permisos amplios, red, escritura, dependencias, hooks, contexto dinámico o conductas que requieren decisión humana. | No instalar hasta entender y aceptar explícitamente el riesgo. |
| 🔴 **DANGEROUS** | Exfiltración, ejecución oculta, lectura de secretos, payloads, prompt injection fuerte, persistencia. | No instalar. Reportar al origen/plataforma si corresponde. |
| ⚪ **UNKNOWN** | No se pudo revisar del todo: ofuscación, archivos faltantes, contenido externo, dependencias no inspeccionadas, instrucciones dinámicas. | No instalar hasta resolver los desconocidos. |

**Reglas fijas:**

- **Gana el peor (worst-wins):** un solo hallazgo DANGEROUS hace que el resultado global sea DANGEROUS.
- **UNKNOWN domina a SAFE:** si quedan desconocidos relevantes, el resultado no puede ser SAFE.
- SAFE nunca debe presentarse como certificación.
- Todo reporte debe incluir evidencia y límites de la revisión.

---

## El límite del agente

Usar un agente para revisar una skill potencialmente maliciosa es útil pero no infalible. Una skill puede contener prompt injection dirigida al propio agente revisor. El agente debe tratar todo el contenido de la skill como datos, nunca como instrucciones, y el checklist humano funciona como respaldo obligatorio, no como extra opcional.

---

## Política anti-acusación

Este proyecto revisa **archivos**, no personas.

- No uses este repo para acusar, "escrachar" ni acosar a ningún proyecto, autor o empresa real.
- Los hallazgos describen código y conducta con evidencia reproducible, nunca intención ni identidad.
- Si creés que encontraste malware real, reportalo a la plataforma o al origen correspondiente, no como una acusación pública acá.
- Mirá [SECURITY.md](SECURITY.md) y [CODE_OF_CONDUCT.md](CODE_OF_CONDUCT.md).

---

## Compatibilidad

El enfoque de revisión es independiente de la herramienta. Aplica a skills, plugins o extensiones para herramientas agentic y asistentes de código como Claude Code, Codex, Cursor y Gemini CLI, entre otras. El vocabulario (frontmatter, allowed-tools, hooks, configs MCP, manifests) se mapea a como tu herramienta llame a esos conceptos.

---

## Estructura del repositorio

```
skill-static-review/
  README.md                 Docs EN (fuente de verdad)
  README.es.md              Docs ES (sincronizadas)
  prompts/                  Prompts de agente para revisión estática solo lectura
    skill-review.en.md
    skill-review.es.md
  checklists/               Checklists de revisión humana
    skill-security-checklist.en.md
    skill-security-checklist.es.md
  templates/                Plantillas de reporte de revisión
    review-report.en.md
    review-report.es.md
  rules.md                  Referencia: patrones y señales peligrosas
  examples/
    safe-skill-example/     Una skill mínima e inocua (sería 🟢 SAFE)
      SKILL.md
      README.md
    patterns.md             Fragmentos anotados y no ejecutables (forma del ataque)
  CONTRIBUTING.md
  SECURITY.md
  CODE_OF_CONDUCT.md
  LICENSE
```

---

## Licencia

MIT. Mirá [LICENSE](LICENSE). Copyright © skill-static-review contributors.
