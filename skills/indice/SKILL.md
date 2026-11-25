---
name: indice
description: "Índice de los 139 formularios de Sociedades de capital: constitución, capital, administradores y cuentas. Úsala cuando el usuario pida un documento de esta materia y no esté claro qué formulario usar: propone el adecuado y lo abre. Requiere Jurisprudenciator."
---

# Sociedades de capital: constitución, capital, administradores y cuentas: índice de formularios

> Plugin `formularios-sociedades-de-capital` · 139 formularios · normativa revisada el 25-11-2026.

## Qué es

Para el día a día societario de las SL y SA fuera de las juntas: constitución y estatutos, nombramiento, cese y renuncia de administradores, poderes, aumentos y reducciones de capital, transmisión de participaciones y acciones, cuentas anuales y auditor, disolución y liquidación, y los escritos al Registro Mercantil. Las juntas y actas están en `formularios-juntas-y-actas-de-sociedades`.

## Cómo se usa

Cuéntale a Claude qué documento necesitas y para qué caso. Esta skill busca en la lista de abajo el formulario que mejor encaja (por tipo de documento y por su nombre) y lo abre. Si hay dos o tres que encajan, te los propone para que elijas.

Ejemplos de petición:

- «Estatutos sociales de una sociedad limitada»
- «Renuncia de un administrador y su comunicación al Registro Mercantil»
- «Escritura de aumento de capital con nuevas aportaciones dinerarias»

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

### Cómo elegir

Busca por tipo de documento y por nombre. Cada formulario es una skill de este plugin (`/formularios-sociedades-de-capital:<skill>`). Si dudas entre dos, elige el que mejor encaje con los hechos y dilo; si la petición es ambigua, propón al usuario los dos o tres formularios que mejor encajan y pregúntale cuál quiere. Las reglas del tema están en `marco.md`.

### Cómo usar el formulario elegido

Invoca su skill. Si esa skill no aparece en tu lista de skills disponibles (puede pasar cuando hay muchas skills instaladas), lee directamente su fichero `SKILL.md`: está en la carpeta hermana de esta (`../<skill>/SKILL.md`). Síguelo igual que si la hubieras invocado: el formulario que se rellena está en `../<skill>/assets/formulario.md` y la guía del tema es el `marco.md` de esta carpeta.

### Demandas, peticiones y solicitudes iniciales (1)

| Código | Formulario | Skill |
|---|---|---|
| MER-0146 | Solicitud de nombramiento de auditor al Registro Mercantil para verificar las cuentas anuales | `solicitud-nombramiento-auditor-registro-mercantil-mer-0146` |

### Contestaciones, oposiciones y alegaciones (3)

| Código | Formulario | Skill |
|---|---|---|
| MER-0090 | Escrito de oposición del acreedor social a la reducción de capital de una SA | `escrito-oposicion-acreedor-social-reduccion-capital-sa-mer-0090` |
| MER-0107 | Escrito de oposición a la rectificación del libro registro de acciones nominativas | `escrito-oposicion-rectificacion-libro-registro-mer-0107` |
| MER-0171 | Escrito de oposición al nombramiento de auditor por el Registro Mercantil | `escrito-oposicion-nombramiento-auditor-registro-mer-0171` |

### Contratos, pactos y cláusulas (10)

| Código | Formulario | Skill |
|---|---|---|
| MER-0009 | Pacto de socios (modelo) | `pacto-socios-modelo-mer-0009` |
| MER-0013 | Contrato de compraventa de acciones o participaciones sociales (SPA) | `contrato-compraventa-acciones-participaciones-sociales-mer-0013` |
| MER-0017 | Pacto parasocial para la constitución de una sociedad | `pacto-parasocial-constitucion-sociedad-mer-0017` |
| MER-0042 | Contrato de inversión entre la sociedad y business angels | `contrato-inversion-entre-sociedad-business-angels-mer-0042` |
| MER-0043 | Carta de intenciones de inversión con business angels | `carta-intenciones-inversion-business-angels-mer-0043` |
| MER-0044 | Acuerdo de gestión entre red de business angels, inversor y emprendedor | `acuerdo-gestion-entre-red-business-angels-inversor-mer-0044` |
| MER-0046 | Compraventa de acciones de una sociedad (contrato) | `compraventa-acciones-sociedad-contrato-mer-0046` |
| MER-0050 | Contrato con el consejero delegado de una SL (art. 249.3 LSC) | `contrato-consejero-delegado-sl-art-249-3-lsc-mer-0050` |
| MER-0145 | Compraventa de acciones nominativas entre personas físicas (contrato) | `compraventa-acciones-nominativas-entre-personas-mer-0145` |
| MER-0199 | Contrato de venta de participaciones de una sociedad limitada | `contrato-venta-participaciones-sociedad-limitada-mer-0199` |

### Estatutos, actas, certificaciones y escrituras (58)

| Código | Formulario | Skill |
|---|---|---|
| MER-0004 | Estatutos sociales de una SPAC | `estatutos-sociales-spac-mer-0004` |
| MER-0016 | Estatutos sociales de una sociedad limitada unipersonal | `estatutos-sociales-sociedad-limitada-unipersonal-mer-0016` |
| MER-0029 | Escritura pública de modificación de estatutos de una SL | `escritura-publica-modificacion-estatutos-sl-mer-0029` |
| MER-0032 | Escritura pública de reducción del capital de una SA | `escritura-publica-reduccion-capital-sa-mer-0032` |
| MER-0035 | Escritura pública de reducción del capital de una SL | `escritura-publica-reduccion-capital-sl-mer-0035` |
| MER-0039 | Escritura pública de aumento de capital de una SL | `escritura-publica-aumento-capital-sl-mer-0039` |
| MER-0041 | Escritura pública de aumento de capital de una SA | `escritura-publica-aumento-capital-sa-mer-0041` |
| MER-0051 | Poder notarial para constituir una sociedad limitada | `poder-notarial-constituir-sociedad-limitada-mer-0051` |
| MER-0059 | Escritura pública de renuncia del administrador de una SL o SA | `escritura-publica-renuncia-administrador-sl-sa-mer-0059` |
| MER-0068 | Anuncio de la reducción de capital de una SL para que los acreedores ejerzan su derecho de oposición | `anuncio-reduccion-capital-sl-acreedores-ejerzan-mer-0068` |
| MER-0069 | Anuncio en el BORME de un acuerdo de SL que da derecho de separación | `anuncio-borme-acuerdo-sl-da-derecho-separacion-mer-0069` |
| MER-0088 | Anuncio en prensa del acuerdo de reducción del capital de una SA | `anuncio-prensa-acuerdo-reduccion-capital-sa-mer-0088` |
| MER-0095 | Anuncio de oferta de nuevas participaciones de SL para el ejercicio del derecho de preferencia | `anuncio-oferta-nuevas-participaciones-sl-ejercicio-mer-0095` |
| MER-0108 | Estatutos sociales simplificados de una sociedad anónima | `estatutos-sociales-simplificados-sociedad-anonima-mer-0108` |
| MER-0119 | Informe de los administradores de una SA sobre la propuesta de modificación de estatutos | `informe-administradores-sa-sobre-propuesta-mer-0119` |
| MER-0121 | Anuncio en el BORME de la reclamación de desembolsos pendientes a los accionistas | `anuncio-borme-reclamacion-desembolsos-pendientes-mer-0121` |
| MER-0154 | Informe especial sobre créditos a compensar en un aumento de capital de SA | `informe-especial-sobre-creditos-compensar-aumento-mer-0154` |
| MER-0155 | Anuncio del acuerdo de reducción del capital de una SA | `anuncio-acuerdo-reduccion-capital-sa-mer-0155` |
| MER-0158 | Anuncio de reducción y aumento simultáneo de capital de SA con derecho de suscripción | `anuncio-reduccion-aumento-simultaneo-capital-sa-mer-0158` |
| MER-0160 | Informe de los administradores de SA sobre aportaciones no dinerarias en un aumento de capital | `informe-administradores-sa-sobre-aportaciones-no-mer-0160` |
| MER-0161 | Informe especial sobre la exclusión del derecho de suscripción preferente en aumento de capital | `informe-especial-sobre-exclusion-derecho-suscripcion-mer-0161` |
| MER-0162 | Anuncio de oferta de retirada de acciones de asignación gratuita en la ampliación de capital de SA | `anuncio-oferta-retirada-acciones-asignacion-gratuita-mer-0162` |
| MER-0167 | Informe especial del auditor sobre las reservas usadas en la ampliación de capital de una SA | `informe-especial-auditor-sobre-reservas-usadas-mer-0167` |
| MER-0183 | Escritura de constitución de una sociedad anónima deportiva | `escritura-constitucion-sociedad-anonima-deportiva-mer-0183` |
| MER-0184 | Estatutos sociales de una sociedad anónima deportiva | `estatutos-sociales-sociedad-anonima-deportiva-mer-0184` |
| MER-0185 | Escritura pública de reactivación de una sociedad de capital disuelta | `escritura-publica-reactivacion-sociedad-capital-mer-0185` |
| MER-0186 | Escritura pública de creación o extinción de prestaciones accesorias en una SL | `escritura-publica-creacion-extincion-prestaciones-mer-0186` |
| MER-0192 | Estatutos sociales de una sociedad anónima unipersonal | `estatutos-sociales-sociedad-anonima-unipersonal-mer-0192` |
| MER-0193 | Escritura pública del acuerdo de disolución de una sociedad anónima | `escritura-publica-acuerdo-disolucion-sociedad-anonima-mer-0193` |
| MER-0195 | Escritura pública de compraventa de acciones al portador de una SA | `escritura-publica-compraventa-acciones-portador-sa-mer-0195` |
| MER-0196 | Escritura pública de compraventa de acciones nominativas de una SA | `escritura-publica-compraventa-acciones-nominativas-sa-mer-0196` |
| MER-0198 | Escritura notarial de otorgamiento de poder | `escritura-notarial-otorgamiento-poder-mer-0198` |
| MER-0208 | Escritura pública de liquidación de una sociedad anónima | `escritura-publica-liquidacion-sociedad-anonima-mer-0208` |
| MER-0209 | Escritura pública de cese y nombramiento de administradores de una sociedad anónima | `escritura-publica-cese-nombramiento-administradores-mer-0209` |
| MER-0211 | Escritura pública de reducción y ampliación simultánea de capital de una SA (operación acordeón) | `escritura-publica-reduccion-ampliacion-simultanea-mer-0211` |
| MER-0215 | Escritura pública de creación o extinción anticipada de prestaciones accesorias en una SA | `escritura-publica-creacion-extincion-anticipada-mer-0215` |
| MER-0220 | Escritura pública de donación de acciones nominativas de una SA a un descendiente | `escritura-publica-donacion-acciones-nominativas-sa-mer-0220` |
| MER-0223 | Escritura de constitución de una SA con aportaciones dinerarias y no dinerarias | `escritura-constitucion-sa-aportaciones-dinerarias-no-mer-0223` |
| MER-0224 | Estatutos sociales de una sociedad anónima | `estatutos-sociales-sociedad-anonima-mer-0224` |
| MER-0229 | Escritura pública de pérdida de la unipersonalidad de una SL o SA por transmisión de su capital | `escritura-publica-perdida-unipersonalidad-sl-sa-mer-0229` |
| MER-0230 | Escritura de constitución de una SL con aportaciones dinerarias, no dinerarias o mixtas | `escritura-constitucion-sl-aportaciones-dinerarias-no-mer-0230` |
| MER-0231 | Escritura de unipersonalidad sobrevenida de una SL por adquirir un socio todas las participaciones | `escritura-unipersonalidad-sobrevenida-sl-adquirir-mer-0231` |
| MER-0232 | Estatutos sociales de una sociedad limitada | `estatutos-sociales-sociedad-limitada-mer-0232` |
| MER-0236 | Escritura de apoderamiento mercantil otorgada por una sociedad anónima a favor de un tercero | `escritura-apoderamiento-mercantil-otorgada-sociedad-mer-0236` |
| MER-0237 | Escritura pública de donación de participaciones de una SL a un descendiente | `escritura-publica-donacion-participaciones-sl-mer-0237` |
| MER-0238 | Escritura pública de cese y nombramiento de administradores de una sociedad limitada | `escritura-publica-cese-nombramiento-administradores-mer-0238` |
| MER-0240 | Escritura pública de reducción y ampliación simultánea de capital de una SL (operación acordeón) | `escritura-publica-reduccion-ampliacion-simultanea-mer-0240` |
| MER-0247 | Escritura pública de liquidación de una sociedad limitada | `escritura-publica-liquidacion-sociedad-limitada-mer-0247` |
| MER-0250 | Escritura pública del acuerdo de disolución de una sociedad limitada | `escritura-publica-acuerdo-disolucion-sociedad-limitada-mer-0250` |
| MER-0251 | Escritura pública de disolución y liquidación simultáneas de una sociedad limitada | `escritura-publica-disolucion-liquidacion-simultaneas-mer-0251` |
| MER-0256 | Escritura pública de cambio de socio único en una sociedad limitada unipersonal | `escritura-publica-cambio-socio-unico-sociedad-limitada-mer-0256` |
| MER-0259 | Escritura de constitución de una sociedad unipersonal, limitada o anónima | `escritura-constitucion-sociedad-unipersonal-limitada-mer-0259` |
| MER-0260 | Escritura pública de cambio de socio único en una sociedad anónima unipersonal | `escritura-publica-cambio-socio-unico-sociedad-anonima-mer-0260` |
| MER-0262 | Escritura de unipersonalidad sobrevenida de una SA por pasar todas las acciones a un solo socio | `escritura-unipersonalidad-sobrevenida-sa-pasar-todas-mer-0262` |
| MER-0300 | Escritura pública de disolución y liquidación simultáneas de una sociedad anónima | `escritura-publica-disolucion-liquidacion-simultaneas-mer-0300` |
| MER-0304 | Escritura de constitución de sociedad con aportación de un bien ganancial | `escritura-constitucion-sociedad-aportacion-bien-mer-0304` |
| MER-0305 | Escritura de ampliación de capital con aportación de un bien ganancial | `escritura-ampliacion-capital-aportacion-bien-ganancial-mer-0305` |
| MER-0308 | Escritura de revocación de poder mercantil | `escritura-revocacion-poder-mercantil-mer-0308` |

### Comunicaciones, requerimientos y cartas (39)

| Código | Formulario | Skill |
|---|---|---|
| MER-0020 | Solicitud al Registro Mercantil de experto independiente para valorar aportaciones no dinerarias | `solicitud-registro-mercantil-experto-independiente-mer-0020` |
| MER-0049 | Solicitud de legalización telemática de libros contables de SL o SA | `solicitud-legalizacion-telematica-libros-contables-sl-mer-0049` |
| MER-0053 | Requerimiento de desembolso de aportaciones pendientes a un socio de una SA | `requerimiento-desembolso-aportaciones-pendientes-socio-mer-0053` |
| MER-0058 | Comunicación a los socios de la restitución de aportaciones por aumento de capital no suscrito | `comunicacion-socios-restitucion-aportaciones-aumento-mer-0058` |
| MER-0063 | Comunicación individual a los socios de la SL del acuerdo que genera derecho de separación | `comunicacion-individual-socios-sl-acuerdo-genera-mer-0063` |
| MER-0067 | Notificación al socio del acuerdo de su exclusión de una SL | `notificacion-socio-acuerdo-exclusion-sl-mer-0067` |
| MER-0082 | Notificación a la participada de haber superado el diez por ciento de su capital | `notificacion-participada-haber-superado-diez-ciento-mer-0082` |
| MER-0093 | Solicitud del accionista de examinar el libro registro de acciones nominativas | `solicitud-accionista-examinar-libro-registro-acciones-mer-0093` |
| MER-0094 | Solicitud de rectificación de error material en una inscripción del Registro Mercantil | `solicitud-rectificacion-error-material-inscripcion-mer-0094` |
| MER-0096 | Solicitud al registrador de experto que valore las participaciones del socio separado o excluido | `solicitud-registrador-experto-valore-participaciones-mer-0096` |
| MER-0097 | Notificación a la SL del representante común de los cotitulares de participaciones | `notificacion-sl-representante-comun-cotitulares-mer-0097` |
| MER-0098 | Notificación a la SL de la adquisición de participaciones sociales | `notificacion-sl-adquisicion-participaciones-sociales-mer-0098` |
| MER-0099 | Comunicación a la SL de la adquisición hereditaria de participaciones sociales | `comunicacion-sl-adquisicion-hereditaria-mer-0099` |
| MER-0100 | Solicitud de inscripción de una sucursal en el Registro Mercantil del domicilio social | `solicitud-inscripcion-sucursal-registro-mercantil-mer-0100` |
| MER-0101 | Solicitud de restitución de aportaciones por aumento de capital de SL no presentado a inscripción | `solicitud-restitucion-aportaciones-aumento-capital-sl-mer-0101` |
| MER-0102 | Solicitud de inscripción parcial en el Registro Mercantil | `solicitud-inscripcion-parcial-registro-mercantil-mer-0102` |
| MER-0103 | Solicitud de rectificación de errores en datos publicados en el BORME | `solicitud-rectificacion-errores-datos-publicados-borme-mer-0103` |
| MER-0105 | Notificación a interesados de la intención de rectificar el libro registro de acciones nominativas | `notificacion-interesados-intencion-rectificar-libro-mer-0105` |
| MER-0106 | Notificación notarial a la participada de haber superado el diez por ciento de su capital | `notificacion-notarial-participada-haber-superado-diez-mer-0106` |
| MER-0126 | Notificación al Registro del cambio de titular de la facultad certificante | `notificacion-registro-cambio-titular-facultad-mer-0126` |
| MER-0132 | Carta de encargo de auditoría de cuentas para ejercicios sucesivos | `carta-encargo-auditoria-cuentas-ejercicios-sucesivos-mer-0132` |
| MER-0140 | Comunicación a los socios de la modificación del régimen de transmisión de participaciones | `comunicacion-socios-modificacion-regimen-transmision-mer-0140` |
| MER-0143 | Comunicación escrita a los socios de una SL para ejercer el derecho de preferencia | `comunicacion-escrita-socios-sl-ejercer-derecho-mer-0143` |
| MER-0144 | Notificación a los acreedores del acuerdo de reducción de capital de una SL para su oposición | `notificacion-acreedores-acuerdo-reduccion-capital-sl-mer-0144` |
| MER-0147 | Solicitud de experto independiente para informar sobre adquisiciones onerosas de una SA | `solicitud-experto-independiente-informar-sobre-mer-0147` |
| MER-0148 | Solicitud de experto independiente sobre aportaciones no dinerarias en aumentos de capital de SA | `solicitud-experto-independiente-sobre-aportaciones-no-mer-0148` |
| MER-0150 | Solicitud de consentimiento a los accionistas para aumentar capital elevando el valor nominal | `solicitud-consentimiento-accionistas-aumentar-capital-mer-0150` |
| MER-0152 | Solicitud de auditor al Registro Mercantil que certifique los créditos a compensar en una SA | `solicitud-auditor-registro-mercantil-certifique-mer-0152` |
| MER-0153 | Solicitud de auditor al Registro Mercantil sobre las reservas con cargo a las que se aumenta capital | `solicitud-auditor-registro-mercantil-sobre-reservas-mer-0153` |
| MER-0159 | Comunicación de que el aumento de capital de SA queda sin efecto por suscripción incompleta | `comunicacion-aumento-capital-sa-queda-sin-efecto-mer-0159` |
| MER-0169 | Carta de separación del socio por cambio de objeto, duración, régimen de transmisión o domicilio | `carta-separacion-socio-cambio-objeto-duracion-regimen-mer-0169` |
| MER-0170 | Solicitud al Registro Mercantil de auditor que determine el valor de acciones o participaciones | `solicitud-registro-mercantil-auditor-determine-valor-mer-0170` |
| MER-0173 | Carta de comunicación de actividades con conflicto de intereses por un administrador | `carta-comunicacion-actividades-conflicto-intereses-mer-0173` |
| MER-0175 | Carta de manifestaciones de la administración al auditor | `carta-manifestaciones-administracion-auditor-mer-0175` |
| MER-0205 | Requerimiento para elevar a escritura pública la venta privada de participaciones de una SL | `requerimiento-elevar-escritura-publica-venta-privada-mer-0205` |
| MER-0257 | Comunicación del administrador de una SL a un socio de su propósito de rectificar el libro de socios | `comunicacion-administrador-sl-socio-proposito-mer-0257` |
| MER-0264 | Solicitud del accionista de autorización del órgano de administración para vender acciones | `solicitud-accionista-autorizacion-organo-mer-0264` |
| MER-0268 | Comunicación del administrador de una SL a los socios del embargo de participaciones sociales | `comunicacion-administrador-sl-socios-embargo-mer-0268` |
| MER-0272 | Solicitud de un socio de SL de consentimiento para transmitir sus participaciones sociales | `solicitud-socio-sl-consentimiento-transmitir-mer-0272` |

### Escritos de trámite y otros (28)

| Código | Formulario | Skill |
|---|---|---|
| MER-0001 | Depósito de cuentas anuales 2025 en modelo oficial abreviado | `deposito-cuentas-anuales-2025-modelo-oficial-abreviado-mer-0001` |
| MER-0002 | Depósito de cuentas anuales 2025 en modelo oficial para PYMES | `deposito-cuentas-anuales-2025-modelo-oficial-pymes-mer-0002` |
| MER-0006 | Depósito de cuentas anuales 2025 en modelo oficial normal | `deposito-cuentas-anuales-2025-modelo-oficial-normal-mer-0006` |
| MER-0007 | Depósito de cuentas anuales consolidadas 2025 en modelo oficial | `deposito-cuentas-anuales-consolidadas-2025-modelo-mer-0007` |
| MER-0022 | Escrito de aceptación del cargo de administrador de una SL o SA | `escrito-aceptacion-cargo-administrador-sl-sa-mer-0022` |
| MER-0047 | Instancia de solicitud de legalización de libros en el Registro Mercantil | `instancia-solicitud-legalizacion-libros-registro-mer-0047` |
| MER-0048 | Relación de libros con su firma digital para legalizar en el Registro Mercantil | `relacion-libros-firma-digital-legalizar-registro-mer-0048` |
| MER-0060 | Separación del socio por desacuerdo con un acuerdo social o falta de reparto de dividendos | `separacion-socio-desacuerdo-acuerdo-social-falta-mer-0060` |
| MER-0061 | Documento de acuerdo sobre el valor de las participaciones del socio que se separa de una SL | `documento-acuerdo-sobre-valor-participaciones-socio-mer-0061` |
| MER-0089 | Título de acción de una sociedad anónima | `titulo-accion-sociedad-anonima-mer-0089` |
| MER-0110 | Escrito de renuncia al cargo de administrador de una SL o SA | `escrito-renuncia-cargo-administrador-sl-sa-mer-0110` |
| MER-0116 | Escrito del socio que reclama el pago de dividendos no prescritos | `escrito-socio-reclama-pago-dividendos-no-prescritos-mer-0116` |
| MER-0118 | Hoja del libro registro de acciones nominativas | `hoja-libro-registro-acciones-nominativas-mer-0118` |
| MER-0131 | Sociedad mercantil irregular (contrato) | `sociedad-mercantil-irregular-contrato-mer-0131` |
| MER-0137 | Publicación de la propuesta de compra de acciones propias para reducir capital de una SA | `publicacion-propuesta-compra-acciones-propias-reducir-mer-0137` |
| MER-0156 | Escrito del secretario cesado que se da por enterado del nombramiento de su sucesor en el consejo | `escrito-secretario-cesado-da-enterado-nombramiento-mer-0156` |
| MER-0157 | Propuesta de acuerdo de reducción y aumento simultáneo de capital de una SA | `propuesta-acuerdo-reduccion-aumento-simultaneo-capital-mer-0157` |
| MER-0163 | Oferta de suscripción preferente de nuevas acciones en el aumento de capital de una SA | `oferta-suscripcion-preferente-nuevas-acciones-aumento-mer-0163` |
| MER-0202 | Artículo estatutario de sometimiento a arbitraje ante una cámara de comercio | `articulo-estatutario-sometimiento-arbitraje-ante-mer-0202` |
| MER-0222 | Resguardo provisional de acciones de una sociedad anónima | `resguardo-provisional-acciones-sociedad-anonima-mer-0222` |
| MER-0226 | Título al portador representativo de una o varias acciones de una SA | `titulo-portador-representativo-varias-acciones-sa-mer-0226` |
| MER-0227 | Programa de fundación de una SA por suscripción pública de acciones (fundación sucesiva) | `programa-fundacion-sa-suscripcion-publica-acciones-mer-0227` |
| MER-0228 | Escrito de aceptación del cargo de administrador de una SA con firma legitimada ante notario | `escrito-aceptacion-cargo-administrador-sa-firma-mer-0228` |
| MER-0255 | Escrito de un socio de SL oponiéndose a la rectificación del libro registro de socios | `escrito-socio-sl-oponiendose-rectificacion-libro-mer-0255` |
| MER-0265 | Endoso de una acción nominativa de una sociedad anónima | `endoso-accion-nominativa-sociedad-anonima-mer-0265` |
| MER-0282 | Boletín de suscripción de acciones en la fundación sucesiva de una sociedad anónima | `boletin-suscripcion-acciones-fundacion-sucesiva-mer-0282` |
| MER-0283 | Título nominativo representativo de una o varias acciones de una sociedad anónima | `titulo-nominativo-representativo-varias-acciones-mer-0283` |
| MER-0307 | Instancia al Registro Mercantil para legalizar los libros del empresario | `instancia-registro-mercantil-legalizar-libros-mer-0307` |
