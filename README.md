# laburo

Mercado laboral tech argentino en tiempo real. Sueldos actualizados, tarifas para freelancers y ayuda para armar CV o propuestas económicas.

## Instalación

```bash
claude --plugin-dir /ruta/a/laburo
```

## Comandos

### `/laburo mercado`

State of the market: sueldos promedio por rol y senioridad, % dolarizado, tendencias.

```
## Mercado IT Argentina — Encuesta Sysarmy 2025.01

**Mediana general IT:** ARS $2.289.000 bruto/mes

| Rol           | Jr          | Semi-Sr     | Sr          |
|---------------|-------------|-------------|-------------|
| Desarrollador | $1.219.000  | $1.900.000  | $2.600.000  |
| DevOps/Infra  | $1.100.000  | $1.800.000  | $2.500.000  |
| Data/ML       | $1.300.000  | $2.100.000  | $3.000.000  |

**Contexto:**
- 64% NO tiene sueldo dolarizado
- 17% trabaja como contractor

Fuente: Encuesta Sysarmy/OpenQube 2025.01 — https://sueldos.openqube.io/encuesta-sueldos-2025.01/
Fecha del dato: enero 2025 (~5.400 participantes)
```

---

### `/laburo tarifa desarrollador senior`

Cuánto cobrar según mercado y modalidad.

```
## Tarifa — Desarrollador Senior

**En relación de dependencia (AR):** ARS $2.600.000 bruto/mes
**Contractor local:** ARS $3.000.000–$3.500.000 / mes
**Remoto internacional:** USD $3.500–$7.000 / mes

💡 Los argentinos que trabajan remoto para el exterior cobran en promedio USD 2.500–5.000/mes.
   Senior especializado puede llegar a USD 7.000/mes.

Fuente: Sysarmy/OpenQube 2025.01 + Infobae/Cronista 2024
Fecha: enero 2025
```

---

### `/laburo cv internacional`

Adaptación del CV para el mercado internacional o remoto.

```
## Sugerencias para tu CV — Mercado internacional

1. **Formato:** resume de 1 página en inglés, sin foto, sin fecha de nacimiento
2. **Stack:** listá tecnologías específicas (no "desarrollo web" sino "React 18, TypeScript, Node.js")
3. **Logros:** cuantificá ("reduje tiempo de build un 40%" no "mejoré el pipeline")
4. **Experiencia remota:** destacá si usaste GitHub, Jira, Notion, Slack con equipos distribuidos
5. **LinkedIn:** URL personalizada, en inglés, mismo contenido que el CV

[El plugin analiza tu CV específico cuando lo pegás en el chat]
```

---

### `/laburo propuesta freelance backend 3 meses startup`

Armado de propuesta económica lista para enviar.

```
## Propuesta — Desarrollo Backend / 3 meses / Startup

**Tarifa mensual:** ARS $3.200.000 (equivalente a ~USD 2.400 al tipo MEP)
**Total proyecto:** ARS $9.600.000

**Estructura de pago:**
- 30% anticipado al inicio: ARS $2.880.000
- 35% al hito 2 (mes 2): ARS $3.360.000
- 35% final a la entrega: ARS $3.360.000

**Ajuste por inflación:** si el proyecto supera 30 días en pesos,
aplicar ajuste mensual por IPC publicado por INDEC.

**Fuera de scope:** deploys a producción, soporte post-entrega, cambios de requerimientos.

[El plugin personaliza la propuesta según tu contexto específico]
```

---

## Fuentes

- [Encuesta de Sueldos Sysarmy/OpenQube](https://sueldos.openqube.io) — publicación semestral
- [Sysarmy Blog](https://sysarmy.com/blog) — análisis y novedades
- [Infobae: sueldos remotos Argentina](https://www.infobae.com/economia/2024/09/15/los-argentinos-que-trabajan-para-el-exterior-ganan-entre-2500-y-5000-dolares-por-mes/)
