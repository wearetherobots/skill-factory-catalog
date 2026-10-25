# Plazos y cómputo en días hábiles (CFF)

Advertencia: el CFF y la Resolución Miscelánea Fiscal (RMF) se reforman cada año. Antes de entregar una fecha, verifica el texto vigente para 2026 y el plazo que indica el propio oficio. Si hay contradicción, usa el plazo más corto y anótalo.

## Reglas de cómputo

1. Días hábiles (art. 12 CFF). No se cuentan:
   - Sábados y domingos.
   - 1 de enero; primer lunes de febrero; tercer lunes de marzo; 1 y 5 de mayo; 16 de septiembre; tercer lunes de noviembre; 25 de diciembre; 1 de diciembre cada seis años cuando hay transmisión del Ejecutivo Federal.
   - Días de vacaciones generales de las autoridades fiscales, publicados en la RMF (verificar la regla vigente de días inhábiles; históricamente un periodo en la segunda mitad de julio y otro a fin de diciembre).
   - Días en que las oficinas permanezcan cerradas en horario normal.
   - La autoridad puede habilitar días inhábiles para ciertas diligencias (por ejemplo, visitas); revisa si el oficio lo indica.
2. Plazos fijados en meses o años: de fecha a fecha. Si el último día es inhábil, el plazo se prorroga al siguiente día hábil (art. 12 CFF).
3. Las notificaciones surten efectos el día hábil siguiente a aquel en que se hacen (art. 135 CFF). El plazo inicia el día hábil siguiente a que surte efectos.
   - Fórmula: Día N = notificación; N+1 hábil = surte efectos; N+2 hábil = día 1 del plazo.
4. Buzón Tributario (arts. 17-K y 134 fr. I CFF): la notificación se tiene por hecha cuando el contribuyente abre el documento; si no lo abre dentro de los tres días hábiles siguientes al aviso, se tiene por notificado al cuarto día hábil. Verificar redacción vigente.
5. Notificación personal: si hubo citatorio y no se atendió, la diligencia se entiende con quien se encuentre (art. 137 CFF). Toma la fecha del acta de notificación.
6. Promociones electrónicas fuera de horario o en día inhábil: verifica en la RMF vigente cómo se tienen por presentadas. Recomienda no presentar el último día.

## Plazos frecuentes

| Situación | Plazo | Fundamento | Nota |
|---|---|---|---|
| Libros y registros solicitados durante visita | De inmediato | Art. 53 inciso a CFF | Tener contabilidad disponible en el local. |
| Documentos que deba tener el contribuyente, pedidos durante visita | 6 días hábiles | Art. 53 inciso b CFF | |
| Demás casos (revisión de gabinete, requerimientos de información) | 15 días hábiles | Art. 53 inciso c CFF | Caso más común. |
| Ampliación de los plazos del art. 53 | 10 días más | Art. 53, último párrafo CFF | Solo para información difícil de obtener o proporcionar; pedirla por escrito antes del vencimiento; es decisión de la autoridad. |
| Desvirtuar después de la última acta parcial | 20 días hábiles; 15 más si son varios ejercicios y se solicita | Art. 46 fr. IV CFF | Verificar requisitos de la ampliación. |
| Desvirtuar oficio de observaciones (gabinete) | 20 días hábiles; 15 más si son varios ejercicios y se solicita | Art. 48 fr. VI CFF | |
| Revisión electrónica: respuesta a resolución provisional | 15 días hábiles | Art. 53-B CFF | Verificar fracciones vigentes. |
| Requerimiento de obligaciones omitidas | Según oficio | Art. 41 CFF | Verificar plazo vigente. |
| Requerimiento en devolución | 20 días; segundo requerimiento 10 días | Art. 22 CFF | Sin respuesta, desistimiento. |
| Presunción art. 69-B (emisor señalado) | 15 días desde la última notificación | Art. 69-B CFF | Verificar posible plazo adicional. |
| Restricción de CSD | Verificar | Art. 17-H Bis CFF y RMF | Tratar como urgente. |
| Discrepancia fiscal persona física | Verificar | Art. 91 LISR | |
| Plazo de la autoridad para concluir visita o gabinete | 12 meses como regla general | Art. 46-A CFF | Hay excepciones y suspensiones; verificar. |
| Acuerdo conclusivo ante PRODECON | Desde el inicio de facultades y antes de la resolución determinante | Arts. 69-C y siguientes CFF | Suspende plazos de la revisión (verificar alcance). |
| Recurso de revocación | 30 días hábiles desde que surte efectos la resolución | Art. 121 CFF | Fuera de alcance; solo señalar. |
| Juicio contencioso administrativo (nulidad) | 30 días hábiles | Art. 13 LFPCA | Verificar; fuera de alcance. |

## Algoritmo para el agente

1. Identifica el día de notificación (regla del Buzón si aplica).
2. Avanza al siguiente día hábil: surte efectos.
3. Avanza al siguiente día hábil: día 1.
4. Cuenta días hábiles hasta completar el plazo, saltando fines de semana, inhábiles del art. 12 y vacaciones SAT de la RMF.
5. Calcula días hábiles restantes desde hoy (no cuentes hoy si ya pasó el horario hábil o es inhábil).
6. Si procede ampliación, indica la fecha límite para pedirla (último día del plazo original) y, de forma estimada, la nueva fecha; aclara que la autoridad debe confirmarla.
7. Recomienda presentar al menos 1 día hábil antes del vencimiento.

## Salida

| Concepto | Fecha | Base |
|---|---|---|
| Notificación | | regla aplicada |
| Surte efectos | | art. 135 CFF |
| Inicio | | art. 12 CFF |
| Vencimiento | | artículo del plazo |
| Días hábiles restantes | | desde hoy |
| Ampliación | | condición y fecha límite para pedirla |
| Supuestos | | lo que no se pudo confirmar |

## Ejemplo con día inhábil (Buzón sin abrir)

- Aviso enviado jueves 10-sep-2026; no se abrió.
- Tres días hábiles siguientes: vie 11, lun 14, mar 15. Miércoles 16 es inhábil.
- Cuarto día hábil: jue 17-sep-2026, se tiene por notificado.
- Surte efectos: vie 18-sep. Día 1 del plazo: lun 21-sep.
- 15 días hábiles: 21-25 sep (5), 28 sep-2 oct (10), 5-9 oct (15). Vence vie 09-oct-2026.
- Supuesto: regla de notificación del Buzón según texto vigente; verificar.
