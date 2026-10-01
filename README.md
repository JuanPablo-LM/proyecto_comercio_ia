# Identificación del comercio potencial y diversificación exportadora para productos No minero-energéticos de Colombia.

**Título del Proyecto:**  

**Integrantes:**  

* Andrés Felipe Linares

* Juan Esteban Roa

* Juan Pablo Lozano 

## 1. Definición del Problema y Objetivos

- **Objetivo General:** Identificar qué productos colombianos **no minero-energéticos** tienen potencial exportador, identificando los productos y países de destino.
- **Descripción del Problema:** Históricamente en Colombia las exportaciones han estado muy concentradas en el sector extractivo o minero-energético. Sin embargo, en Colombia se ha intentado diversificar la canasta exportadora, tratando de identificar potencial exportador, tanto en productos alternativos, como en principales mercados para estos productos.  
- **Entrega de Valor:** Será identificar las combinaciones producto-país con mayor oportunidad de exportación, que sirva como insumo para orientar decisiones de política comercial, promoción de exportaciones y priorización empresarial.


---

## 2. Análisis de Stakeholders

- **Decisor:** Entidades de política comercial y promoción de exportaciones alternativas y gremios exportadores
- **Afectados:** Empresas exportadoras actuales y potenciales, productores de bienes no minero-energéticos, regiones económicas dependientes de la diversificación exportadora.


---

## 3. Estrategia Técnica

- **Técnicas a utilizar:** Un modelo gravitacional de comercio, para identificar el comercio esperado entre países. Adicionalmente, modelos de machine learning para confirmar si las oportunidades identificadas son consistentes.
- **Desafíos Identificados:**
  * El modelo posiblemente no pueda identificarse para productos y países para los cuales el comercio es nulo.
  * Si cambian condiciones estructurales comerciales, es muy difícil hacer un cálculo preciso.


---

## 4. Datos y Variables

- **Fuentes de Datos:**
* DIAN/DANE (comercio exterior colombiano)
* CEPII Gravity Dataset (distancia, acuerdos comerciales)
* Banco de la República (tipo de cambio).
- **Descripción del Dataset:** 
## Variables del panel

El panel está organizado a nivel país socio-año (2017-2024), con Colombia
como referencia fija. Las variables se agrupan en tres bloques:

### Comercio (BACI, CEPII)

- X_Total: Exportaciones de Colombia a sus socios, en USD constantes.
- M_Total: Importaciones de Colombia desde sus socios, en USD constantes.
- X_Fuels: Exportaciones de combustibles (capítulo HS 27) de Colombia a sus socios.
- M_Fuels: Importaciones de combustibles de Colombia desde sus socios.
- X_NoComb: Exportaciones no minero-energéticas de Colombia a sus socios.
  Variable objetivo principal del modelo.
- M_NoComb: Importaciones no minero-energéticas de Colombia desde sus socios.

### Comercio por producto (UN Comtrade, nivel HS6)

- hs6: Código de producto a 6 dígitos del Sistema Armonizado (HS).
- hs6_name: Descripción del producto correspondiente al código HS6.
- hs4 / hs2: Agregaciones del código de producto a 4 y 2 dígitos,
  útiles para análisis a mayor nivel (sector/capítulo) cuando el
  detalle de HS6 sea demasiado granular.
- trade_value_usd: Valor comerciado del producto, en USD.
- net_weight_kg: Peso neto del producto comerciado, en kilogramos. Permite
  calcular valor unitario implícito (trade_value_usd / net_weight_kg) como
  chequeo de calidad y como variable de interés en sí misma.
- flow: Dirección del flujo comercial (exportación/importación).

  Nota metodológica: los datos de producto cubren dos revisiones distintas
  de la nomenclatura HS — HS2017 para 2017-2021 y HS2022 para 2022 en
  adelante (campo hs_revision). Los códigos HS6 no son directamente
  comparables entre ambos periodos sin una tabla de correlación oficial,
  ya que la revisión HS2022 reorganizó varias categorías de producto. Este
  cambio de nomenclatura debe tenerse en cuenta al interpretar variaciones
  de comercio por producto que coincidan con el corte de 2022, para no
  confundir un cambio de clasificación con un cambio real en el comercio.

### Variables gravitacionales (CEPII Gravity Dataset)

- dist: Distancia en kilómetros entre Colombia y el país socio.
- contig: Frontera física común entre Colombia y el país socio (1/0).
- comlang_off: Idioma oficial común, hablado por al menos el 9% de la
  población de ambos países (1/0).
- col_dep_ever: Relación de dependencia colonial histórica entre Colombia
  y el país socio, en cualquier momento (1/0). Nota: esta es la variable
  equivalente a "COLONIA" en el planteamiento original del proyecto; el
  nombre cambió respecto a la propuesta inicial porque así está etiquetada
  en la versión del Gravity Dataset utilizada (V202211).
- fta_wto: Acuerdo de libre comercio vigente entre Colombia y el país
  socio, notificado a la OMC (1/0). Variable equivalente a "FTA" en la
  propuesta original.

### Tamaño de mercado

- gdp_d: PIB del país socio, en USD constantes. Para 2022-2024 (años no
  cubiertos por el Gravity Dataset original, que llega hasta 2021) se
  actualizó con datos reales extraídos de la API del Banco Mundial
  (indicador NY.GDP.MKTP.KD), en vez de arrastrar el último valor
  disponible.

### Cobertura y exclusiones

El panel cubre 197 países socio. Se excluyeron del panel:
- Entidades políticas disueltas antes de 2017 (ej. Unión Soviética,
  Checoslovaquia, Yugoslavia, Alemania Oriental).
- Microestados y territorios dependientes sin peso comercial propio
  reportado de forma independiente (ej. islas del Pacífico y el Caribe,
  territorios de ultramar).
- Países con datos de PIB no disponibles en el Banco Mundial por motivos
  de aislamiento internacional o conflicto activo (Corea del Norte,
  Siria, Sudán del Sur).

Taiwán se mantuvo en el panel pese a no tener PIB reportado por el Banco
Mundial (por motivos de reconocimiento político, no de tamaño económico);
queda pendiente completar este dato con una fuente alternativa (FMI) o
excluirlo, según se defina.

### Pendiente de integrar

- Variable de tipo de producto exportado (código HS), peso neto y precio
  implícito: en proceso de unión con la base de comercio a nivel producto
  (HS6, revisiones HS2017/HS2022 — pendiente resolver la concordancia
  entre ambas nomenclaturas antes de integrar al panel final).
---

## 5. Estado Actual del Proyecto

### Confirmado
- Modelo Gravitacional
- Análisis de producto por país de destino

### Por definir
- Enfoque empresarial
- Modelos de Machine Learning


---

## 6. Próximas Etapas
1. Construcción de dataset limpio
2. Estimación del Modelo
3. Cálculo de la brecha
4. Modelos de Machine Learning

