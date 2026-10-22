# sprint7-final-project
#  Análisis Exploratorio de Datos y Segmentación de Clientes — ConnectaTel

Este repositorio contiene el Análisis Exploratorio de Datos (EDA) y la segmentación estratégica de clientes realizada para la compañía de telecomunicaciones **ConnectaTel**. El objetivo es identificar patrones de consumo, evaluar el impacto de los hábitos de uso frente a las variables demográficas y proponer estrategias comerciales de *upselling*.

---

## Objetivo del Proyecto

* **Identificar patrones de consumo:** Analizar el comportamiento de los clientes en cuanto a minutos de llamada, cantidad de llamadas y mensajes de texto.
* **Evaluar datos atípicos:** Analizar la presencia de *heavy users* (usuarios de uso extremo) para entender su valor operativo sin distorsionar la integridad del negocio.
* **Segmentación estratégica:** Crear grupos de clientes basados en uso (`grupo_uso`) y edad (`grupo_edad`) para determinar qué factores impulsan la elección entre los planes **Básico** y **Premium**.
* **Generar recomendaciones estratégicas:** Proporcionar un análisis ejecutivo orientado a la optimización del portafolio comercial y la migración de clientes a planes de mayor valor.

---

##  Datasets Utilizados

El análisis se basa en el dataset de perfiles de usuario de telecomunicaciones:

* **`user_profile`**: Contiene la información demográfica y los registros de tráfico por usuario.
  * `user_id`: Identificador único del cliente.
  * `age`: Edad del usuario.
  * `plan`: Tipo de plan contratado (*Básico* o *Premium*).
  * `cant_llamadas`: Cantidad total de llamadas realizadas.
  * `cant_minutos_llamada`: Total de minutos consumidos en llamadas.
  * `cant_mensajes`: Cantidad total de mensajes de texto enviados.

---

## 🛠️ Etapas del Análisis Realizadas

1. **Limpieza de Datos y Gestión de Atípicos:**
   * Identificación de valores atípicos mediante el método de Rango Intercuartílico (IQR).
   * Confirmación de que los valores extremos corresponden a hábitos reales de alto consumo (*heavy users*), conservándolos para preservar la representatividad financiera y de red.
2. **Ingeniería de Funciones y Segmentación:**
   * `grupo_uso`: Clasificación en **Bajo uso** (< 5 llamadas y mensajes), **Uso medio** (< 10 llamadas y mensajes) y **Alto uso** (resto de casos).
   * `grupo_edad`: Clasificación en **Joven** (< 30 años), **Adulto** (< 60 años) y **Adulto Mayor** (≥ 60 años).
3. **Análisis Exploratorio Visual (EDAV):**
   * Gráficos de distribución univariados y bivariados (`countplot`, `boxplot`) cruzando segmentaciones con el tipo de plan.
4. **Hallazgos Clave y Recomendaciones:**
   * La edad no influye en la preferencia de plan ni en el volumen consumido.
   * El nivel de uso determina la oportunidad de negocio: los usuarios de **Alto uso** en el plan **Básico** representan la oportunidad prioritaria de *upselling* a **Premium**.
