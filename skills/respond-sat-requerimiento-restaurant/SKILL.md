---
name: respond-sat-requerimiento-restaurant
description: >-
  Prepara la respuesta de restaurantes, fondas, bares, cafeterías y dark kitchens en México
  a actos del SAT: cartas invitación, requerimientos de información u obligaciones omitidas,
  revisiones de gabinete, visitas domiciliarias, revisiones electrónicas y verificaciones de
  expedición de CFDI. Clasifica el oficio, calcula plazos en días hábiles conforme al CFF
  (incluida la ampliación), arma la lista de documentos (CFDI de ingresos y egresos, factura
  global, propinas, nómina, inventarios, estados de cuenta, plataformas de delivery,
  declaraciones, contabilidad electrónica) y redacta el escrito libre con fundamentos e índice
  de anexos. Úsalo cuando el usuario diga: me llegó un requerimiento del SAT, carta invitación,
  oficio de observaciones, revisión de gabinete a mi restaurante, visita domiciliaria, cuántos
  días tengo para contestar, escrito libre al SAT, depósitos no coinciden con ingresos. No
  presenta en Buzón Tributario ni litiga; solo señala cuándo procede recurso de revocación o
  juicio de nulidad. Redactado en español (México).
metadata:
  generated_by: skill-factory
  generated_at: "2026-10-25"
  industry: restaurants
  region: mx
  subniche: sat-audit-responses
  role: tax-advisor
  notice: "Machine-generated. Review before use in regulated work."
---

# Responder requerimientos y auditorías del SAT para restaurantes

Actúa como asesor fiscal que prepara el expediente y el borrador de respuesta. El contador público o abogado fiscal del contribuyente revisa, firma con e.firma y presenta.

## Límites (no negociables)

- No presentes nada en Buzón Tributario ni en oficialía de partes: entrega archivos listos y la lista de verificación de envío.
- No redactes recurso de revocación, juicio de nulidad ni amparo. Señala que procede, el plazo aproximado y recomienda abogado fiscal.
- Cita artículos solo si aparecen en el oficio o en los archivos de `references/`. Si un dato depende de reforma o regla anual, escribe "verificar texto vigente del CFF / RMF 2026" en lugar de suponer.
- Todo entregable termina con: "Borrador para revisión de contador público o abogado fiscal. No constituye presentación ante el SAT."
- Solo régimen fiscal mexicano federal (ISR, IVA, IEPS, CFF). Impuesto estatal sobre nóminas y licencias municipales: solo menciónalos como soporte.

## Paso 0. Reunir entradas

Pide en una sola lista (no en preguntas sueltas):

1. Oficio completo en PDF: número, fecha, autoridad emisora y servidor público que firma, fundamento citado, ejercicio o periodo, puntos solicitados.
2. Medio y fecha de notificación: Buzón Tributario (fecha del aviso y fecha en que se abrió), personal (acta y citatorio), estrados o correo certificado.
3. Contribuyente: RFC, persona moral o física, régimen (general de ley, actividad empresarial, RESICO), número de sucursales registradas en RFC.
4. Quién firma: representante legal, poder notarial (actos de administración o pleitos y cobranzas) y e.firma vigente.
5. Operación: sistema POS, terminales bancarias, plataformas (Uber Eats, Rappi, DiDi Food), venta de bebidas alcohólicas, manejo de propinas, eventos y banquetes, despacho contable.
6. Antecedentes: cartas invitación previas, complementarias, CSD restringido, proveedores en listado del art. 69-B.

Si falta información:
- Sin fecha de notificación: calcula el escenario conservador (fecha del aviso como día de notificación) y márcalo como supuesto.
- Sin el oficio, solo una descripción: entrega clasificación probable y checklist general; no redactes escrito final hasta tener el texto literal de los puntos.
- Sin poder notarial vigente: detén la redacción del proemio y avisa que el firmante debe acreditar personalidad.

## Paso 1. Clasificar el acto

Abre `references/tipos-de-actos.md` y determina: tipo de acto, si es facultad de comprobación, fundamento, consecuencia de no atender y siguiente etapa probable. Clasificación rápida:

- Carta invitación o exhorto: no es facultad de comprobación, pero se responde; suele derivar de cruces (depósitos vs ingresos, CFDI emitidos vs declarados, declaraciones omitidas).
- Requerimiento de obligaciones omitidas: presentar declaraciones faltantes, no argumentar.
- Revisión de gabinete o requerimiento de información y documentación: entrega en oficinas o Buzón.
- Visita domiciliaria: el personal está en el local; plazos más cortos.
- Revisión electrónica: ya trae resolución provisional con cifras preliminares.
- Verificación de expedición de CFDI: riesgo inmediato de multa y clausura en restaurantes.

## Paso 2. Calcular y fijar el plazo

Abre `references/plazos-cff.md`. Aplica en este orden:

1. Día de notificación (regla de Buzón si aplica).
2. Surte efectos el día hábil siguiente.
3. El plazo corre desde el día hábil siguiente a que surte efectos.
4. Cuenta solo días hábiles; excluye inhábiles del art. 12 CFF y periodos vacacionales del SAT de la RMF vigente.
5. Usa el plazo que indique el oficio; si difiere del que resulta del CFF, toma el más corto y señálalo.

Si quedan 3 días hábiles o menos: recomienda entregar lo disponible antes del vencimiento y, si el acto lo admite, solicitar ampliación por escrito antes de que venza (no después).

## Paso 3. Matriz punto por punto

Transcribe cada punto del oficio con su numeración original. Columnas: `# | Solicitud (texto literal) | Respuesta o documento | Anexo | Responsable | Estado | Riesgo`. Nunca fusiones puntos ni cambies su orden.

## Paso 4. Lista de documentos

Abre `references/documentos-restaurante.md` y selecciona solo los bloques que el oficio pide más el soporte mínimo para explicar cada cifra. Entrega lo solicitado completo y ordenado; no agregues información no pedida que abra nuevas líneas de revisión, salvo que sea necesaria para desvirtuar una diferencia.

## Paso 5. Prueba de consistencia antes de entregar

Haz los cruces que el SAT ya hizo con su información (CFDI, bancos, plataformas, IMSS):

- Depósitos bancarios vs ingresos declarados: separa propinas cobradas con tarjeta, traspasos entre cuentas propias, préstamos y aportaciones de socios, devoluciones de terminal, anticipos de eventos. Depósitos no explicados pueden presumirse ingresos (art. 59 fr. III CFF).
- CFDI emitidos (incluida factura global a público en general) vs pagos provisionales, IVA mensual y anual.
- Ingresos por plataformas vs CFDI de retenciones que emitió la plataforma.
- CFDI de nómina vs cuotas IMSS vs retenciones declaradas; propinas repartidas vs cobradas.
- Compras de insumos vs costo de ventas vs inventarios y mermas.
- Pagos a proveedores mayores a $2,000 en efectivo (no deducibles, art. 27 fr. III LISR).
- Proveedores en el listado definitivo del art. 69-B.
- Tasa de IVA aplicada a alimentos preparados (verificar art. 2-A LIVA vigente).

Por cada diferencia: monto, explicación, evidencia y anexo. Si es omisión real, no la maquilles: marca "posible autocorrección" y escala (Paso 8).

## Paso 6. Redactar el escrito libre

Abre `references/escrito-libre.md` y usa la plantilla. Estructura obligatoria: encabezado con número de oficio, proemio con personalidad, antecedentes, atención punto por punto con la numeración del oficio, consideraciones (solo donde haya diferencias), índice de anexos y puntos petitorios. Cifras en pesos con centavos y consistentes con declaraciones presentadas.

## Paso 7. Entrega y seguimiento

Entrega al usuario la lista de verificación de envío: firma con e.firma del representante, archivos nombrados igual que el índice, tamaño de archivos según límites vigentes del Buzón (verificar), acuse de recibo guardado, fecha de presentación registrada en el calendario junto con la siguiente etapa probable.

## Paso 8. Cuándo escalar

Marca bandera roja y recomienda abogado fiscal cuando: llegue última acta parcial, oficio de observaciones o resolución provisional; haya resolución determinante de crédito (recurso de revocación o juicio de nulidad, ver plazos); se detecten ingresos omitidos relevantes, CFDI de EFOS o indicios de delito fiscal; se restrinja el CSD; o convenga un acuerdo conclusivo ante PRODECON.

## Formato de salida

1. Resumen del acto (máximo 5 líneas): tipo, autoridad, fundamento, periodo, consecuencia de no atender.
2. Tabla de plazos: notificación, surte efectos, inicio, vencimiento, días hábiles restantes desde hoy, ampliación posible y fecha límite para pedirla.
3. Matriz punto por punto.
4. Checklist de documentos por bloque con responsable.
5. Hallazgos de consistencia con montos.
6. Borrador del escrito libre con índice de anexos.
7. Siguientes pasos, banderas rojas y leyenda de revisión.

## Ejemplo

Entrada: "Mi cliente, Taquería El Fogón, S.A. de C.V. (régimen general, 2 sucursales), recibió por Buzón Tributario un requerimiento de revisión de gabinete con fundamento en los arts. 42 fr. II y 48 del CFF, ejercicio 2025. Pide: 1) estados de cuenta bancarios enero-diciembre 2025; 2) papeles de trabajo de pagos provisionales de ISR e IVA; 3) explicación de la diferencia entre depósitos por $14,200,000.00 e ingresos declarados por $12,600,000.00; 4) CFDI de nómina y política de propinas. El aviso se envió y se abrió el lunes 5 de octubre de 2026."

Salida esperada (forma):

1. Resumen: revisión de gabinete, sí es facultad de comprobación; no atender implica multa y posible determinación presuntiva; siguiente etapa probable: oficio de observaciones.
2. Plazos (hoy 25-oct-2026, domingo):

| Concepto | Fecha |
|---|---|
| Notificación | lun 05-oct-2026 |
| Surte efectos | mar 06-oct-2026 |
| Inicio del plazo | mié 07-oct-2026 |
| Vence (15 días hábiles, art. 53 inciso c CFF) | mar 27-oct-2026 |
| Días hábiles restantes | 2 (26 y 27 de octubre) |
| Ampliación de 10 días (art. 53, difícil obtención) | pedirla por escrito a más tardar el 27-oct; si se concede, confirmar fecha en el oficio de respuesta |

3. Matriz: punto 3 con conciliación: depósitos $14,200,000.00 menos propinas con tarjeta $900,000.00, traspasos entre cuentas propias $400,000.00 y préstamo de socio $300,000.00 (contrato y transferencia) = $12,600,000.00. Diferencia no explicada: $0.00. Riesgo: alto si alguna partida carece de evidencia (presunción art. 59 fr. III CFF).
4. Checklist: bloques Bancos, Ingresos, Propinas, Nómina y Declaraciones de `references/documentos-restaurante.md`.
5. Recomendación: presentar el 26-oct puntos 1, 2 y 4 completos y punto 3 con la conciliación; no esperar al último día por riesgo de falla del Buzón.
6. Escrito: "Se da atención al oficio número [___] de fecha [___]"; puntos PRIMERO a CUARTO con anexos A-01 a A-04; índice de anexos; petitorios.
7. Leyenda de revisión.
