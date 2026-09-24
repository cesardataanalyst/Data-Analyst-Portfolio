# Data-Analyst-Portfolio
Data Analysis Projects using SQL
# Proyecto de Ventas | MercadoLibre Funnel Analysis

## Contexto y problema de negocio

El análisis busca comprender el recorrido de los usuarios dentro de una plataforma de comercio electrónico, desde su primera visita hasta la realización de una compra.
El proceso de compra está compuesto por diferentes etapas, y analizar el comportamiento de los usuarios en cada una permite identificar dónde se producen pérdidas de usuarios y qué etapas del recorrido requieren mayor atención.
Para este proyecto se construyó un embudo de conversión (funnel) utilizando eventos registrados durante el período comprendido entre el 1 de enero y el 31 de agosto de 2025, segmentando los resultados por país.

## Objetivo
Analizar el recorrido de los usuarios a través de las principales etapas del proceso de compra y medir la conversión alcanzada en cada etapa del funnel.
El análisis busca identificar:
- La cantidad de usuarios que avanzan en cada etapa del proceso.
- La conversión de usuarios desde la primera visita hasta la compra.
- Las diferencias de conversión entre países.
- Los puntos del recorrido donde se presentan mayores pérdidas de usuarios.

  ## Preguntas de negocio
El análisis busca responder las siguientes preguntas:
- ¿Cuántos usuarios comienzan su recorrido con una primera visita?
- ¿Cuántos usuarios avanzan hacia la selección de productos o promociones?
- ¿Cuántos usuarios agregan productos al carrito?
- ¿Cuántos usuarios comienzan el proceso de checkout?
- ¿Cuántos usuarios proporcionan información de envío?
•	¿Cuántos usuarios proporcionan información de pago?
•	¿Cuántos usuarios completan una compra?
•	¿Cómo varían las tasas de conversión entre los diferentes países?
•	¿En qué etapas del funnel se concentra la pérdida de usuarios?

## Datos utilizados
El análisis utiliza la tabla:
mercadolibre_funnel
Los eventos analizados representan diferentes etapas del recorrido del usuario:
- first_visit
- select_item
- select_promotion
- add_to_cart
- begin_checkout
- add_shipping_info
- add_payment_info
- purchase

El período analizado corresponde del 2025-01-01 al 2025-08-31.
Las principales variables utilizadas en el análisis son:
- user_id: identificador del usuario.
- country: país asociado al usuario.
- event_name: evento realizado.
- event_date: fecha del evento.

## Herramientas y tecnologías
- SQL
- Common Table Expressions (CTEs)
- Funnel Analysis
- Data Aggregation
- Conversion Rate Analysis

## Hallazgos principales
El análisis permite estudiar el comportamiento de los usuarios a lo largo de todo el proceso de compra y observar cómo disminuye el número de usuarios a medida que avanzan por las diferentes etapas del funnel.

La segmentación por país permite identificar diferencias en las tasas de conversión y detectar mercados que requieren un análisis más detallado.
Las principales áreas de análisis corresponden a:
- Pérdida de usuarios entre etapas.
- Conversión hacia el checkout.
- Continuidad del proceso de envío y pago.
- Conversión final a compra.
- Diferencias de comportamiento entre países.

Los hallazgos cuantitativos deberán interpretarse a partir de los resultados obtenidos directamente de la consulta SQL.
Se logró identificar el comportamiento de los usuarios a lo largo de todo el proceso de compra mediante un embudo estructurado de conversión.
El análisis permitió medir la efectividad de cada etapa y detectar posibles puntos de abandono dentro del recorrido del cliente.
La comparación por país facilita identificar mercados con mejor desempeño y mayores tasas de conversión final.
El cálculo de conversiones por etapa proporciona información valiosa para optimizar la experiencia del usuario y mejorar el rendimiento comercial de la plataforma.

## Valor para el negocio
Este análisis proporciona una visión integral del customer journey y permite responder preguntas clave como:
- ¿Cuántos usuarios avanzan entre cada etapa del embudo?
- ¿Dónde se presentan las mayores pérdidas de usuarios?
- ¿Qué países presentan mejores niveles de conversión?
- ¿Qué etapas del proceso requieren optimización para incrementar las ventas?

## Metodología
El análisis se desarrolló mediante una consulta SQL estructurada en varias etapas.

### 1. Identificación de eventos
Primero se identificaron los diferentes eventos disponibles en la tabla mercadolibre_funnel mediante SELECT DISTINCT.

### 2. Construcción de las etapas del funnel
Se utilizaron CTEs (Common Table Expressions) para separar cada etapa del recorrido del usuario:
- first_visits
- select_item
- add_to_cart
- begin_checkout
- add_shipping_info
- add_payment_info
- purchase
Cada etapa fue filtrada utilizando el período de análisis definido.

### 3. Segmentación por país
Los usuarios fueron asociados con su país y posteriormente se utilizaron las diferentes etapas del funnel para realizar la comparación entre países.

### 4. Consolidación de usuarios
Se utilizaron LEFT JOIN para relacionar las diferentes etapas del recorrido a partir de:
- user_id
- country
Esto permitió consolidar el recorrido de los usuarios desde first_visit hasta purchase.

### 5. Cálculo de conversión
Finalmente, se calcularon las tasas de conversión de cada etapa tomando como referencia la cantidad de usuarios que realizaron first_visit.
Las conversiones analizadas fueron:
-First Visit → Select Item
- First Visit → Add to Cart
- First Visit → Begin Checkout
- First Visit → Add Shipping Info
- First Visit → Add Payment Info
- First Visit → Purchase

Los resultados fueron ordenados de acuerdo con la conversión final a compra.

## Resultados
Funnel de conversión.
La consulta SQL permite obtener, para cada país, la cantidad de usuarios que alcanzaron cada etapa del proceso y su respectiva tasa de conversión respecto a first_visit.

## Conclusiones
El análisis demuestra cómo SQL puede utilizarse para transformar eventos individuales de usuarios en una visión estructurada del customer journey.
La utilización de CTEs permitió organizar las diferentes etapas del proceso de compra y facilitar la construcción del funnel.
La segmentación por país permite complementar el análisis general con una perspectiva geográfica y comparar el comportamiento de los usuarios en diferentes mercados.
Las conclusiones específicas sobre qué etapa presenta la mayor pérdida de usuarios y qué países presentan mayores tasas de conversión deben basarse en los resultados cuantitativos obtenidos de la consulta.

## Contacto
📧 cesarpalacioleiva@gmail.com

🔗 www.linkedin.com/in/cesar-palacio-data

