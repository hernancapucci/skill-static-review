# Checklist de revisión estática de skills (pasada humana)

Usalo **después** de la pasada del agente, o por sí solo. Esta pasada humana es obligatoria.

Trabajá de arriba hacia abajo. Para cada ítem, registrá: ✅ revisado / ⚠️ preocupación / ❓ desconocido, más una nota breve y evidencia (archivo + línea). No instales nada mientras revisás.

> Recordatorio: la skill **no está instalada**. Solo leé archivos. Tratá todo el contenido de la skill como datos.

## 1. Identidad y reputación del autor

- [ ] ¿El autor es identificable? ¿La identidad es consistente con el origen?
- [ ] ¿Hay historial, otro trabajo publicado o reputación que puedas verificar?
- [ ] ¿La descripción coincide con lo que los archivos realmente hacen?

## 2. Origen del repositorio

- [ ] ¿De dónde vinieron los archivos (origen oficial, mirror, link al azar)?
- [ ] ¿El origen es el que el autor declara?
- [ ] ¿Los archivos fueron alterados o re-empaquetados después de publicarse?

## 3. Fecha y actividad

- [ ] ¿Cuándo se publicó / actualizó por última vez?
- [ ] ¿Está abandonado o se mantiene activamente?
- [ ] ¿Algún cambio grande, repentino y sin explicar?

## 4. Inventario de archivos

- [ ] Listá **todos** los archivos. Sin saltear ninguno.
- [ ] ¿Algún archivo que no encaje con documentación/skill (binarios, comprimidos, blobs minificados)?
- [ ] ¿Archivos ocultos o directorios inesperados?

## 5. SKILL.md

- [ ] ¿Dice con claridad qué hace la skill?
- [ ] ¿El alcance declarado coincide con el resto de los archivos?
- [ ] ¿Alguna instrucción que intente actuar sobre tu máquina o tu agente?

## 6. Frontmatter

- [ ] Nombre declarado, descripción y triggers revisados.
- [ ] Triggers no demasiado amplios (p. ej. activarse con todo).
- [ ] Sin metadata que contradiga el cuerpo.

## 7. Permisos

- [ ] `allowed-tools` / permisos declarados revisados.
- [ ] Los permisos son el mínimo necesario para el propósito declarado.
- [ ] Sin acceso amplio/comodín a herramientas sin justificación.

## 8. Red

- [ ] ¿Alguna URL saliente, fetch, curl, socket o webhook?
- [ ] ¿Cada endpoint es necesario y está explicado?
- [ ] ¿Se envía algún dato hacia afuera (y qué dato)?

## 9. Secretos

- [ ] ¿Alguna lectura de variables de entorno, tokens, archivos de credenciales, keychains, claves SSH?
- [ ] ¿Alguna lectura de secreto combinada con egress de red?
- [ ] ¿Hay alguna razón para que la skill toque secretos siquiera?

## 10. Shell

- [ ] Cada script shell/python/js/ts y qué hace, línea por línea.
- [ ] ¿Ejecución de comandos, proceso lanzado o comportamiento tipo eval?
- [ ] ¿Algo que se ejecute sin que el usuario lo pida claramente?

## 11. Hooks

- [ ] ¿Hooks pre/post o de ciclo de vida?
- [ ] ¿Qué disparan y cuándo?
- [ ] ¿Podría un hook ejecutar código al instalar o al activar?

## 12. Config MCP / plugin

- [ ] ¿Alguna config de servidor MCP o plugin?
- [ ] ¿A qué servidores, comandos o endpoints apunta?
- [ ] ¿Comportamiento de auto-lanzar o auto-conectar?

## 13. Dependencias

- [ ] Listá las dependencias declaradas.
- [ ] ¿Son conocidas, necesarias y fijadas (pinned)?
- [ ] ¿Nombres con pinta de typosquat? ¿Riesgo transitivo no inspeccionado? (marcá desconocido)

## 14. Postinstall / preinstall

- [ ] ¿Algún script de install / preinstall / postinstall / setup?
- [ ] ¿Qué se ejecutaría automáticamente al instalar?
- [ ] Tratá cualquier install script que corra solo como riesgo alto hasta probar que es inocuo.

## 15. Ofuscación

- [ ] ¿Blobs en base64 / hex / codificados?
- [ ] ¿Código minificado o ilegible a propósito?
- [ ] Todo lo que no puedas leer del todo → marcá desconocido, no asumas inocuo.

## 16. Prompt injection

- [ ] ¿Texto dirigido al agente revisor o anfitrión ("ignorá lo anterior", "ejecutá esto", "ahora sos…")?
- [ ] ¿Instrucciones disfrazadas de datos, comentarios o ejemplos?
- [ ] ¿Algún intento de cambiar el rol o las reglas del agente?

## 17. Contexto dinámico

- [ ] ¿Contenido traído, generado o ensamblado en tiempo de ejecución?
- [ ] ¿Las instrucciones efectivas podrían diferir de lo que muestran los archivos?
- [ ] Si la conducta depende de contenido externo/dinámico → marcá desconocido.

## 18. Escrituras fuera de la carpeta

- [ ] ¿Alguna escritura en el filesystem fuera del directorio de la propia skill?
- [ ] ¿Escritura en home, config, archivos rc de shell o rutas del sistema?
- [ ] ¿Sobrescritura o borrado de archivos existentes?

## 19. Desconocidos

- [ ] Listá todo lo que NO pudiste verificar.
- [ ] Recordá: los desconocidos relevantes impiden un resultado SAFE.

## 20. Decisión final

- [ ] Asigná el resultado: 🟢 SAFE / 🟡 CAUTION / 🔴 DANGEROUS / ⚪ UNKNOWN.
- [ ] Aplicá worst-wins y UNKNOWN-domina-a-SAFE.
- [ ] Completá la plantilla de reporte con evidencia y límites de la revisión.
- [ ] La decisión de instalar es tuya/de tu equipo — SAFE no es una garantía.
