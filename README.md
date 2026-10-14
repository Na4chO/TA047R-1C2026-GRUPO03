# Trabajo Práctico 1 - Ciencia de Datos (TA047)

Cátedra Rodríguez - Villanueva · 2do Cuatrimestre 2026 · Grupo 03

## Integrantes

| Nombre y apellido | Padrón |
|---|---|
| Thiago Reller | 111067 |
| Sofía Encina | 111891 |
| Ignacio Politti | 112034 |
| Francisco Serrano | 111813 |
| Salvador Perez Mendoza | 110198 |

## Informe

[Acceder al informe del proyecto](LINK_INFORME)

## Notebooks

* [TA047R_TP1_GRUPO03_ENTREGA_EJ1](./notebooks/TA047R_TP1_GRUPO03_ENTREGA_EJ1.ipynb): análisis exploratorio de los datasets de Rebrickable (LEGO), cuatro preguntas de investigación y agrupamiento con K-Means.
* [TA047R_TP1_GRUPO03_ENTREGA_EJ2](./notebooks/TA047R_TP1_GRUPO03_ENTREGA_EJ2.ipynb): modelos de regresión sobre publicaciones de AirBnB en Milán (regresión lineal múltiple y Random Forest).
* [TA047R_TP1_GRUPO03_ENTREGA_EJ3](./notebooks/TA047R_TP1_GRUPO03_ENTREGA_EJ3.ipynb): clasificación de cancelaciones de reservas de hotel para la competencia de Kaggle (árbol de decisión, Random Forest, XGBoost y ensambles Voting y Stacking).

## Modelos entrenados

Los modelos del Ejercicio 3 se encuentran en la carpeta modelos/.

## Requisitos para la ejecución

Los notebooks leen los datos locales de `datasets/`, sin montar Google Drive.
Se pueden ejecutar con Jupyter o VS Code desde la raíz del proyecto o desde
`notebooks/`. Ejecutar las celdas en orden.

Instalar las dependencias con:

```bash
python -m pip install -r requirements.txt
```

Para visualizar el árbol de XGBoost en el Ejercicio 3 también se necesita
Graphviz instalado en el sistema (comando `dot`; en Ubuntu: `sudo apt install graphviz`).
Los CSV de predicciones se guardan en el directorio de ejecución.

Si se usa Google Colab, copiar o clonar el proyecto completo en el entorno,
incluyendo `notebooks/` y `datasets/`, y ejecutar desde esa carpeta.

## Datos

* `datasets/ej1/`: archivos CSV de Rebrickable (LEGO); `inventory_parts.csv.gz` se lee directamente comprimido.
* `datasets/ej2/`: `listings.csv.gz` y `tpl_metrofermate.csv`.
* `datasets/ej3/`: `hotels_train.csv` y `hotels_test.csv`.

Las estaciones de metro provienen del [portal de datos abiertos del Comune di Milano](https://dati.comune.milano.it/dataset/ds535_atm-fermate-linee-metropolitane/resource/0f4d4d05-b379-45a4-9a10-412a34708484)
(licencia CC BY 4.0). Se incluye una copia local para ejecutar sin descargar datos.
