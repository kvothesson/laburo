# laburo

Plugin para Claude Code sobre el mercado laboral argentino.

Cualquier trabajador —registrado, informal, monotributista o desempleado— puede consultar sueldos, paritarias, tarifas para independientes y consejos para armar su CV.

## Instalación

```bash
claude --plugin-dir /ruta/a/laburo
```

### OpenAI Codex

No requiere instalación. Codex lee `AGENTS.md` automáticamente al abrirse en este directorio.

```bash
git clone https://github.com/kvothesson/laburo ~/laburo
cd ~/laburo
codex
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

### Salario Mínimo Vital y Móvil

**Usuario:** "¿A cuánto está el salario mínimo hoy?"

**Claude:**
```
El Salario Mínimo, Vital y Móvil (SMVM) en Argentina es de $334.800/mes (dic 2025).
Para trabajadores jornalizados: $1.642/hora.

Fuente: Consejo del Salario — argentina.gob.ar
Dato al: diciembre 2025
```

---

### Paritarias de comercio

**Usuario:** "¿Cuánto tiene que ganar un administrativo de comercio?"

**Claude:**
```
## Sueldo — Administrativo de Comercio

SMVM vigente: $334.800/mes
Básico de convenio (FAECYS): ~$650.000 bruto/mes (Administrativo A)
Sueldo de bolsillo estimado: ~$490.000–520.000/mes

Último acuerdo paritario: +15% a partir de marzo 2024 + suma no remunerativa

Fuente: Secretaría de Trabajo / FAECYS — argentina.gob.ar
Dato al: marzo 2024
```

---

### Paritarias gastronómicas

**Usuario:** "¿Cuánto gana un mozo?"

**Claude:**
```
## Sueldo — Mozo / Gastronómico

SMVM vigente: $334.800/mes
Básico de convenio (UTHGRA): desde ~$939.463/mes (Categoría D, nivel inicial)
Categorías superiores (cocinero, recepcionista): $1.000.000–$1.145.000/mes
Sueldo de bolsillo estimado: ~$700.000–850.000/mes

Último acuerdo paritario (UTHGRA-FEHGRA):
  Vigencia: junio 2025 – mayo 2026
  Aumentos escalonados en 7 cuotas + sumas no remunerativas
  Las sumas se incorporan al básico en febrero 2026

💡 Las propinas no están en estos montos pero son parte real del ingreso.

Fuente: UTHGRA — uthgra.org.ar
Dato al: abril 2026
```

---

### Paritarias metalúrgicas

**Usuario:** "Soy operario metalúrgico, ¿cuánto debería ganar?"

**Claude:**
```
## Sueldo — Operario Metalúrgico (UOM)

SMVM vigente: $334.800/mes
Ingreso Mínimo Global de Referencia (IMGR): $1.016.008/mes (feb 2026)
  (incluye remunerativos + no remunerativos, sin horas extras)
Sueldo de bolsillo estimado: ~$750.000–820.000/mes

Último acuerdo paritario (UOM):
  Homologado el 04/02/2026 — Disposición 207/2026
  Cronograma oct 2025 – abr 2026: +4,2% remunerativo
  + sumas fijas no remunerativas mensuales ($15.000–$35.000)

⚠️ El básico varía según rama. Consultá tu seccional UOM.

Fuente: UOM — uom.org.ar / Boletín Oficial Disposición 207/2026
Dato al: febrero 2026
```

---

### Tarifa para trabajadora independiente

**Usuario:** "Soy diseñadora gráfica independiente, ¿cuánto cobro por hora?"

**Claude:**
```
## Tarifa — Diseñadora Gráfica Independiente

Con valores típicos de AMBA (Monotributo activo, 2026):

  Gastos fijos:              $250.000/mes
  Aportes Monotributo (Cat. D): ~$95.000/mes
  Ganancia objetivo:         $600.000/mes
  ──────────────────────────────────────
  Total necesario:           $945.000/mes
  Horas facturables:         80 hs/mes
  ──────────────────────────────────────
  Valor hora mínimo:         $11.813 → redondeá a $12.000–$13.000

Categoría Monotributo estimada: D (hasta $3.887.000 facturación anual — servicios)
Cuota mensual: ~$95.000

Para presupuestar un proyecto:
  - Materiales/licencias: separar del valor hora
  - Imprevistos: +15% sobre el total
  - Anticipo: 30–50% antes de arrancar

Fuente: AFIP Monotributo — afip.gob.ar
Dato al: mayo 2026
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

Se valora: puntaje docente acumulado, cargos jerárquicos, proyectos institucionales.
Qué NO incluir: foto, estado civil, referencias de familiares.

Fuente: Portal Empleo — portalempleo.gob.ar
```

---

## Fuentes

- [Ministerio de Trabajo — argentina.gob.ar](https://www.argentina.gob.ar/trabajo)
- [INDEC — Índice de Salarios](https://www.indec.gob.ar/indec/web/Nivel4-Tema-4-31-61)
- [Portal Empleo — portalempleo.gob.ar](https://www.portalempleo.gob.ar)
- [AFIP Monotributo — afip.gob.ar](https://www.afip.gob.ar/monotributo/categorias.asp)
- [Consejo del Salario — argentina.gob.ar](https://www.argentina.gob.ar/trabajo/consejodelsalario)
- [UTHGRA — uthgra.org.ar](https://uthgra.org.ar)
- [UOM — uom.org.ar](https://uom.org.ar)
