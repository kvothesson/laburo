---
description: Mercado laboral tech argentino en tiempo real — sueldos, tarifas, CV y propuestas. Usar cuando el usuario pregunta cuanto cobrar, como armar un CV o una propuesta económica para el mercado argentino o remoto.
---

## Comandos

### `/laburo mercado`

Hace WebSearch con la query:
`"encuesta sueldos sysarmy openqube [año actual] resultados tech argentina"`

Presenta el estado del mercado:
- Mediana general IT
- Sueldos por rol: desarrolladores, DevOps, Data, QA, diseñadores
- Sueldos por senioridad: Jr / Semi-Sr / Sr
- % con sueldo dolarizado
- % trabajando como contractor
- Tendencias destacadas

Fallback si WebSearch falla: usar la URL directa `https://sysarmy.com/blog` y buscar el post más reciente de encuesta de sueldos.

Formato de respuesta:
```
## Mercado IT Argentina — [periodo de la encuesta]

**Mediana general IT:** ARS $X.XXX.XXX bruto/mes

| Rol           | Jr        | Semi-Sr   | Sr        |
|---------------|-----------|-----------|-----------|
| Desarrollador | $X.XXX.XXX | $X.XXX.XXX | $X.XXX.XXX |
| DevOps/Infra  | ...       | ...       | ...       |
| Data/ML       | ...       | ...       | ...       |

**Contexto:**
- X% tiene sueldo dolarizado
- X% trabaja como contractor

Fuente: Encuesta Sysarmy/OpenQube [periodo] — https://sueldos.openqube.io
Fecha del dato: [fecha de publicación]
```

---

### `/laburo tarifa [rol] [senioridad]`

Hace WebSearch con:
`"sueldo [rol] [senioridad] argentina [año actual] pesos dolares remoto"`

Y también:
`"[rol] [senioridad] argentina remoto exterior usd freelance [año actual]"`

Presenta tres escenarios:
1. Relación de dependencia local (ARS)
2. Contractor en empresa argentina (ARS/USD)
3. Remoto internacional (USD)

Formato:
```
## Tarifa — [Rol] [Senioridad]

**En relación de dependencia (AR):** ARS $X.XXX.XXX bruto/mes
**Contractor local:** ARS $X.XXX.XXX / mes (equivalente a ~USD X.XXX)
**Remoto internacional:** USD $X.XXX–$X.XXX / mes

💡 Para [Rol] [Senioridad], el percentil 75 en AR está en $X.XXX.XXX.
El mercado internacional paga entre X–X veces más para el mismo rol.

Fuente: Sysarmy/OpenQube + búsqueda de mercado
Fecha: [mes y año]
```

Fallback: WebSearch a `site:glassdoor.com.ar [rol] argentina` o `site:coderhouse.com sueldos [rol] argentina`.

---

### `/laburo cv [objetivo]`

El objetivo puede ser "empresa local", "startup argentina", "empresa internacional", "trabajo remoto", u otro texto libre.

Pedí al usuario que comparta el CV en texto o los puntos principales de su experiencia si no los compartió aún.

Luego sugerí adaptaciones concretas según el objetivo:

**Para empresa local / startup AR:**
- Destacar stack técnico específico (no genérico)
- Incluir proyectos con impacto medible en ARS o usuarios
- Formato: 1 página, en español, sin foto

**Para empresa internacional / remoto:**
- Traducir a inglés (o spanglish según empresa)
- Formato: resume de 1 página, en inglés, sin foto, sin fecha de nacimiento ni DNI
- Destacar experiencia con equipos remotos, async, y herramientas globales (GitHub, Jira, Slack)
- Cuantificar logros en métricas (usuarios, uptime, reducción de tiempo, etc.)

Respondé con sugerencias puntuales sobre el CV del usuario, no con un template genérico.

---

### `/laburo propuesta [contexto]`

El contexto puede incluir: tipo de proyecto, duración estimada, cliente (empresa local, startup, internacional), si es por hora o por proyecto, senioridad.

Pedí los datos que falten si el contexto es incompleto.

Armar la propuesta con:
1. **Tarifa base:** calculada con `/laburo tarifa` para el rol/senioridad implícito
2. **Estructura del proyecto:** fases, entregables, hitos
3. **Condiciones de pago:** anticipo recomendado (30-50%), hitos, forma de pago
4. **Cláusulas clave:** revisiones incluidas, fuera de scope, propiedad intelectual
5. **Ajuste por inflación** si el proyecto es en pesos y dura más de 30 días

Formato: propuesta lista para copiar y enviar, en tono profesional pero directo.

---

## Tono

- Directo, sin paja institucional
- Números concretos, no rangos vagos
- Si el mercado está raro (inflación alta, dólar inestable), decirlo
- No dar consejos de vida, solo datos accionables
- Si hay incertidumbre en los datos, aclararlo y dar la fuente
