La Dirección General de los Registros y del Notariado (DGRN), en la Instrucción de 12 de febrero de 2015, proporciona criterios procedimentales únicos y uniformes para la legalización de los libros de todas clases que obligatoriamente deben llevar los empresarios, así como, un nuevo formato que recoge los archivos que conforman la legalización de los libros en un archivo comprimido, aportando una mayor simplicidad, ahorro de tamaño y disminución del tiempo de proceso en la tramitación telemática.

En el soporte electrónico de que se trate deberán constar obligatoriamente los ficheros que a continuación se detallan.

A) Libros legalizados:

Libros legalizados que se corresponderán con la siguiente tabla:

Nombre del libro
Diario
Inventario y Cuentas Anuales
Balances de comprobación (sumas y saldos)
Inventario
Balances
Memoria
Mayor
Libro de Pérdidas y Ganancias
IVA
Facturas Emitidas
Facturas Recibidas
Detalle del Diario
Registro de Acciones Nominativas
Registro de Socios
Libro de Actas
Libro de Detalle de Actas
Libro de Actas del Consejo
Libro de Detalle de Actas del Consejo
Libro-Registro de Contratos del Socio Único con la Sociedad Unipersonal
Otros

B) Archivo NOMBRES.TXT:

Fichero ASCII que contiene los nombres de los ficheros correspondientes a cada uno de los libros cuya legalización se pretenda. Los nombres de dichos ficheros y sus extensiones deberán ajustarse a los requisitos que se detallan a continuación. Cada línea de texto, separada con Intro, indicará el nombre de cada uno de los libros legalizados.

Solamente se permitirá la presentación de un máximo de nueve libros correlativos por cada tipo (por ejemplo, del libro de DIARIO podrá presentar hasta nueve libros). El nombre de dichos ficheros deberá ser el correspondiente al tipo de libro, DIARIO en este caso, concatenado con _NNN (NNN el n.º correspondiente a cada uno de los libros presentados de dicho tipo). En caso de presentarse tipos de libros que no correspondan a ningún nombre de la tabla anterior, sus ficheros correspondientes se nombrarán todos como OTROS_ al que se le concatenará un número correlativo X (del 1 al 9) que los distinga.

Los nombres de los ficheros se ajustarán a la siguiente tabla:

Nombre del libro	Nombre del fichero en el archivo NOMBRE.TXT
Diario	DIARIO_NNN.<extension>
Inventario y cuentas anuales	INV_CUEN_NNN.<extension>
Balances de comprobación (sumas y saldos)	BAL_SUMS_NNN.<extension>
Inventario	INVENTAR_NNN.<extension>
Balances	BALANCES_NNN.<extension>
Memoria	MEMORIA_NNN.<extension>
Mayor	MAYOR_NNN.<extension>
Libro de Pérdidas y Ganancias	PER_GAN_NNN.<extension>
IVA	IVA_NNN.<extension>
Facturas Emitidas	FAC_EMIT_NNN.<extension>
Facturas Recibidas	FAC_RECI_NNN.<extension>
Detalle del Diario	DET_DIA_NNN.<extension>
Registro de Acciones Nominativas	ACCIONES_NNN.<extension>
Registro de Socios	SOCIOS_NNN.<extension>
Libro de Actas	ACTASCON_NNN.<extension>
Libro de Detalle de Actas	ACTASDET_NNN.<extension>
Libro de Actas del Consejo	ACTALCON_NNN.<extension>
Libro de Detalle de Actas del Consejo	ACTACODE_NNN.<extension>
Libro-registro de Contratos del Socio Único con la Sociedad Unipersonal	SOCUNICO_NNN.<extension>
Otros	OTROS_NNN.<extensión>

Las extensiones de los ficheros se ajustarán a la siguiente tabla:

Formato	Extensiones válidas
Excel	XLS o XLSX
QuatroPro	WQ1
Lotus	WK1
Word	DOC o DOCX
Rich Text Format	RTF
Acrobat Reader	PDF
Open Office	ODS y ODT

C) Archivo DATOS.TXT:

Fichero de datos [OTROS DATOS] correspondientes a la solicitud y a la certificación, ajustándose a la estructura siguiente:

Código de campo	Formato	Longitud	Contenido del campo
101	Alfanumérico	8	Fecha de la solicitud (ddmmaaaa)
102	Alfanumérico	100	Nombre o Denominación Social del empresario
103	Alfanumérico	32	Primer apellido
104	Alfanumérico	32	Segundo apellido
105	Alfanumérico	9	NIF
106	Alfanumérico	32	Domicilio
107	Alfanumérico	32	Ciudad
108	Numérico	5	Código Postal
109	Numérico	2	Código de la Provincia
110	Alfanumérico	10	Fax
111	Alfanumérico	10	Teléfono
112	Numérico	5	Código de Registro
201	Alfanumérico	6	Tomo (Datos Registrales)
202	Alfanumérico	6	Libro (Datos Registrales)
203	Alfanumérico	6	Sección (Datos Registrales)
204	Alfanumérico	6	Folio (Datos Registrales)
205	Alfanumérico	32	Tipo de Registro Público
206	Alfanumérico	6	Hoja (Datos Registrales)
207	Alfanumérico	32	Otros (Datos Regístrales)
301	Alfanumérico	100	Nombre o Denominación Social del presentante
302	Alfanumérico	32	Primer apellido presentante
303	Alfanumérico	32	Segundo apellido presentante
304	Alfanumérico	9	DNI presentante
305	Alfanumérico	32	Domicilio presentante
306	Alfanumérico	32	Ciudad presentante
307	Alfanumérico	5	Código postal presentante
308	Alfanumérico	32	Provincia del presentante
309	Alfanumérico	10	Fax presentante
310	Alfanumérico	10	Teléfono presentante
311	Alfanumérico	60	Correo electrónico presentante
401	Alfanumérico	2	Solicita retención (SI/NO)
501	Numérico	3	Número total de libros presentados

Y para cada uno de los libros, en conjunto de seis registros:

Código de campo	Formato	Longitud	Contenido del campo
xxx01	Alfanumérico	100	Descripción del libro
xxx02	Numérico	3	Número del libro
xxx03	Alfanumérico	8	Fecha de apertura del libro (ddmmaaaa)
xxx04	Alfanumérico	8	Fecha de cierre del libro (ddmmaaaa)
xxx05	Alfanumérico	8	Fecha último cierre (ddmmaaaa)
xxx06	Alfanumérico	64	Huella digital del libro

Donde xxx cambiará para cada libro, y por lo tanto para cada grupo de esos cuatro registros, yendo desde el 001 para el primer grupo (el primer libro), hasta el 180 en caso de presentarse el máximo número posible de libros para cada uno de los 20 tipos posibles de dichos libros. El valor xxx ha de coincidir con el orden de líneas del fichero NOMBRES.TXT

D) Rutina cálculo huella digital:

Para generar la huella digital correspondiente a cada libro, se aplicará al fichero de dicho libro el algoritmo estándar SHA256 (RFC 6234) el cual producirá un hash de 256 bits (32 bytes), dicho conjunto de bits a su vez se codificará para su conversión en texto según el estándar base64 (RFC 4648).

Formato ZIP:

Todos los ficheros que componen la legalización se encontrarán comprimidos en un archivo con extensión.ZIP. La tecnología de compresión para conseguir el fichero.ZIP será la de la versión 2.0 o anteriores. Todos los ficheros incluidos en el.ZIP penderán directamente de la raíz (sin estructurarlos en directorios). El algoritmo de compresión será el Deflate estándar (no el Deflate 64) y no se usarán cifrados ni signaturas.
