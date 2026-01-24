# 🦠 Simulación de Epidemiología en México
**Autores**: Natalia Malpica, Diego Martínez, Alen Solís y Esteban Eguiarte

Este proyecto es una aplicación interactiva desarrollada en **Python con Streamlit** que permite **simular la propagación de un virus en los estados de México**, considerando factores climáticos, sociales y de salud pública.

El usuario puede **crear su propio virus**, definir sus características y observar cómo se dispersa por el país utilizando un **modelo basado en grafos (BFS)** y simulación de población en tiempo real.

---

## 📌 Características principales

- Mapa real de México usando **GeoPandas**
- Estados modelados como nodos de un **grafo**
- Propagación del virus mediante **Búsqueda en Anchura (BFS)**
- Simulación de población sana y contagiada
- Visualización en tiempo real con **matplotlib**
- Creación personalizada de virus
- Análisis por estado y regresión polinomial

---

## 🧠 ¿Cómo funciona?

Cada estado de México tiene atributos como:

- Lluvias intensas  
- Temperaturas altas y bajas  
- Sistema de salud  
- Densidad poblacional  
- Ganadería  
- Pobreza  
- Impacto de enfermedades respiratorias  

Cuando el usuario crea un virus, selecciona qué factores favorecen su propagación.  
Con esto, el sistema calcula un **índice de contagio** para cada estado y simula cómo se infectan sus poblaciones.

El virus se propaga entre estados usando un **grafo de fronteras**, y dentro de cada estado la población se contagia mediante **hilos (threads)** que representan el paso del tiempo.

---

## 🗺️ Modelo de propagación

- Los estados son nodos.
- Las fronteras y conexiones aéreas son aristas.
- Se usa **BFS (Breadth First Search)** para simular la expansión.
- Los estados más vulnerables se infectan primero.

---

## 📊 Visualización

La app muestra:

- Un mapa de México con puntos:
  - 🟢 Verde = población sana  
  - 🔴 Rojo = población contagiada
- Evolución de casos por estado
- Curva ajustada por **regresión polinomial**
- Camino que siguió el virus hasta un estado específico

---

## ⚙️ Requisitos

Asegúrate de tener Python 3.8 o superior.

Instala las dependencias:

```bash
pip install streamlit pandas geopandas shapely matplotlib networkx numpy
```

## ▶️ Cómo ejecutar el proyecto

1. Asegúrate de tener los siguientes archivos en la misma carpeta:
   - `EXAMEN_FINAL_IA.py`
   - `IA TABLA EXAMEN FINAL.csv`

2. Instala las dependencias necesarias:

  ```bash
  pip install streamlit pandas geopandas shapely matplotlib networkx numpy
  ```

3. Ejecuta la aplicación desde la terminal:
   ```bash
    python -m streamlit run EXAMEN_FINAL_IA.py
    ```
  
4. Se abrirá automáticamente una pestaña en tu navegador con la aplicación.

## 🧪 Cómo usar la aplicación

1. En el menú lateral selecciona **"Crear virus"**.
2. Escribe el **nombre del virus**.
3. Usa los **sliders** para definir qué factores favorecen su propagación:
   - Lluvias intensas  
   - Temperaturas altas y bajas  
   - Densidad poblacional  
   - Ganadería  
   - Pobreza  
   - Transmisión respiratoria  
4. Selecciona el **estado donde inicia el brote**.
5. Ajusta la **velocidad de transmisión entre estados**.
6. Haz clic en **"Guardar"** para registrar el virus.
7. Ve a la sección **"Simular"** desde el menú lateral.
8. Observa cómo el virus se propaga en el mapa de México.
9. Selecciona un estado para ver:
   - El camino que siguió el virus hasta ese estado  
   - La gráfica de personas contagiadas por semana  
   - Los datos del virus utilizado
