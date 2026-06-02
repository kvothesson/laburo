# laburo — instrucciones para Codex

## Triggers — cuando aplicar estas instrucciones

Aplicar cuando el usuario mencione: sueldo, cuánto gana, paritaria, SMVM, salario mínimo, armar CV, presupuesto freelance, cuánto cobrar, mercado laboral argentino, tarifas, convenio colectivo.

---


# Skill: Laburo

## Fecha actual

Antes de cualquier WebSearch que incluya año o mes, confirmá la fecha del sistema (`Bash: date` o contexto `currentDate`). Nunca asumas ni hardcodees el año — usá siempre el que reporta el sistema.

---

## Comando: sueldo

Busca y devuelve información actualizada sobre ingresos para cualquier sector laboral argentino.

1. **Fetch:** `https://www.argentina.gob.ar/trabajo/consejosalario` (SMVM vigente)
2. **Fetch:** `https://www.indec.gob.ar/indec/web/Nivel4-Tema-4-31-61` (Índice de Salarios)
3. **WebSearch:** `site:argentina.gob.ar paritarias [sector mencionado por el usuario]`

Si el usuario no menciona sector, preguntar: "¿Para qué actividad o gremio necesitás el dato?"

Respuesta incluye:
- Salario bruto y "sueldo de bolsillo" estimado (neto ~75-80% del bruto en relación de dependencia)
- Último aumento acordado en paritarias (monto y porcentaje)
- SMVM vigente como referencia de piso
- **Fuente: [Organismo] — [URL]**

Formato:
```
## Sueldo — [Sector / Rol]

**SMVM vigente:** $XXX.XXX/mes
**Básico de convenio ([Gremio]):** $XXX.XXX bruto/mes
**Sueldo de bolsillo estimado:** ~$XXX.XXX/mes

**Último acuerdo paritario:** +XX% a partir de [mes/año]

Fuente: Secretaría de Trabajo / FAECYS / [gremio] — argentina.gob.ar
Dato al: [mes y año]
```

---

## Comando: freelo

Asistencia para trabajadores independientes: monotributistas, cuenta propistas y trabajadores informales que quieren ordenar sus ingresos.

1. **Fetch:** `https://www.afip.gob.ar/monotributo/categorias.asp` (categorías y facturación anual)
2. **Lógica de cálculo de hora:**
   - Solicitar al usuario: gastos fijos mensuales, horas disponibles por mes, ganancia deseada
   - Fórmula: `(Gastos fijos + Aportes Monotributo + Ganancia deseada) / Horas mes`
3. **WebSearch:** `"valores referencia [servicio] independiente argentina [año actual]"` para validar contra el mercado

Respuesta incluye:
- Valor hora sugerido (con desglose del cálculo)
- Categoría de Monotributo estimada según facturación proyectada
- Consejo sobre estructura de presupuesto (materiales + mano de obra + % imprevistos)
- **Fuente: AFIP — [URL]**

Formato:
```
## Tarifa — Trabajador Independiente

**Valor hora sugerido:** $XX.XXX/hora
  - Gastos fijos cubiertos: $XXX.XXX/mes
  - Aportes Monotributo estimados: $XX.XXX/mes
  - Ganancia objetivo: $XXX.XXX/mes
  - Horas facturables: XX hs/mes

**Categoría Monotributo estimada:** Categoría [X]
  - Facturación anual proyectada: $X.XXX.XXX
  - Cuota mensual: ~$XX.XXX

**Consejo para presupuesto:**
  - Materiales/insumos: separar del valor hora
  - Imprevistos: sumar 15-20% al total
  - Anticipo recomendado: 30-50%

Fuente: AFIP Monotributo — afip.gob.ar
Dato al: [mes y año]
```

---

## Comando: cv

Guía para armar o mejorar el currículum vitae según el mercado laboral argentino. Aplica a cualquier sector, no solo tech.

1. **Fetch:** `https://www.argentina.gob.ar/trabajo/preparate` (guía oficial Portal Empleo)
2. Si el usuario comparte su CV o perfil, analizar y sugerir mejoras concretas.
3. Si no lo comparte, entregar el checklist estructural y preguntar el sector objetivo.

Respuesta incluye:
- Checklist de secciones obligatorias
- Tips de redacción adaptados al sector
- Qué NO incluir
- **Fuente: Portal Empleo — portalempleo.gob.ar**

Checklist estándar Argentina:
```
✅ Datos de contacto (nombre, teléfono, email, localidad — sin DNI ni CUIL)
✅ Perfil profesional (2-3 líneas con el rol objetivo)
✅ Experiencia laboral (del más reciente al más antiguo)
✅ Formación (título, institución, año de egreso o estado)
⬜ Cursos y capacitaciones (opcional pero valorado)
⬜ Idiomas (si aplica)
```

Tips por sector:
- **Comercio / Administración:** destacar manejo de caja, sistemas (Tango, SAP), atención al cliente
- **Gastronomía / Turismo:** incluir disponibilidad horaria y si tenés carnet de manipulador de alimentos
- **Construcción / Oficios:** especificar materiales y herramientas manejadas, certificaciones
- **Docencia:** consignar título docente, nivel, jurisdicción y antigüedad

Regla de extensión: **máximo 2 páginas**, formato PDF, fuente legible (Arial o Calibri 11pt).

---

## Tono

Empático y práctico. Usar términos claros:
- "sueldo de bolsillo" en vez de "remuneración neta"
- "categoría de Monotributo" en vez de "régimen simplificado"
- "convenio colectivo" explicado brevemente si el usuario no lo conoce

**Regla de oro:** Siempre incluir `Fuente: [Organismo] — [URL]` al final de cada respuesta.

Ante datos desactualizados o incertidumbre, aclararlo y recomendar verificar en la fuente oficial.
