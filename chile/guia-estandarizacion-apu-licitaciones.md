# Estándar de Datos: Análisis de Precios Unitarios (APU) en Edificación e Industria

Este repositorio contiene la guía técnica para la estandarización de bases de datos de **Análisis de Precios Unitarios (APU)**, siguiendo las directrices de la **NCh 1156 (Cubicaciones)** y las exigencias de la **LGUC (Ley General de Urbanismo y Construcciones)**.

## 1. El Problema: Datos No Estructurados
En la mayoría de los estudios de licitación (privados o públicos), la fragmentación de la información de costos genera:
- Inconsistencias entre la oferta detallada y el presupuesto resumen.
- Omisión de leyes sociales (imposiciones) en el cálculo de mano de obra.
- Desviaciones en el rendimiento de maquinaria por falta de desglose de combustible y lubricantes.

## 2. Estandarización bajo NCh 1156
Para garantizar la integridad de una licitación, cada partida debe descomponerse en una estructura jerárquica:

### Estructura de Insumo (Maestro de Precios)
| Campo | Tipo | Norma / Referencia |
| :--- | :--- | :--- |
| `ID_INSUMO` | Alfanumérico | Código interno único |
| `DESCRIPCION` | Texto | Según Glosario LGUC |
| `UNIDAD` | Enum | SI (Sistema Internacional) |
| `CATEGORIA` | Enum | Material / Mano de Obra / Equipo / Subcontrato |
| `PRECIO_NETO` | Decimal | Precio base sin IVA |

### Lógica de Cálculo del APU
Un APU robusto no es solo una suma; es un algoritmo de rendimiento:
`Costo_Partida = (Σ Rendimiento_Insumo * Precio_Insumo) * (1 + % Perdición)`

## 3. Implementación Forense
La estandarización permite auditar la oferta automáticamente. Si los datos no siguen esta estructura, el riesgo de rechazo por "falta de integridad" en las bases administrativas es crítico.

Para profundizar en la implementación técnica de estos desgloses y asegurar que tu oferta sea financieramente viable, consulta:  
👉 **[Guía Completa de Análisis APU y Costos Directos](https://www.sepo.cl/apu-construccion.html)**

---
*Este recurso es parte de la iniciativa de SEPO para la profesionalización de la ingeniería de costos en Chile.*
