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

[Acceder al informe del proyecto](./TA047R_TP1_GRUPO03_REPORTE.pdf)

## Notebooks

* [TA047R_TP1_GRUPO03_ENTREGA_EJ1](./notebooks/TA047R_TP1_GRUPO03_ENTREGA_EJ1.ipynb): análisis exploratorio de los datasets de Rebrickable (LEGO), cuatro preguntas de investigación y agrupamiento con K-Means.
* [TA047R_TP1_GRUPO03_ENTREGA_EJ2](./notebooks/TA047R_TP1_GRUPO03_ENTREGA_EJ2.ipynb): modelos de regresión sobre publicaciones de AirBnB en Milán (regresión lineal múltiple y Random Forest).
* [TA047R_TP1_GRUPO03_ENTREGA_EJ3](./notebooks/TA047R_TP1_GRUPO03_ENTREGA_EJ3.ipynb): clasificación de cancelaciones de reservas de hotel para la competencia de Kaggle (árbol de decisión, Random Forest, XGBoost y ensambles Voting y Stacking).

## Cómo ejecutar el proyecto

Los datos ya están incluidos en `datasets/`. No hace falta usar Google Drive
ni descomprimir los archivos `.gz`. Mantener `datasets/` y `notebooks/` dentro
de la misma carpeta del proyecto.

### 1. Descargar el proyecto

Se necesita Python 3.10 o superior. Clonar el repositorio y entrar a su carpeta:

```bash
git clone https://github.com/Na4chO/TA047R-1C2026-GRUPO03.git
cd TA047R-1C2026-GRUPO03
```

Si ya tenés el proyecto, abrir una terminal en la carpeta donde están
`README.md` y `requirements.txt` y continuar con el paso 2.

### 2. Preparar el entorno (solo la primera vez)

En Linux o macOS:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

En Windows, desde PowerShell:

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

Las dependencias se instalan dentro de `.venv`.

Para generar el gráfico del árbol de XGBoost del ejercicio 3, instalar también
Graphviz en el sistema. El ejecutable `dot` no se instala con `requirements.txt`.
En Ubuntu o Debian:

```bash
sudo apt update
sudo apt install graphviz
```

Comprobar la instalación con:

```bash
dot -V
```

Si muestra la versión de Graphviz, el ejecutable está disponible. Esta instalación
se realiza una sola vez, fuera del entorno virtual.

### 3. Abrir Jupyter

Con el entorno activado, ejecutar:

```bash
jupyter notebook
```

Se abre una página en el navegador. Mantener abierta la terminal que inició
Jupyter durante la ejecución.

### 4. Ejecutar un notebook

1. En la página de Jupyter, entrar a `notebooks/` y abrir el ejercicio deseado.
2. Elegir **Kernel → Restart Kernel and Run All Cells…** para ejecutarlo desde cero.
   En la interfaz clásica, usar **Kernel → Restart & Run All**.
3. Esperar a que termine: `[*]` indica que una celda se está ejecutando o está
   en espera; un número como `[1]` indica que terminó.
4. Los resultados y gráficos aparecen debajo de las celdas. Los entrenamientos
   del ejercicio 3 pueden tardar bastante, especialmente el ensamble Stacking.
5. Guardar los resultados con **Ctrl + S** o **File → Save Notebook**.

Para ejecutar una sola celda, seleccionarla y presionar **Shift + Enter**.
Si aparece un error, la ejecución de las celdas siguientes se detiene: revisar
el primer error antes de volver a ejecutar todo.

### Volver a ejecutar otro día

No hace falta crear el entorno ni instalar nuevamente las dependencias.
Desde la carpeta del proyecto, en Linux o macOS:

```bash
source .venv/bin/activate
jupyter notebook
```

En Windows, activar con `.\.venv\Scripts\Activate.ps1` y ejecutar
`jupyter notebook`. Al terminar, detener Jupyter con **Ctrl + C** en la terminal
(y confirmar si lo pide); luego ejecutar `deactivate`.

### Usar VS Code

Abrir la carpeta del proyecto e instalar las extensiones Python y Jupyter.
Abrir un archivo de `notebooks/`, elegir **Select Kernel** y seleccionar el
entorno `.venv`. Usar **Run All** para ejecutar todas las celdas.

### Archivos que se generan

Los archivos se guardan en el directorio de ejecución (normalmente `notebooks/`
al abrirlos desde Jupyter):

* `.ipynb_checkpoints/`: respaldos automáticos de Jupyter.
* `real_vs_predicho_lineal.png`: gráfico exportado por el ejercicio 2.
* `submission_*.csv`: predicciones del ejercicio 3 para enviar a Kaggle;
  contienen `id` e `is_canceled`, con un archivo por modelo.

Estos archivos se excluyen de Git. Los PNG y CSV se pueden borrar y regenerar
al ejecutar sus celdas. Los modelos se entrenan en memoria; no se guardan
modelos entrenados en una carpeta `modelos/`.

### Problemas frecuentes

* **No aparecen gráficos:** esperar a que termine la celda. Si sigue sin
  mostrarlos, ejecutar `%matplotlib inline` en una celda antes de los gráficos.
* **`ModuleNotFoundError`:** comprobar que el kernel usa `.venv` y ejecutar
  `python -m pip install -r requirements.txt` con el entorno activado.
* **No se encuentra `datasets/`:** abrir el proyecto completo y ejecutar desde
  su raíz o desde `notebooks/`, conservando las carpetas de datos.
* **No se dibuja el árbol de XGBoost:** instalar Graphviz en el sistema;
  en Ubuntu, `sudo apt install graphviz`. El paquete `graphviz` de Python
  no instala el ejecutable `dot`. Si falta, el notebook omite ese árbol y
  continúa con las demás operaciones.

## Datos

* `datasets/ej1/`: archivos CSV de Rebrickable (LEGO); `inventory_parts.csv.gz` se lee directamente comprimido (Se tuvo que comprimir por restricciones de espacio de GitHub).
* `datasets/ej2/`: `listings.csv.gz` y `tpl_metrofermate.csv`.
* `datasets/ej3/`: `hotels_train.csv` y `hotels_test.csv`.

Las estaciones de metro provienen del [portal de datos abiertos del Comune di Milano](https://dati.comune.milano.it/dataset/ds535_atm-fermate-linee-metropolitane/resource/0f4d4d05-b379-45a4-9a10-412a34708484)
(licencia CC BY 4.0). Se incluye una copia local para ejecutar sin descargar datos.
