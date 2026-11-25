---
name: escritura-publica-reactivacion-sociedad-capital-mer-0185
description: "Escritura pública de reactivación de una sociedad de capital disuelta. Lo redacta con los datos del caso y comprueba las normas en el BOE. Requiere Jurisprudenciator."
---

# Escritura pública de reactivación de una sociedad de capital disuelta

> Formulario **MER-0185** del plugin **Sociedades de capital: constitución, capital, administradores y cuentas** (`formularios-sociedades-de-capital`) · Mercantil › Sociedades de capital (juntas, órganos, capital y cuentas) · normativa revisada el 25-11-2026.

## Qué es

Modelo de escritura pública por la que se eleva a público el acuerdo de la Junta General Extraordinaria de una sociedad limitada o anónima de reactivar la sociedad disuelta, una vez desaparecida la causa de disolución, junto con los demás acuerdos precisos (derecho de separación y, en su caso, reducción de capital).

Es un modelo de tipo **estatutos, actas, certificaciones y escrituras**, en su versión revisada y actualizada a la normativa vigente.

## Para qué sirve

Para obtener, en pocos minutos, un borrador completo de «Escritura pública de reactivación de una sociedad de capital disuelta» adaptado a tu caso y a la normativa vigente, en Word y listo para revisar. Claude no se limita a copiar el modelo: te pide los datos, decide contigo las opciones, redacta las partes que dependen de los hechos y comprueba en el BOE cada norma que cita.

## Cómo se usa

1. **Pídelo con tus palabras**, por ejemplo: «Prepárame el documento “Escritura pública de reactivación de una sociedad de capital disuelta” para mi caso». También puedes invocarla directamente con `/formularios-sociedades-de-capital:escritura-publica-reactivacion-sociedad-capital-mer-0185`.
2. **Dale los datos del caso** cuando te los pida (abajo tienes la lista para tenerlos a mano). Lo que no sepas queda como hueco visible.
3. **Resuelve las opciones** que te plantee (las marcadas [ELEGIR] y [OPCIONAL] en el modelo).
4. **Recibe el documento en Word, tal cual es el formulario**: empieza por su primera línea (por ejemplo «En [LOCALIDAD], a [FECHA]» o «A LA SECCIÓN…»), sin títulos ni notas añadidas, en Times New Roman 11, interlineado 1,15 y texto justificado. Lo pendiente, las normas comprobadas y el plazo te los dice en el chat.

Si no estás seguro de que este sea el formulario que necesitas, usa el índice del plugin: `/formularios-sociedades-de-capital:indice`.

## Qué contiene esta skill

- `SKILL.md` (este fichero): qué es el formulario, para qué sirve, cómo se usa, los datos que pide, las normas que cita, los avisos de actualización y las instrucciones para Claude.
- `assets/formulario.md`: el formulario seco, tal cual, desde su primera línea hasta la firma, con sus campos [EN MAYÚSCULAS] y sus opciones [ELEGIR…] / [OPCIONAL…]. Es el texto que se rellena; no lleva explicaciones.
- `../indice/marco.md` (en la skill `indice` del plugin): la guía del tema (Sociedades de capital: constitución, capital, administradores y cuentas) con las normas, órganos y plazos vigentes que Claude lee antes de redactar.

## Datos que conviene tener a mano

- [ ] IMPORTE (8 veces)
- [ ] FECHA (5 veces)
- [ ] DENOMINACIÓN SOCIAL (4 veces)
- [ ] NOMBRE Y APELLIDOS (4 veces)
- [ ] Nº (4 veces)
- [ ] LOCALIDAD (3 veces)
- [ ] NOMBRE DEL NOTARIO (3 veces)
- [ ] PROVINCIA (3 veces)
- [ ] AÑO (2 veces)
- [ ] DÍA (2 veces)
- [ ] FIRMA (2 veces)
- [ ] MES (2 veces)
- [ ] Nº DE PROTOCOLO (2 veces)
- [ ] COLEGIO NOTARIAL
- [ ] DATOS REGISTRALES: TOMO, FOLIO, HOJA NÚMERO E INSCRIPCIÓN
- [ ] DNI/NIE
- [ ] DOMICILIO
- [ ] DOMICILIO SOCIAL
- [ ] EXPLICACIÓN DE LA CAUSA DE DISOLUCIÓN Y DE LA DESAPARICIÓN DE LA MISMA
- [ ] NACIONALIDAD
- [ ] NIF
- [ ] Nº DE INSCRIPCIÓN
- [ ] NÚMERO
- [ ] OTROS SOCIOS QUE HAYAN EJERCITADO EL DERECHO DE SEPARACIÓN
- [ ] PLAZO

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

### Avisos de actualización (0) — se aplican en el texto, nunca se copian en el documento

- Ninguno.

### Notas de uso del formulario — orientan la redacción, nunca se copian en el documento

NOTAS DE AYUDA

La reactivación de la sociedad disuelta está regulada en el artículo 370 del texto refundido de la Ley de Sociedades de Capital. Según este precepto, la junta general podrá acordar el retorno de la sociedad disuelta a la vida activa siempre que haya desaparecido la causa de disolución, el patrimonio contable no sea inferior al capital social y no haya comenzado el pago de la cuota de liquidación a los socios. No podrá acordarse la reactivación en los casos de disolución de pleno derecho. El acuerdo de reactivación se adoptará con los requisitos establecidos para la modificación de los estatutos. El socio que no vote a favor de la reactivación tiene derecho a separarse de la sociedad. Los acreedores sociales podrán oponerse al acuerdo de reactivación, en las mismas condiciones y con los mismos efectos previstos en la ley para el caso de reducción del capital.

Según el artículo 107 del Reglamento del Registro Mercantil, la elevación a instrumento público de los acuerdos de la junta o asamblea general o especial y de los acuerdos de los órganos colegiados de administración podrá realizarse tomando como base el acta o libro de actas, testimonio notarial de los mismos o certificación de los acuerdos. También podrá realizarse tomando como base la copia autorizada del acta, cuando los acuerdos constaren en acta notarial. En la escritura de elevación a público del acuerdo social deberán consignarse todas las circunstancias del acta que sean necesarias para calificar la validez de aquel. En su caso, el Notario testimoniará en la escritura el anuncio de convocatoria publicado o protocolizará testimonio notarial del mismo.

De conformidad con el artículo 108 del Reglamento del Registro Mercantil, la elevación a instrumento público de los acuerdos sociales corresponde a la persona que tenga facultad para certificarlos. Las decisiones del socio único, consignadas en acta bajo su firma o la de su representante, podrán ser ejecutadas y formalizadas por el propio socio o por los administradores de la sociedad. También podrá realizarse por cualquiera de los miembros del órgano de administración con nombramiento vigente e inscrito en el Registro Mercantil, cuando hubieren sido expresamente facultados para ello en la escritura social o en la reunión en que se hayan adoptado los acuerdos. La elevación a instrumento público por cualquier otra persona requerirá el otorgamiento de la oportuna escritura de poder, que podrá ser general para todo tipo de acuerdos, en cuyo caso deberá inscribirse en el Registro Mercantil. Este procedimiento no será aplicable para elevar a públicos los acuerdos sociales cuando se tome como base para ello el acta o testimonio notarial de la misma.


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
