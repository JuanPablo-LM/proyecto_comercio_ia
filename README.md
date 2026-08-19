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
- **Variables Clave:**
  * Distancia Geográfica: Distancia entre Colombia y el país destino.
  * Tamaño del Mercado: Tamaño económico del país destino.
  * Aranceles Aplicados: Arancel que enfrenta el producto colombiano al entrar al país destino.
  * Acuerdos Comerciales Vigentes: Si existe un tratado de libre comercio con el país destino
  * Tipo de Cambio Real: Competitividad cambiaria del peso colombiano frente al país destino.


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

