# Contributing / Contribuir

Thanks for helping improve skill-static-review. This is a lightweight,
documentation-first, community project. Keep changes simple and easy to
maintain.

Gracias por ayudar a mejorar skill-static-review. Es un proyecto comunitario,
liviano y centrado en documentación. Mantené los cambios simples y fáciles de
mantener.

---

## Bilingual rule (EN/ES) / Regla bilingüe

English is the source of truth. Spanish must stay in sync as a natural,
equivalent version.

- **Edit English first.**
- **Then update the Spanish version in the same change.**
- **Do not let EN/ES drift.**

El inglés es la fuente de verdad. El español debe mantenerse sincronizado como
una versión equivalente y natural.

- **Editá primero el inglés.**
- **Después actualizá la versión en español en el mismo cambio.**
- **No dejes que EN/ES se desincronicen.**

---

## What we accept / Qué aceptamos

- Improvements to checklists, prompts, templates, rules, and examples.
- Clearer wording, better organization, fixes to EN/ES drift.
- New annotated, non-runnable pattern *shapes* in `examples/patterns.md`.

- Mejoras a checklists, prompts, plantillas, reglas y ejemplos.
- Redacción más clara, mejor organización, arreglos de desincronización EN/ES.
- Nuevas *formas* de patrones anotadas y no ejecutables en `examples/patterns.md`.

---

## Hard rules / Reglas firmes

- **No functional malware.** Never add working malware, real payloads, working
  base64, or anything reassemblable into an attack. Use `.invalid` / `.example`
  hosts and placeholders, and mark fragments **DO NOT RUN**.
- **No naming real projects as malicious.** Do not name, accuse, or imply that
  any real project, author, or company is malicious.
- **No accusations without reproducible evidence.** Findings describe code and
  behavior, with evidence — never intent or identity.
- **No badges or certification language.** This project does not certify,
  approve, or guarantee any skill. SAFE is a process result, not a guarantee.
- **No scanners or automation** (CLI, GitHub Actions, scanners, bots) unless
  future maintainers explicitly decide to add them. This repo is intentionally
  static documentation.
- **Keep it simple and low-maintenance.**

- **Nada de malware funcional.** Nunca agregues malware que funcione, payloads
  reales, base64 funcional ni nada rearmable en un ataque. Usá hosts
  `.invalid` / `.example` y placeholders, y marcá los fragmentos **DO NOT RUN**.
- **No nombrar proyectos reales como maliciosos.** No nombres, acuses ni
  insinúes que un proyecto, autor o empresa real es malicioso.
- **Sin acusaciones sin evidencia reproducible.** Los hallazgos describen código
  y conducta, con evidencia — nunca intención ni identidad.
- **Sin lenguaje de sellos ni certificación.** Este proyecto no certifica,
  aprueba ni garantiza ninguna skill. SAFE es un resultado del proceso, no una
  garantía.
- **Sin scanners ni automatización** (CLI, GitHub Actions, scanners, bots) salvo
  que los mantenedores futuros decidan explícitamente agregarlos. Este repo es
  documentación estática a propósito.
- **Mantenelo simple y de bajo mantenimiento.**

---

## How to propose a change / Cómo proponer un cambio

1. Make the EN change and the matching ES change together.
2. Keep edits focused and small.
3. If touching `examples/patterns.md`, re-read the hard rules above first.

1. Hacé el cambio en EN y el cambio equivalente en ES juntos.
2. Mantené las ediciones acotadas y chicas.
3. Si tocás `examples/patterns.md`, releé primero las reglas firmes de arriba.
