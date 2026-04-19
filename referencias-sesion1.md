# Referencias · Sesión 1 — Entiendo la IA

Material complementario para los asistentes. Aquí encontraréis los enlaces y prompts que hemos visto durante la sesión.

---

## Conoce Claude

| Recurso | Enlace |
|---------|--------|
| Claude (web) | [claude.ai](https://claude.ai) |
| Descargar app de escritorio | [claude.ai/downloads](https://claude.ai/downloads) |

---

## Prompting — la versión de bolsillo (ICR)

### Ejemplo ICR completo

```
[INSTRUCCIONES]
Redacta un email al director de servicios generales del Hospital
Vall d'Hebron informando de que el mantenimiento preventivo de
climatización de abril se adelanta una semana por una incidencia
detectada en la última revisión.

[CONTEXTO]
Soy Carlos Manzanares, director comercial de Geinstal. Llevamos
el mantenimiento integral del hospital desde hace 8 años. En la
última revisión trimestral, el técnico detectó un desgaste anormal
en los rodamientos del equipo de climatización de la planta 3. No
es urgente, pero conviene intervenir antes de que suba la temperatura
exterior en mayo.

[RESTRICCIONES]
Tono profesional pero cercano — llevamos muchos años trabajando juntos.
Máximo 150 palabras.
Incluye propuesta de fecha: lunes 21 de abril a las 8:00.
```

### Pro Tip 1 — Entrevista contextual

Cierra tu prompt con *"hazme todas las preguntas que necesites"* y deja que Claude te entreviste antes de responder:

```
Necesito preparar una propuesta comercial para un nuevo cliente
— un centro comercial en Terrassa que quiere externalizar el
mantenimiento de todas sus instalaciones (HVAC, electricidad,
fontanería, PCI).

Antes de redactar nada, hazme todas las preguntas que necesites
para tener contexto y hacerlo bien.
```

### Pro Tip 2 — Investiga primero, pregunta después

Dos prompts en el mismo chat. Primero que investigue, luego la tarea real:

**Prompt 1:**
```
Investiga cuáles son los requisitos actuales del RITE para el
mantenimiento preventivo de climatización en edificios de uso
comercial con potencia superior a 70 kW. Resume las claves.
```

**Prompt 2** (a continuación, en el mismo chat):
```
Bien. Ahora con eso en mente, redáctame un checklist de las
10 operaciones de mantenimiento preventivo que nuestros técnicos
deben hacer en cada revisión trimestral de un centro comercial,
ordenadas por prioridad.
```

---

## Palanca 1 · Resumir — De un pliego de 80 páginas a un resumen ejecutivo

### Pliego de ejemplo

Pliego de Prescripciones Técnicas para mantenimiento integral de un edificio público (28 páginas). Incluye electricidad, climatización, PCI, fontanería, CCTV, control, jardinería.

Fuente: [contrataciondelestado.es](https://www.food.imdea.org/sites/default/files/Pliego%20tecnico%20Mantmto%20Edificio%202017.pdf)

### Instrucciones del Project

Antes de lanzar el prompt, crea un Project en Claude con estas instrucciones:

> **Nombre del proyecto:** Licitación Mantenimiento Edificio Público
>
> **Instrucciones:**
> Eres mi asistente para la preparación de esta oferta de licitación. Tono formal corporativo. Geinstal es una empresa de mantenimiento integral con 305 empleados, 35M€ de facturación, especializada en HVAC, electricidad, fontanería y PCI. Siempre verificas datos del pliego antes de afirmar. No haces promesas que no podamos respaldar.

Sube el PDF del pliego como archivo del proyecto. Cada chat dentro del proyecto heredará el pliego y las instrucciones automáticamente.

### Prompt de la demo

```
Resume este pliego de licitación. Extrae en formato tabla:
- Objeto del contrato
- Presupuesto base de licitación (sin IVA e IVA incluido)
- Plazo de ejecución
- Requisitos de solvencia técnica (experiencia, personal, medios)
- Requisitos de solvencia económica (facturación mínima)
- Criterios de adjudicación con ponderación (automáticos vs juicio de valor)
- Plazo de presentación de ofertas
- Penalizaciones relevantes

Después evalúa si una empresa con este perfil cumple los requisitos:
- 305 empleados, 45 ingenieros
- Facturación anual: 35M€
- Especialidades: HVAC, electricidad, fontanería, PCI, telecomunicaciones
- Experiencia: 30 años en mantenimiento integral de hospitales y edificios
  públicos en Cataluña
```

---

## Palanca 2 · Crear y editar — Email profesional a un cliente insatisfecho

### Prompt

```
Redacta un email profesional al director de servicios generales
del Hospital Vall d'Hebron.

Contexto: Se queja de que tardamos 6 horas en responder a una
urgencia de climatización en la planta de pediatría. La demora
fue porque la pieza de repuesto (válvula de expansión del equipo
Carrier 30XA) no estaba en nuestro almacén local y hubo que
traerla del proveedor en Martorell.

El email debe:
1. Reconocer el problema y disculparse sin culpar al equipo
2. Explicar la causa técnica de forma comprensible para un no-técnico
3. Detallar las medidas correctivas: hemos implementado un protocolo
   de piezas críticas en stock para sus equipos
4. Proponer una reunión de seguimiento la próxima semana
5. Tono: profesional, empático pero firme. No servil.

Firma como: Director Comercial, Geinstal
```

### Iteración (segundo prompt en el mismo chat)

```
Hazlo más corto, máximo 150 palabras, y añade la fecha
de reunión: martes 22 de abril a las 10:00.
```

---

## Palanca 3 · Investigar — Subvenciones de eficiencia energética en Cataluña

### Prompt

```
¿Qué subvenciones y ayudas públicas hay activas en Cataluña
para mejoras de eficiencia energética en edificios públicos?

Incluye:
- Programas autonómicos (Generalitat / ICAEN) y estatales (IDAE)
- Plazos de solicitud vigentes
- Cuantías o porcentajes de subvención
- Requisitos de elegibilidad
- Si aplican a empresas de mantenimiento como ejecutoras

Céntrate en lo que esté abierto o próximo a abrirse.
```

> **Antes y después:** lanzar primero el prompt tal cual. Después, activar el modo **Investigación** (botón `+` → Investigación) y lanzar el mismo prompt — esta vez devolverá un informe con citas verificables. Compara las dos respuestas.

> **Importante:** la IA puede inventar datos. Las subvenciones y plazos que devuelva deben verificarse en las fuentes oficiales antes de actuar sobre ellas.

---

## Palanca 4 · Estructurar y transformar — Un informe técnico → 3 versiones

### Informe técnico de ejemplo (pegar antes del prompt)

```
INFORME DE INTERVENCIÓN — Mantenimiento correctivo
Fecha: 14/04/2026
Técnico: J. Sánchez
Cliente: Hospital Vall d'Hebron — Planta 3 Pediatría
Equipo: Unidad climatizadora Carrier 30XA-0602 (potencia 180 kW)
Incidencia: Aviso por ruido anormal y vibración excesiva en el compresor.
Diagnóstico: Rodamientos del compresor con desgaste avanzado. Holgura
en el eje principal. Filtros de aire en estado aceptable pero próximos
a sustitución. Válvula de expansión con respuesta lenta.
Trabajos realizados: Sustitución de rodamientos del compresor (2 uds,
ref. SKF 6312-2RS). Reajuste del eje principal. Limpieza de la bandeja
de condensados. Verificación de presiones de refrigerante (R-410A):
alta 28 bar, baja 9 bar — dentro de rango. Medición de consumo:
42A por fase — correcto.
Pendiente: Programar sustitución de filtros en próxima preventiva (mayo).
Valorar sustitución de válvula de expansión si persiste respuesta lenta.
Tiempo total: 4,5 horas. Material: 2x rodamientos SKF 6312-2RS (stock).
```

### Prompt

```
Tengo este informe técnico de una intervención de mantenimiento.
Necesito 3 versiones:

1. RESUMEN EJECUTIVO para el director del hospital (no técnico):
   1 párrafo, lenguaje accesible, enfocado en estado del equipo
   y acciones pendientes.

2. EMAIL INTERNO para el responsable de departamento: bullet points,
   enfocado en la incidencia de vibración y la acción requerida
   (pedir rodamientos, programar intervención).

3. REGISTRO GMAO: campos estándar (fecha, equipo, tipo intervención,
   trabajos realizados, incidencias, acciones pendientes, técnico, horas).
```

### Artifacts (segundo prompt en el mismo chat)

```
Ahora entrégame las 3 versiones como artifacts separados
para poder editarlas independientemente.
```

---

## Palanca 5 · Analizar información — Órdenes de trabajo Q1 2026

### Archivo de datos

`ordenes-trabajo-q1-2026.xlsx` — 120 registros ficticios con columnas: Fecha, Cliente, Tipo (Preventiva/Correctiva/Urgencia), Descripción, Tiempo respuesta (h), Horas trabajo, Técnico, Resolución 1ª visita.

Clientes: Hospital Vall d'Hebron, SEAT Martorell, UAB Bellaterra, Danone Parets, CCCB Barcelona.


### Prompt (genera informe descargable en PDF)

```
Analiza esta tabla de órdenes de trabajo del departamento
de mantenimiento (Q1 2026).

Necesito:
1. Cliente con más incidencias correctivas (no preventivas)
2. Tiempo medio de respuesta en urgencias por cliente
3. Tasa de resolución en primera visita por técnico
4. Tendencia: ¿hay algún cliente cuyo servicio está empeorando?
5. Recomendaciones concretas para el responsable de departamento

Redacta un email con el resumen para enviarlo antes de la
reunión mensual de directores.
```

### Dashboard visual (segundo prompt en el mismo chat)

```
Ahora preséntame el mismo análisis como un dashboard visual
interactivo con gráficos de los KPIs principales.
```

### Claude para Excel — plugin y prompts para la demo (Bloque 4, slide 81)

Abrir el Excel `ordenes-trabajo-q1-2026.xlsx` con el complemento de Claude activo.

**Prompt dentro de Excel:**

```
Analiza estos datos. Crea una columna nueva "Urgencia" que
clasifique como "Crítica" si el tiempo de respuesta es >4h.

Genera un gráfico de barras con incidencias correctivas por
cliente y un gráfico de líneas con la evolución del tiempo
de respuesta por mes en una nueva pestaña que se llame Análisis.
```

**Instalar el complemento:**

Descargar plugin: [Claude for Excel — Microsoft Marketplace](https://marketplace.microsoft.com/es-es/product/saas/wa200009404?tab=overview)

Más info: [Claude for Excel — Help Center](https://support.claude.com/en/articles/12650343-usa-claude-para-excel)

---

## Palanca 6 · Razonar y decidir — ¿Nos presentamos a esta licitación?

> Esta demo se hace **dentro del mismo Project** de la Palanca 1. Claude ya tiene el pliego de IMDEA Alimentación cargado y las instrucciones del proyecto.

### Prompt (abrir chat nuevo dentro del Project)

```
Analiza el pliego que tienes en el proyecto y evalúa si Geinstal
debería presentarse a esta licitación.

Perfil de Geinstal:
- 305 empleados, 45 ingenieros, 35M€ facturación
- Especialidades: HVAC, electricidad, fontanería, PCI, telecomunicaciones
- Experiencia: 30 años en hospitales y edificios públicos en Cataluña
- NO tenemos experiencia en edificios de investigación ni laboratorios
- Equipo de Estudios con capacidad actual al 80%
- Sede en Sant Cugat del Vallès (Barcelona) — el edificio está en Madrid

Analiza:
1. ¿Qué instalaciones cubre el pliego y cuáles dominamos / cuáles no?
2. Fortalezas y debilidades de nuestra candidatura
3. Riesgos principales (incluyendo la distancia geográfica)
4. Estrategia recomendada (presentarse / no presentarse / con socios)
5. Si nos presentamos: ¿qué priorizamos en la oferta técnica?
```

---

## Palanca 7 · Automatizar — 5 emails de renovación personalizados (opcional)

### Datos de los 5 contratos (pegar antes del prompt)

| Cliente | Tipo | Importe anual | Años activo | Incidencias Q1 |
|---------|------|--------------|-------------|----------------|
| Hospital Vall d'Hebron | Público | 450.000€ | 8 | 12 (2 urgentes) |
| SEAT Martorell | Privado | 280.000€ | 3 | 8 (3 urgentes) |
| UAB Bellaterra | Público | 180.000€ | 5 | 3 |
| Danone Parets | Privado | 120.000€ | 2 | 2 |
| CCCB Barcelona | Público | 95.000€ | 1 | 1 |

### Prompt

```
Estos 5 contratos vencen en mayo 2026. Genera un email de
renovación personalizado para cada uno. Adapta:
- Tono (formal para público, cercano para privado)
- Argumentos (historial largo vs relación nueva)
- Si hay muchas incidencias, reconocerlas y explicar
  mejoras implementadas
```

### Connector Gmail (segundo prompt en el mismo chat)

```
Ahora créame cada uno como un borrador en mi bandeja de Gmail.
```

> **Configurar Outlook:** Geinstal usa Microsoft 365. IT debe habilitar el conector siguiendo esta guía: [Habilitar y usar el conector de Microsoft 365](https://support.claude.com/es/articles/12542951-habilitar-y-usar-el-conector-de-microsoft-365)


---

## Palanca 8 · Aprender — Plan de onboarding para un nuevo TGC (opcional)

### Prompt

```
Crea un plan de onboarding de 4 semanas para un nuevo Técnico
de Gestión de Contratos (TGC) que se incorpora al departamento
de Mantenimiento de Geinstal.

El TGC gestiona contratos de mantenimiento de edificios públicos
y privados. Sus tareas principales son: coordinar técnicos de campo,
gestionar incidencias, generar documentación administrativa
(certificados RITE, informes de intervención, actas de revisión),
y relación con clientes.

Herramientas que usará: GMAO GIM (TCMAN), Outlook, Excel, SAGE.

Estructura el plan con:
- Objetivos semanales
- Actividades concretas cada día
- Persona de referencia para cada tema
- Checklist de competencias a validar al final de cada semana
```

### Artifact (segundo prompt en el mismo chat)

```
Convierte el plan en un artifact editable con calendario
visual por semanas.
```

---

## Palanca 9 · Practicar — Simulación con un cliente que quiere rescindir (opcional)

### Prompt

```
Simula que eres el director de servicios generales del Hospital
Germans Trias i Pujol. Estás muy enfadado porque:
- En el último mes ha habido 3 fallos de climatización en la UCI
- El último fallo duró 8 horas y tuvisteis que trasladar pacientes
- Estás considerando rescindir el contrato de mantenimiento
  con Geinstal

Yo soy el director de Mantenimiento de Geinstal y voy a intentar
salvar la relación.

Actúa de forma realista: enfadado pero profesional.
No me lo pongas fácil. Quiero practicar.
```

### Primera respuesta del formador (para arrancar la escena)

Después de que Claude suelte su primer monólogo, pegar esta respuesta para dar juego:

```
Tiene razón. No voy a justificar lo injustificable. Tres fallos
en la UCI en un mes es inaceptable y lo sé.

Le pido una cosa antes de que tome cualquier decisión: déjeme
enseñarle lo que hemos hecho esta semana. No promesas, hechos.
Hemos cambiado al técnico responsable de su contrato, hemos
triplicado el stock de repuestos críticos para sus equipos, y
hemos instalado sensores de temperatura con alerta directa a
mi móvil personal. Si vuelve a pasar, me voy a enterar yo antes
que sus enfermeras.

Ahora bien, entiendo perfectamente que eso no borra lo que ha
pasado. ¿Qué necesita ver de nosotros en los próximos 30 días
para no activar esa cláusula?
```

---

## Mega Prompt 1 · Inteligencia competitiva — Análisis de competidores en Cataluña (slide 69)

> **Activar modo Investigación** (botón `+` → Investigación) antes de lanzar el prompt. Tarda 5-15 min. Lanzar al inicio y seguir con la lluvia de ideas (slide 70) mientras trabaja.

### Prompt

```
<rol>
Eres un analista de inteligencia competitiva especializado en el
sector de mantenimiento integral de edificios e instalaciones
en España, concretamente en Cataluña.
</rol>

<tarea>
Investiga y analiza a los principales competidores de Geinstal
en el mercado catalán de mantenimiento integral de edificios.

Geinstal: 305 empleados, 35M€ facturación, sede en Sant Cugat,
especialistas en HVAC, electricidad, fontanería, PCI.
Clientes: hospitales (Vall d'Hebron, Germans Trias, Sant Joan de Déu),
universidades (UAB, UIC, UPC), edificios públicos, empresas privadas.

Para cada competidor identificado:
1. Nombre, tamaño estimado (empleados/facturación), sede
2. Especialización principal
3. Clientes conocidos (especialmente si compiten por los mismos)
4. Donde son MÁS fuertes que Geinstal
5. Donde son MÁS débiles que Geinstal

Después genera:
- Mapa de posicionamiento: eje X = tamaño, eje Y = especialización
  (generalista vs especialista)
- 3 ventajas competitivas que Geinstal tiene y no está explotando
- 3 amenazas de competidores que deberían vigilar
- 1 nicho de mercado que ningún competidor está cubriendo bien
</tarea>
```

---

## Mega Prompt 2 · Lluvia de ideas — 15 ideas de negocio en eficiencia energética (slide 70)

> Se puede hacer en el mismo chat que la inteligencia competitiva, así Claude ya tiene el análisis de competidores como contexto.

### Prompt

```
<rol>
Eres un consultor estratégico especializado en el sector de
mantenimiento integral de edificios e instalaciones en España.
Conoces el mercado, la normativa, y las tendencias tecnológicas.
</rol>

<contexto>
Geinstal es una empresa de mantenimiento integral con 305 empleados,
35M€ de facturación, especializada en HVAC, electricidad, fontanería
y PCI. Nuestros clientes principales son hospitales, universidades,
edificios públicos y empresas privadas en Cataluña.

Queremos explorar nuevas líneas de negocio o servicios de valor
añadido relacionados con la eficiencia energética y la
sostenibilidad, aprovechando nuestra base de clientes y
nuestro conocimiento técnico.
</contexto>

<tarea>
Genera 15 ideas de nuevas líneas de negocio o servicios.
Para cada idea:
1. Nombre del servicio (3-5 palabras)
2. Descripción (2 frases)
3. Cliente objetivo (qué tipo de cliente lo contrataría)
4. Ventaja competitiva de Geinstal (por qué nosotros y no otro)
5. Inversión estimada para lanzar: Baja (<10K) / Media (10-50K) / Alta (>50K)
6. Tiempo hasta generar ingresos: Corto (<3 meses) / Medio (3-12 meses) / Largo (>12 meses)

Organiza las 15 ideas en 3 categorías:
- Quick Wins (baja inversión + corto plazo)
- Apuestas estratégicas (media inversión + alto potencial)
- Moonshots (alta inversión + transformacionales)
</tarea>
```

### Profundizar (segundo prompt)

```
De las 15 ideas, desarrolla en profundidad la #3 y la #7.
Para cada una: modelo de negocio, pricing sugerido, primeros
3 pasos para lanzar en 30 días, y riesgos principales.
```

### Artifact (tercer prompt)

```
Preséntamelo como un artifact tipo dashboard con tarjetas
agrupadas por categoría.
```

---

## Mega Prompt 3 · Auditoría operativa — 5 entregables en un solo prompt (slide 71)

> Usa el mismo Excel `ordenes-trabajo-q1-2026.xlsx` de la Palanca 5.

### Prompt

```
<rol>
Eres un consultor senior especializado en operaciones de empresas
de mantenimiento de edificios. Has auditado 50+ empresas del sector
y sabes identificar dónde se pierde dinero y dónde hay potencial
de mejora.
</rol>

<datos>
Te adjunto los datos operativos del departamento de Mantenimiento
de Geinstal del Q1 2026 (enero-marzo).
</datos>

<entregables>

1. INFORME DE FUGAS DE EFICIENCIA
- Dónde se pierde tiempo (intervenciones con tiempos anormales)
- Dónde se pierde dinero (clientes no rentables, revisitas evitables)
- Ranking de gravedad: Crítico / Mayor / Menor
- Para cada fuga: causa probable y acción correctora

2. ANÁLISIS DE CLIENTES
- Segmentar clientes en 3-4 perfiles por comportamiento
  (bajo mantenimiento vs intensivo, urgencias frecuentes, etc.)
- Para cada segmento: rentabilidad estimada, riesgo de fuga,
  oportunidad de upselling
- El cliente más rentable y por qué
- El cliente que más cuesta mantener y qué hacer con él

3. ANÁLISIS DE EQUIPO
- Rendimiento por técnico (velocidad, resolución primera visita)
- Patrones: ¿hay técnicos que rinden mejor en cierto tipo de cliente?
- Recomendaciones de asignación óptima

4. PLAN DE ACCIÓN 90 DÍAS
- Semana a semana: acciones concretas
- Cada acción con: impacto estimado (Alto/Medio/Bajo) +
  esfuerzo requerido (Alto/Medio/Bajo)
- Las 2 primeras semanas: ejecutables sin contratar a nadie

5. RESUMEN EJECUTIVO (para Blanca)
- 1 página, lenguaje directo, sin jerga técnica
- Conclusión primero, datos después
</entregables>
```

### Artifacts (segundo prompt)

```
Reorganízame los 5 entregables como artifacts separados y navegables.
```

---

## Mega Prompt 4 · RRHH — Screening inteligente de 5 candidatos (slide 72)

### Prompt

```
<rol>
Eres un especialista en selección de personal para el sector
de mantenimiento integral de edificios. Sabes que en este sector
la experiencia práctica y las certificaciones técnicas pesan más
que los títulos académicos.
</rol>

<vacante>
Técnico de Gestión de Contratos (TGC) para el departamento
de Mantenimiento de Geinstal.

Requisitos críticos:
- Experiencia en gestión de contratos de mantenimiento (min 2 años)
- Conocimiento de normativa RITE
- Manejo de GMAO (cualquier plataforma)
- Capacidad de coordinación de equipos de campo
- Residencia en área metropolitana de Barcelona

Deseables:
- Experiencia en hospitales o edificios públicos
- Certificación energética
- Inglés nivel intermedio

Cultura Geinstal: empresa familiar de 30 años, cercana,
profesional, orientada a servicio, valora compromiso y autonomía.
</vacante>

<candidatos>
Candidato 1: María López — Ingeniera industrial, 4 años en Veolia
gestionando contratos de climatización en hospitales. Certificación
RITE. Vive en Sabadell.

Candidato 2: Pere García — FP2 Instalaciones, 8 años como técnico
de campo en Acciona Mantenimiento. Sin experiencia en gestión de
contratos pero es jefe de equipo informal. Vive en Terrassa.

Candidato 3: Laura Fernández — Arquitecta técnica, 2 años en
consultoría energética (sin experiencia en mantenimiento).
Certificación LEED y ISO 50001. Vive en Barcelona.

Candidato 4: Jordi Puig — FP2 Electromecánica, 12 años en
Geinstal como técnico de campo. Quiere pasar a gestión.
Conoce GIM y todos los clientes. Sin título universitario.

Candidato 5: Ana Ruiz — MBA + 3 años en gestión de facilities
en Sodexo. Sin conocimientos técnicos profundos de HVAC.
Vive en Madrid, dispuesta a trasladarse.
</candidatos>

<entregable>
Para cada candidato:
1. Puntuación 0-100 (40% competencias técnicas, 30% experiencia
   relevante, 20% encaje cultural, 10% disponibilidad)
2. 3 fortalezas específicas
3. 2 riesgos principales
4. 1 pregunta de entrevista personalizada para este candidato
5. Recomendación: Entrevistar / Quizás / Descartar

Al final: ranking ordenado + la sorpresa (quién puntuaría bajo
en un filtro tradicional pero tiene potencial real).
</entregable>
```

### Artifact (segundo prompt)

```
Preséntame el ranking como una tabla interactiva ordenable
por columnas (puntuación total, encaje cultural, experiencia,
competencias técnicas).
```

---

## Mega Prompt 5 · Base de conocimiento — Mapa de riesgos de Geinstal (slide 73)

### Prompt

```
<rol>
Eres un especialista en gestión del conocimiento empresarial.
Tu trabajo es identificar dónde está el conocimiento crítico
de una organización y cómo institucionalizarlo para que no
dependa de personas concretas.
</rol>

<contexto>
Geinstal tiene 305 empleados y 30 años de historia. Mucho
conocimiento crítico está en la cabeza de personas concretas:
- Los técnicos veteranos conocen las instalaciones de cada
  cliente mejor que la documentación oficial
- Las administrativas saben los requisitos documentales
  de cada cliente (cada hospital pide cosas diferentes)
- Los directores de departamento tienen relaciones personales
  con clientes clave
- Los ingenieros de Estudios conocen los criterios no escritos
  de las mesas de contratación

Herramientas actuales: GMAO GIM (TCMAN), Outlook, Excel, SAGE.
No tienen wiki interna ni sistema de gestión del conocimiento.
</contexto>

<tarea>
1. MAPA DE RIESGOS DE CONOCIMIENTO
   - Identifica 10 áreas de conocimiento crítico en una empresa
     de mantenimiento integral como Geinstal
   - Para cada área: dónde está ese conocimiento hoy (personas,
     documentos, sistemas), riesgo de pérdida (Alto/Medio/Bajo),
     impacto si se pierde

2. PLAN DE CAPTURA RÁPIDA (sin tecnología nueva)
   - 5 acciones que pueden hacer MAÑANA usando herramientas
     que ya tienen (Outlook, Word, Excel)
   - Para cada acción: qué capturar, quién lo hace, cuánto tarda,
     dónde se guarda

3. VISIÓN A 6 MESES
   - Cómo sería una base de conocimiento básica de Geinstal
   - Estructura propuesta (categorías, subcategorías)
   - Qué herramienta usarían (Notion, SharePoint, wiki interna)
   - Coste estimado y esfuerzo de implementación
</tarea>
```

### Artifacts (segundo prompt)

```
Estructúrame los 3 entregables como artifacts separados navegables.
```

---

## Gemini — Generación y edición de imágenes (slide 76)

| Recurso | Enlace |
|---------|--------|
| Gemini | [gemini.google.com](https://gemini.google.com/) |

> Activar la opción **"Crear imagen"** antes de lanzar el prompt.

### Prompt (generar imagen)

```
Genera una imagen profesional de un equipo de técnicos
revisando un sistema de climatización en la sala de máquinas
de un hospital moderno. Estilo fotográfico, iluminación
profesional, aspecto corporativo.
```

### Prompt (editar la imagen generada)

```
Modifica la imagen: añade el logo adjunto en la esquina inferior derecha, y cambia el color de los uniformes de los técnicos al mismo color del logo.
```

### Prompt (infografía sobre el temario de la sesión)

Subir `temario-sesion1.pdf` a Gemini y pedir:

```
Genera una infografía visual que resuma los contenidos principales del documento adjunto.
```

---

## NotebookLM — Analiza documentos y genera podcasts (slide 77)

| Recurso | Enlace |
|---------|--------|
| NotebookLM | [notebooklm.google.com](https://notebooklm.google.com/) |

### Preparación previa

Crear un notebook y subir estos documentos:
- `pliego-ejemplo-mantenimiento-integral.pdf` (el de IMDEA) → para podcast y pregunta cruzada
- `temario-sesion1.pdf` → para infografía y mapa mental

### Prompt (pregunta cruzada sobre el pliego)

```
¿Qué requisitos del pliego no cubriría una empresa especializada
en hospitales pero sin experiencia en laboratorios ni geotermia?
```

### Podcast

Usar la opción **"Generar audio"** sobre el pliego de IMDEA. NotebookLM generará una conversación de 5-10 minutos resumiendo el documento.

> Preparar el podcast ANTES de la sesión — tarda unos minutos en generarse. Así en la demo solo le das al play.

### Mapa mental (sobre el temario de la sesión)

```
Genera un mapa mental con los conceptos clave de este
documento y cómo se relacionan entre sí.
```

---

## Claude en Office — Complementos para Word, PowerPoint y Excel (slides 78-81)

### Instalar los complementos

| Complemento | Guía de instalación |
|-------------|---------------------|
| Claude para Word | [support.claude.com — Word](https://support.claude.com/es/articles/14465370-usar-claude-para-word) |
| Claude para PowerPoint | [support.claude.com — PowerPoint](https://support.claude.com/es/articles/13521390-usa-claude-para-powerpoint) |
| Claude para Excel | [support.claude.com — Excel](https://support.claude.com/es/articles/12650343-usa-claude-para-excel) |

### Demo Word (slide 79) — Contrato de mantenimiento con plantilla Geinstal

Abrir `plantilla-word-geinstal.docx` (portada corporativa con logo + barra verde + footer, y a partir de la página 2 header con logo circular sin footer). Activar complemento de Claude para Word.

**Prompt:**

```
Usando esta plantilla, redacta un contrato de mantenimiento integral
entre Geinstal S.A. (mantenedor) y Centro Comercial Terrassa Parc
(cliente) para todas las instalaciones del edificio (HVAC, electricidad,
PCI, fontanería, CCTV).

En la portada sustituye "TÍTULO DEL DOCUMENTO" por:
"CONTRATO DE MANTENIMIENTO INTEGRAL DE INSTALACIONES" y añade
debajo la fecha y la referencia GEI-MNT-2026-041.

A partir de la página 2, desarrolla las cláusulas completas:

1. Objeto y alcance del servicio
2. Duración, prórrogas y preaviso de denuncia
3. Precio, revisión anual (IPC) y forma de pago
4. Obligaciones del mantenedor (SLA, tiempos de respuesta por
   criticidad, reporting mensual)
5. Obligaciones del cliente
6. Garantías y responsabilidad civil
7. Confidencialidad y protección de datos (RGPD)
8. Penalizaciones por incumplimiento de SLA
9. Causas de resolución
10. Jurisdicción y ley aplicable (tribunales de Barcelona)
11. Anexos: inventario de instalaciones, plan preventivo anual,
    tarifa de materiales, listado de contactos 24/7

Extensión objetivo: 8-12 páginas. Mantén el formato corporativo de
la plantilla (logo en cada página, márgenes, tipografía).
```

#### Demos adicionales sobre el contrato ya generado

> Con el contrato abierto (`contrato-demo1.docx`), ejecutar estas demos en el mismo panel.

**A. Q&A con citas clicables sobre el contrato**

```
¿Cuál es la duración del contrato y en qué condiciones se prorroga?
¿Qué plazo de preaviso hay para denunciarlo? Cítame las cláusulas
exactas.
```

> Cada cita en la respuesta es clicable: lleva directamente a la cláusula del Word.

**B. Extracción en tabla — resumen ejecutivo**

```
Al final del documento, añade una sección titulada
"Anexo · Resumen ejecutivo" con una tabla de 2 columnas
(Concepto | Detalle) y estas filas:

- Partes
- Objeto
- Duración y prórrogas
- Precio y revisión
- SLA (tiempos de respuesta por criticidad)
- Penalizaciones máximas
- Jurisdicción

Rellena cada celda con la información extraída del contrato.
```

> Verifica que la tabla queda insertada al final del documento y respeta la tipografía y márgenes de la plantilla.

**C. Edición con control de cambios activado**

```
Activa el control de cambios. Rebaja las penalizaciones por
incumplimiento de SLA del 15% al 5% del importe anual, y ajusta
proporcionalmente la cláusula 8. Además, reduce la duración
inicial del contrato de 3 años a 2 años y actualiza todas las
referencias cruzadas afectadas.
```

> Abre el panel de Revisión de Word para ver cada cambio marcado como inserción o eliminación.

**C-bis. Detectar cambios hechos por otro usuario**

> Con el control de cambios aún activado, edita manualmente la cláusula del alcance del servicio: sustituye `(b) Instalaciones eléctricas de baja tensión` por `(b) Instalaciones eléctricas de alta tensión`. Guarda el documento. Luego lanza a Claude:

```
¿Qué cambios se han hecho desde la última revisión? Agrúpalos
por autor y dime cuáles son sustantivos y cuáles cosméticos.
```

> La respuesta agrupa los cambios por autor y fecha: tu edición manual aparece distinguida de las que hizo Claude. Es el mismo flujo cuando un cliente o abogado devuelve un contrato con redlines.

**D. Traducción bilingüe de una cláusula sensible**

```
Crea una tabla de dos columnas (español | inglés) al final del
documento con la traducción de la cláusula 10 (Jurisdicción y ley
aplicable). Mantén ambas columnas alineadas párrafo a párrafo.
Título de la tabla: "Anexo bilingüe · Jurisdicción".
```

> Verifica que la tabla bilingüe aparece al final del documento con los párrafos alineados español-inglés.

**E. Revisión de calidad y consistencia**

```
Revisa el documento entero y listame:

1. Términos definidos usados con nombres distintos (p.ej. "el
   Cliente" vs "la Propiedad" vs "Terrassa Parc").
2. Referencias cruzadas rotas o inexistentes.
3. Inconsistencias en fechas, cifras o plazos.
4. Errores de ortografía, concordancia o tiempos verbales.

Para cada hallazgo, indica la cláusula y propón la corrección.
```

> Para cada hallazgo se indica la cláusula exacta y se propone una corrección — útil al revisar contratos recibidos de un tercero.

---

### Demo PowerPoint (slide 80) — Presentación corporativa de Geinstal

Abrir PowerPoint con una presentación nueva. En la primera slide, pegar el logo de Geinstal. Activar el complemento de Claude.

**Prompt:**

```
En la primera diapositiva te he dejado el logo de Geinstal.
Quiero que me hagas una presentación corporativa completa de
la empresa Geinstal en base a la información que hay en su
web: https://www.geinstal.com/es/
```

**Después, pegar las fotos** de la carpeta `materiales/fotos/` en la última diapositiva y pedir:

```
En la última diapositiva te he dejado unas fotos de la empresa.
Revisalas y colócalas en las slides donde creas que vayan o
queden mejor respetando sus proporciones originales.
```

> Fotos disponibles: climatización, electricidad, PCI, control, equipo directivo, CCCB, Mercabarna.

**Prompt adicional — Traducción a italiano:**

```
Necesito esta presentacion en italiano para visitar a unos clientes potenciales
```

### Demo PowerPoint (slide 80) — Informe mensual con plantilla Geinstal

Abrir `plantilla-informe-mensual.pptx` (ya tiene portada con logo, barra verde y título). Activar complemento de Claude.

**Prompt:**

```
Usando esta plantilla, crea un informe mensual completo del
departamento de Mantenimiento de Geinstal para marzo 2026
con estos datos:

- 47 intervenciones totales: 32 preventivas, 15 correctivas
- Tiempo medio de respuesta en urgencias: 2.8 horas
- Tasa de resolución en primera visita: 78%
- Clientes con más incidencias: Vall d'Hebron (8), SEAT Martorell (4)
- SEAT Martorell con tendencia negativa: 3 urgencias sin resolver
  en primera visita
- Técnico más activo: J. Sánchez (34 OT)
- Técnico con menor resolución: D. Rodríguez (50%)
- Acción pendiente: reasignar técnico en SEAT y reforzar stock
  de repuestos para sus equipos

Incluye: slide de resumen ejecutivo, slide de datos clave con
gráficos, slide de análisis por cliente, slide de rendimiento
de equipo, y slide de acciones pendientes para abril.

Mantén el estilo visual de la plantilla (colores verdes Geinstal).
```

#### Demos adicionales sobre el informe mensual ya generado

> Con el informe mensual abierto, ejecutar estas demos.

**F. Pinpoint edit — simplificar una slide concreta**

```
Simplifica la slide 3, está muy cargada. Deja solo los 3 datos
más importantes y el resto muévelo a notas del orador.
```

> Solo debería modificarse la slide 3 — verifica que el resto del deck queda intacto y el formato se respeta.

**G. Bullets → gráfico nativo de PowerPoint**

```
En la slide de datos clave, convierte los bullets numéricos en
un gráfico de barras nativo de PowerPoint comparando
intervenciones preventivas vs correctivas, y otro gráfico de
dona con el % de resolución en primera visita.
```

> Para comprobar que son gráficos editables (no imágenes): clic derecho sobre el gráfico → "Editar datos".

**H. Reestructurar el storyline**

```
Reordena las slides para contar la historia al revés:
primero las acciones pendientes y recomendaciones para abril,
luego los datos que las justifican (clientes con incidencias,
rendimiento de técnicos) y al final un resumen ejecutivo de
cierre. Ajusta la slide de agenda en consecuencia.
```

> Verifica que la slide de agenda se ha actualizado para reflejar el nuevo orden de las secciones.

---

## Claude para Excel — Modelos financieros avanzados (slide 81)

> Seleccionar modelo **Opus** para estas demos (más avanzadas que el análisis básico).

### Prompt 1 — Construir un modelo de rentabilidad por cliente desde cero

Abrir un Excel nuevo con el complemento de Claude activo.

```
Actúa como un experto en control de gestión del sector de
mantenimiento de edificios. Soy el responsable financiero
de Geinstal, una empresa de mantenimiento integral con
305 empleados y 35M€ de facturación.

Necesito un modelo de rentabilidad por cliente para análisis
interno. Tenemos estos 5 contratos principales:

- Hospital Vall d'Hebron: 450.000€/año, 8 técnicos asignados,
  coste medio técnico 35.000€/año, material estimado 45.000€/año
- SEAT Martorell: 280.000€/año, 4 técnicos, material 30.000€/año
- UAB Bellaterra: 180.000€/año, 3 técnicos, material 15.000€/año
- Danone Parets: 120.000€/año, 2 técnicos, material 10.000€/año
- CCCB Barcelona: 95.000€/año, 1 técnico, material 8.000€/año

Construye un modelo en dos pestañas:
- Pestaña "Supuestos": todas las variables de entrada organizadas
  por cliente
- Pestaña "Modelo": cálculo mensual de ingresos, costes directos,
  margen bruto y margen neto por cliente, con un check de cuadre
  de totales y un gráfico comparativo de margen por cliente.

Usa fórmulas dinámicas que referencien la pestaña de supuestos.
```

> Fíjate en que el prompt no especifica columnas ni fórmulas — Claude decide la estructura del modelo a partir de la descripción del negocio.

### Prompt 2 — Mejorar el modelo sin re-explicarlo

En el mismo Excel, sin volver a describir el modelo:

```
Añade a la pestaña de supuestos una variable de "horas extra
por urgencias" para cada cliente, expresada como porcentaje
del coste base de técnicos. Usa estos valores iniciales:
Vall d'Hebron 8%, SEAT 15%, UAB 3%, Danone 5%, CCCB 2%.

Añade una fila de "coste de urgencias" al modelo que calcule
el impacto mensual y actualiza el gráfico para incluir una
línea de margen neto ajustado por urgencias.

Mantén todas las fórmulas y dependencias existentes intactas.
```

> Sin re-explicar el modelo, Claude mantiene todas las dependencias. Compara cómo cambia el margen de SEAT (15% urgencias) frente a CCCB (2%).

### Prompt 3 — Verificar y auditar el modelo

```
Revisa el modelo completo y ejecuta estas verificaciones:
1. ¿Cuadran los totales de ingresos con la suma por cliente?
2. ¿Hay algún cliente con margen neto negativo en algún mes?
3. ¿Las fórmulas de la pestaña Modelo referencian correctamente
   los supuestos?
4. Genera un resumen de salud del modelo con las conclusiones.
```

### Prompt 4 — Forecasting y escenarios (base / optimista / pesimista)

En el mismo modelo, sin re-explicarlo:

```
Añade una pestaña "Forecast" con proyección a 12 meses del
margen neto por cliente y consolidado. Crea tres escenarios:

- Base: mantiene los supuestos actuales
- Optimista: +8% en ingresos, -5% en costes directos,
  horas extra por urgencias reducidas a la mitad
- Pesimista: -5% en ingresos, +10% en costes, horas extra x2

Incluye una tabla de sensibilidad del margen neto consolidado
variando la tasa de crecimiento (-10% a +15%) y el coste
técnico (±20%). Marca en verde/rojo las combinaciones que
generan margen positivo/negativo.
```

> Comprueba en la pestaña Forecast los tres escenarios y la tabla de sensibilidad con celdas en verde/rojo según margen positivo o negativo.

### Prompt 5 — Explicar una fórmula existente (auditar modelo heredado)

Hacer clic en una celda con una fórmula compleja (p. ej. la de margen neto consolidado) y preguntar:

```
Explícame en cristiano qué hace la fórmula de la celda
seleccionada, qué supuestos arrastra desde otras pestañas,
y si hay algún riesgo de que se rompa al modificar datos
(referencias absolutas/relativas, dependencias ocultas).
```

> Fíjate en cómo Claude traza la fórmula hasta sus inputs en otras pestañas y señala los riesgos de que se rompa al modificar datos.

### Prompt 6 — Limpieza de datos sucios

> Cambiar al Excel `ordenes-trabajo-q1-2026.xlsx`.

```
Audita y limpia esta hoja: marca duplicados, homogeneiza
fechas a dd/mm/aaaa, separa Cliente en Grupo y Centro,
normaliza técnicos contra la plantilla (M. Olivares,
D. Rodríguez, D. Pérez, A. Fort, J. Sánchez), y crea una
pestaña "Anomalías" con atípicos y huecos. Informe breve
al final.
```

> Compara el informe de estado de los datos antes y después: verás cuántos duplicados, formatos incoherentes y anomalías ha limpiado.

---

## Cross-app: de Excel a PowerPoint automáticamente (slide 82, opcional)

Tener abiertos a la vez:
- **Excel**: `ordenes-trabajo-q1-2026.xlsx` (con la pestaña "Análisis" generada en la demo anterior)
- **PowerPoint**: `plantilla-informe-mensual.pptx`

### Prompt (desde el complemento de PowerPoint)

```
Tengo abierto un Excel con los datos de órdenes de trabajo del
departamento de Mantenimiento Q1 2026 y una pestaña "Análisis"
con gráficos ya generados.

Toma los datos y gráficos del Excel y genera las slides del
informe mensual en esta presentación. Incluye:
- Slide de resumen ejecutivo con los KPIs principales
- Slide con los gráficos de incidencias por cliente y evolución
  del tiempo de respuesta
- Slide de rendimiento por técnico
- Slide de acciones pendientes basadas en las recomendaciones

Mantén el estilo visual de la plantilla (colores verdes Geinstal).
```

> Ningún dato se ha copiado o pegado a mano: PowerPoint lee directamente del Excel abierto y genera las slides aplicando el estilo de la plantilla.

---

## Deberes post-sesión

1. **Date de alta en Claude** con la licencia que te facilite Geinstal: [claude.ai](https://claude.ai)
2. **Material de la sesión** — presentación y prompts de referencia:
   [github.com/danisev7/geinstal-ia-sesion1](https://github.com/danisev7/geinstal-ia-sesion1)
