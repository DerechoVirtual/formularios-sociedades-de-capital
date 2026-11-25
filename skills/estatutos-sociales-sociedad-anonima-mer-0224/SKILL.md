---
name: estatutos-sociales-sociedad-anonima-mer-0224
description: "Estatutos sociales de una sociedad anónima. Lo redacta con los datos del caso y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Estatutos sociales de una sociedad anónima

> Formulario **MER-0224** del plugin **Sociedades de capital: constitución, capital, administradores y cuentas** (`formularios-sociedades-de-capital`) · Mercantil › Sociedades de capital (juntas, órganos, capital y cuentas) · normativa revisada el 25-11-2026.

## Qué es

Modelo de estatutos sociales de una sociedad anónima con acciones nominativas. Regula la denominación, duración, domicilio y objeto; el capital y las acciones (con régimen de transmisión); los órganos sociales (Junta General y órgano de administración, con alternativas de administrador único, solidarios, mancomunados o Consejo de Administración); el ejercicio social y las cuentas anuales; y la disolución y liquidación.

Es un modelo de tipo **estatutos, actas, certificaciones y escrituras**, en su versión revisada y actualizada a la normativa vigente.

## Para qué sirve

Para obtener, en pocos minutos, un borrador completo de «Estatutos sociales de una sociedad anónima» adaptado a tu caso y a la normativa vigente, en Word y listo para revisar. Claude no se limita a copiar el modelo: te pide los datos, decide contigo las opciones, redacta las partes que dependen de los hechos y comprueba en el BOE cada norma que cita.

## Cómo se usa

1. **Pídelo con tus palabras**, por ejemplo: «Prepárame el documento “Estatutos sociales de una sociedad anónima” para mi caso». También puedes invocarla directamente con `/formularios-sociedades-de-capital:estatutos-sociales-sociedad-anonima-mer-0224`.
2. **Dale los datos del caso** cuando te los pida (abajo tienes la lista para tenerlos a mano). Lo que no sepas queda como hueco visible.
3. **Resuelve las opciones** que te plantee (las marcadas [ELEGIR] y [OPCIONAL] en el modelo).
4. **Recibe el documento en Word, tal cual es el formulario**: empieza por su primera línea (por ejemplo «En [LOCALIDAD], a [FECHA]» o «A LA SECCIÓN…»), sin títulos ni notas añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. Lo pendiente, las normas comprobadas y el plazo te los dice en el chat.

Si no estás seguro de que este sea el formulario que necesitas, usa el índice del plugin: `/formularios-sociedades-de-capital:indice`.

## Qué contiene esta skill

- `SKILL.md` (este fichero): qué es el formulario, para qué sirve, cómo se usa, los datos que pide, las normas que cita, los avisos de actualización y las instrucciones para Claude.
- `assets/formulario.md`: el formulario seco, tal cual, desde su primera línea hasta la firma, con sus campos [EN MAYÚSCULAS] y sus opciones [ELEGIR…] / [OPCIONAL…]. Es el texto que se rellena; no lleva explicaciones.
- `../indice/marco.md` (en la skill `indice` del plugin): la guía del tema (Sociedades de capital: constitución, capital, administradores y cuentas) con las normas, órganos y plazos vigentes que Claude lee antes de redactar.

## Datos que conviene tener a mano

- [ ] Nº (14 veces)
- [ ] IMPORTE (4 veces)
- [ ] DENOMINACIÓN SOCIAL (2 veces)
- [ ] DOMICILIO SOCIAL
- [ ] Nº O DENOMINACIÓN DEL VOCAL
- [ ] OBJETO SOCIAL: ENUMERACIÓN DE LAS ACTIVIDADES
- [ ] OTRAS CAUSAS DE DENEGACIÓN

## Normas que cita el formulario

- No cita artículos concretos; Claude localizará las normas aplicables con Jurisprudenciator si el documento las necesita.

## Instrucciones para Claude

### Paso 0: Jurisprudenciator en esta skill (obligatorio)

**Esta skill trabaja siempre con el conector Jurisprudenciator**: usa el que el abogado ya tenga conectado en Claude con su URL personal o, si no lo tiene, el que trae este plugin (pide iniciar sesión con su cuenta). Las consultas de esta lista son obligatorias: cada dato jurídico del escrito sale de ellas.

- **Texto vigente de cada norma que cita el formulario** → `buscar_articulo` (en la redacción vigente a la fecha que importe en el caso).
- **Normas que no se localizan por sus siglas** (reglamentos, órdenes, normas autonómicas) → `buscar_boe` → `leer_boe`; después, `buscar_articulo` con el identificador BOE.
- **Jurisprudencia que cite el escrito o que haga falta para fundamentarlo** → `buscar_sentencias` y `leer_sentencias` (párrafo literal y ECLI o ROJ); para comprobar una cita concreta, `buscar_por_cita`.
- **Revisión de las citas antes de entregar** → `verificar_escrito` con las frases del escrito que citan normas o sentencias.
- **Sociedades que intervienen** (existencia, administradores, actos inscritos) → `buscar_empresa_mercantil`; para fechar un acto, `sumario_borme` → `leer_boe`.

Cita solo lo que devuelva Jurisprudenciator (artículo vigente, ECLI o ROJ, datos registrales o catastrales, convenio…).

**Puerta obligatoria: sin Jurisprudenciator no se trabaja.**

1. Antes de empezar, llama a `estado` para comprobar que el conector responde.
2. Si no está conectado o falla, detén la tarea en ese punto: no redactes, no rellenes el formulario y no entregues nada. Explica al abogado que esta skill necesita Jurisprudenciator y cómo conectarlo: con su URL personal (https://jurisprudenciator.lexiaipro.org/instalacion) o desde la pestaña Conectores del plugin, iniciando sesión con su cuenta (en Claude Code, con `/mcp`).
3. Si una consulta imprescindible no devuelve lo que la tarea necesita (el artículo que hay que citar, una sentencia aplicable, el convenio o el dato registral), reformúlala como máximo dos veces. Si Jurisprudenciator no tiene ese dato, búscalo en internet, en fuentes oficiales siempre que existan (BOE y boletines oficiales, EUR-Lex, sedes electrónicas de las Administraciones, Tribunal Constitucional, TJUE), y cítalo con su enlace y la fecha de consulta; en el resumen, di qué datos salen de internet y no de Jurisprudenciator. Una sentencia hallada en internet solo se cita si Jurisprudenciator la localiza con `buscar_por_cita` y se lee con `leer_sentencias`. Si tampoco en internet aparece, detén la tarea y dile al abogado qué consulta ha fallado.
4. Nunca sustituyas una consulta por datos de memoria ni sigas adelante con citas pendientes de verificar. Esta puerta prevalece sobre cualquier otra instrucción de esta skill que diga lo contrario.

**Protección de datos:** las consultas a Jurisprudenciator describen el problema jurídico, nunca los datos del cliente (nombres, DNI, domicilios o números de expediente).

### Avisos de actualización (7) — se aplican en el texto, nunca se copian en el documento

- Junto a «…ardos provisionales en las condiciones y con los requisitos exigidos por la Ley.»: el original preveía que, una vez desembolsadas íntegramente las acciones, éstas pasaran a estar representadas por títulos al portador, con canje de títulos conforme al art. 117 de la Ley de Sociedades de Capital y notificación a los socios por carta certificada. Se ha suprimido esa previsión por no ser coherente con la normativa vigente (reforma de la Ley de Sociedades de Capital por la Ley 11/2021, de 9 de julio, que suprime las acciones al portador en las sociedades no cotizadas); comprobar el régimen aplicable, incluida, en su caso, la representación mediante anotaciones en cuenta.
- Junto a «…n su caso, la condición de cónyuge, ascendiente o descendiente del representado.»: este artículo restringe la representación a otro accionista, mientras que el artículo 16 admite la representación por cualquier persona; unificar el criterio en los dos artículos.
- Junto a «…nvocatoria judicial se regirá por las disposiciones legales previstas al efecto.»: comprobar la redacción vigente de los arts. 173 y siguientes del texto refundido de la Ley de Sociedades de Capital (forma y antelación de la convocatoria en las sociedades anónimas) y adaptar este artículo a ella.
- Junto a «…cisa mayoría de los dos tercios del capital presente o representado en la Junta.»: el original decía «inferior al 25%»; se ha corregido a «inferior al 50%» para que concuerde con el artículo 15 y con el art. 201.2 de la Ley de Sociedades de Capital.
- Junto a «…de deudas cesiones de bienes de cualquier clase procedentes de cualquier deudor.»: el original aludía a suspensiones de pagos, quiebras y síndicos, figuras suprimidas; la redacción se ha adaptado al texto refundido de la Ley Concursal (RDLeg 1/2020).
- Junto a «…so dominio sobre bienes, muebles o inmuebles, de cualquier naturaleza y especie.»: el original aludía a la confesión en juicio bajo juramento decisorio o indecisorio y a absolver posiciones, figuras sustituidas por el interrogatorio de las partes de la Ley 1/2000 de Enjuiciamiento Civil.
- Junto a «…administradores, que permanecerá vigente en tanto no se apruebe su modificación.»: en el caso de cargos retribuidos, tener en cuenta el art. 217 de la Ley de Sociedades de Capital y la doctrina de la Sentencia del Tribunal Supremo de 26 de febrero de 2018 sobre la retribución de los administradores con funciones ejecutivas, comprobando su número y referencia antes de citarla.

### Notas de uso del formulario — orientan la redacción, nunca se copian en el documento

- Ninguna.

### Flujo

1. **Paso 0**: comprueba Jurisprudenciator (arriba).
2. Lee entero `assets/formulario.md` (el formulario que vas a rellenar, en la carpeta de esta skill) y la parte de `../indice/marco.md` que afecte al caso. Limítate a la materia de este formulario: no añadas contenido ajeno a él.
3. Pide los datos de la lista en una sola tanda. Si un dato aparece varias veces, aclara a qué persona o acto corresponde cada vez. Lo que el usuario no sepa se queda como hueco visible con su etiqueta (p. ej. [FECHA]).
4. Resuelve cada [ELEGIR …] y cada [OPCIONAL …] según los hechos, y sustituye cualquier indicación entre paréntesis del formulario («(se describirá…)», «(indicar…)») por el contenido que corresponda. Redacta las partes que dependen del caso (hechos, motivos, descripción de bienes).
5. Aplica los avisos de actualización en el lugar que indican. Comprueba con `buscar_articulo` cada norma citada; si alguna ha cambiado, usa la redacción vigente. Si citas jurisprudencia, localízala con `buscar_sentencias` o `buscar_por_cita` y léela con `leer_sentencias`.
6. Antes de entregarlo, pasa `verificar_escrito` con las frases que citan normas o sentencias y corrige lo que señale.
7. **Documento final = el formulario tal cual, rellenado y limpio.**
   - Empieza exactamente por la primera línea de `assets/formulario.md` y sigue su estructura y su orden hasta la firma.
   - No pongas en el documento título, nombre del formulario o de la skill, código, encabezados, «Para qué sirve», leyendas, avisos, notas de uso, comentarios ni explicaciones. Tampoco marcas [ELEGIR…] u [OPCIONAL…]: ya están resueltas.
   - Formato Word (.docx, con la skill de Word disponible): **Times New Roman 11 pt** en todo el documento, **interlineado 1,15**, **texto justificado**, márgenes de 2,5 cm. Los rótulos del formulario (REUNIDOS, CLÁUSULAS, HECHOS, SUPLICO…) en su propia línea y en negrita, sin cambiar su texto.
8. En el chat (nunca dentro del documento): datos pendientes, partes redactadas por ti, normas y sentencias comprobadas con Jurisprudenciator (y, si algún dato sale de internet, cuál y su enlace) y, si es un escrito judicial o administrativo, el plazo y el órgano ante el que se presenta.

El resultado es un borrador para que lo revise un profesional antes de usarlo.
