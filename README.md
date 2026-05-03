# laburo

Plugin para Claude Code sobre el mercado laboral argentino.

Cualquier trabajador —registrado, informal, monotributista o desempleado— puede consultar sueldos, paritarias, tarifas para independientes y consejos para armar su CV.

## Instalación

```bash
claude --plugin-dir /ruta/a/laburo
```

## Comandos

### `/laburo sueldo [sector o rol]`

Consulta el SMVM, el Índice de Salarios del INDEC y los últimos acuerdos paritarios para el sector indicado.

---

### `/laburo freelo [servicio]`

Ayuda a trabajadores independientes a calcular su valor hora y determinar la categoría de Monotributo correspondiente.

---

### `/laburo cv [sector objetivo]`

Guía para armar o mejorar el currículum vitae según los estándares del mercado laboral argentino.

---

## Ejemplos de uso

### Consultar el Salario Mínimo

**Usuario:** "¿A cuánto está el salario mínimo hoy?"

**Claude:**
```
El Salario Mínimo, Vital y Móvil (SMVM) en Argentina es de $262.432/mes (valor vigente a enero 2025).

Fuente: Consejo del Salario — argentina.gob.ar
```

---

### Paritarias de Comercio

**Usuario:** "¿Cuánto tiene que ganar un administrativo de comercio?"

**Claude:**
```
## Sueldo — Administrativo de Comercio

**SMVM vigente:** $262.432/mes
**Básico de convenio (FAECYS):** ~$650.000 bruto/mes (Administrativo A)
**Sueldo de bolsillo estimado:** ~$490.000-520.000/mes

**Último acuerdo paritario:** +15% a partir de marzo 2024 + suma no remunerativa

Fuente: Secretaría de Trabajo / FAECYS — argentina.gob.ar
Dato al: marzo 2024
```

---

### Tarifa para gasista matriculado

**Usuario:** "Soy gasista matriculado. ¿Cuánto debería cobrar por hora?"

**Claude:**
```
## Tarifa — Trabajador Independiente (Gasista Matriculado)

Contame tus gastos fijos mensuales (alquiler, herramientas, movilidad) y cuántas horas facturables tenés por mes para calcular tu tarifa exacta.

Como referencia inicial para un gasista en AMBA (2024):
- Valor hora de mano de obra: $8.000–$12.000/hora
- Los materiales se presupuestan aparte
- Anticipo recomendado: 50% para trabajos de más de 4 horas

Fuente: AFIP Monotributo — afip.gob.ar
```

---

### Ayuda con CV para buscar laburo de cajero

**Usuario:** "Ayudame a armar mi CV para buscar laburo de cajero"

**Claude:**
```
Claro. Para un perfil de atención al cliente en Argentina, tu CV debe seguir este orden:

✅ Datos de contacto: nombre, teléfono, email, localidad (sin DNI ni CUIL)
✅ Perfil: "Cajero con experiencia en manejo de valores y posnet"
✅ Experiencia: del más reciente al más antiguo
✅ Formación: secundario completo (o en curso)

Qué NO incluir: foto, estado civil, DNI, ni referencias de familiares.

Tip: En Argentina se valora que el CV no supere las 2 páginas. Guardalo en PDF.

Fuente: Portal Empleo — portalempleo.gob.ar
```

---

### Ayuda con CV para docente

**Usuario:** "Necesito actualizar mi CV para presentarme a un cargo docente"

**Claude:**
```
Para un perfil docente en Argentina, el CV debe incluir:

✅ Datos personales: nombre, DNI, domicilio, teléfono, email
✅ Título docente: carrera, institución, año de egreso y resolución de validez
✅ Antigüedad: años frente al aula por nivel y jurisdicción
✅ Capacitaciones: cursos con puntaje reconocido por el Ministerio
✅ Disponibilidad horaria y geográfica

Qué se valora: puntaje docente acumulado, cargos jerárquicos, publicaciones o proyectos institucionales.

Fuente: Portal Empleo — portalempleo.gob.ar
```

---

## Fuentes

- [Ministerio de Trabajo — argentina.gob.ar](https://www.argentina.gob.ar/trabajo)
- [INDEC — Índice de Salarios](https://www.indec.gob.ar/indec/web/Nivel4-Tema-4-31-61)
- [Portal Empleo — portalempleo.gob.ar](https://www.portalempleo.gob.ar)
- [AFIP Monotributo — afip.gob.ar](https://www.afip.gob.ar/monotributo/categorias.asp)
- [Consejo del Salario — argentina.gob.ar](https://www.argentina.gob.ar/trabajo/consejosalario)
