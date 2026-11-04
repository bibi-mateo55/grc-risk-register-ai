---
name: registro-riesgos
description: Convierte un escenario o caso de ciberseguridad en un registro de riesgos estructurado (estilo ISO 27005). Usar siempre que el usuario pida analizar riesgos, crear un risk register, evaluar amenazas o vulnerabilidades de una organizacion, aunque no diga explicitamente "registro de riesgos".
---

# Registro de riesgos

Cuando se active, produce siempre:

1. **Contexto** en 2 frases: organizacion y activos criticos.
2. **Tabla de riesgos** con columnas: ID | Amenaza | Vulnerabilidad | Activo | Probabilidad (1-5) | Impacto (1-5) | Nivel (P x I) | Tratamiento (mitigar/transferir/aceptar/evitar) | Control propuesto
3. Ordena la tabla de mayor a menor nivel.
4. **Top 3 prioridades** con una recomendacion accionable cada una.
5. Si falta informacion clave, indica los supuestos al final.

Idioma: responde en el idioma del usuario.
