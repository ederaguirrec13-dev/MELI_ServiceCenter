# Service Centers Analytics – Caso práctico BI

## Contenido entregado

Este caso práctico incluye:

- Notebook con limpieza, transformación y módulo IA
- Dataset consolidado
- Dashboard desarrollado en Looker Studio
- Documentación del proyecto



## Descripción

Este proyecto tiene como objetivo analizar el proceso de apertura y seguimiento operativo de Service Centers, integrando limpieza y transformación de datos, visualización de indicadores y un módulo de IA para generación automática de insights.

La idea fue construir un flujo completo donde los datos pasan por un proceso de validación, transformación y análisis para convertir información operativa en hallazgos accionables.

---

## Objetivo del ejercicio

Desarrollar una solución que permita:

- Detectar inconsistencias y problemas de calidad de datos.
- Transformar las inconsistencias en datos y corregirlas
- Construir indicadores operativos relevantes.
- Monitorear el avance y riesgos de apertura de los Service Centers a través de tableros
- Generar insights automáticos mediante IA para apoyar la toma de decisiones.

---

## Herramientas utilizadas

- Python
- Pandas
- NumPy
- Jupyter Notebook
- Looker Studio
- OpenAI API
- JSON

---

## Flujo desarrollado

```
Carga de datos
      ↓
Revisión Inicial de datos
      ↓
Limpieza y transformación
      ↓
Validación y calidad
      ↓
Generación de métricas
      ↓
Construcción DataFrame consolidado
      ↓
Exportación del resultado
      ↓
Dashboard operativo
      ↓
Módulo IA para detección de riesgos
```

---

## Entregable 1 – Limpieza y transformación de datos

Durante esta etapa se realizó una revisión y validación de la información para detectar posibles inconsistencias.

Validaciones aplicadas:

- Revisión de porcentajes fuera de rango
- Identificación de valores negativos
- Validación de campos nulos
- Validación de consistencia entre métricas
- Revisión del mix operativo

Posteriormente se aplicaron reglas de limpieza y transformación para construir indicadores adicionales.

Indicadores generados:

- avance_total_pct
- dias_retraso
- cumplimiento_throughput_pct
- ejecucion_capex_pct
- riesgo_apertura
- nivel_avance

---

## Entregable 2 – Dashboard operativo

Se desarrolló un dashboard en Looker Studio enfocado en el seguimiento de apertura y desempeño operativo de los Service Centers.

### Resumen ejecutivo

Permite visualizar rápidamente:

- Total de Service Centers activos
- Avance promedio
- Retrasos críticos
- Riesgo de apertura
- Distribución por estatus

### Detalle operativo

Incluye:

- Detalle por Service Center
- Cumplimiento Throughput
- Ejecución CAPEX
- Alertas y niveles de riesgo
- Observaciones operativas

### Dashboard [Disponible en: https://datastudio.google.com/reporting/1dbe78c7-7367-47b8-92aa-e8ea0a5f8b09]

Resumen Ejecutivo:

![Dashboard Ejecutivo]
![alt text](image.png)

Detalle Operativo:

![alt text](image-1.png)

---

## Entregable 3 – Módulo IA para detección de riesgos

Se implementó un módulo utilizando OpenAI API que recibe un DataFrame consolidado en formato JSON y genera automáticamente:

- Resumen ejecutivo
- Top 3 riesgos operativos
- Recomendaciones de acción
- Priorización de Service Centers

Se agregaron reglas de negocio para reducir falsos positivos:

- Excluir Service Centers con estatus "Operativo"
- Priorizar por score de riesgo
- Validar escenarios de throughput y CAPEX
- Aplicar filtros sobre indicadores inconsistentes

---

## Ejecución del proyecto

Instalar dependencias:

```bash
pip install pandas numpy openai python-dotenv
```

Ejecutar:

```bash
jupyter notebook
```

Abrir:

```text
MELI - ServiceCenters.ipynb
```

---

## Consideraciones

Para el módulo de IA se utiliza OpenAI API mediante variables de entorno.

Crear un archivo:

```text
.env
```

Agregar:

```text
OPENAI_API_KEY=TU_API_KEY
```

En caso de no configurar una API Key, el notebook puede ejecutarse utilizando un modo demostración.

---

## Comentarios finales

Además de generar visualizaciones, el enfoque fue construir un flujo reproducible que permitiera pasar de datos operativos a información útil para toma de decisiones, integrando reglas de negocio y automatización de insights mediante IA.