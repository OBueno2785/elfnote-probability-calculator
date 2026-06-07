# Elfnote Probability Calculator

Este proyecto contiene una herramienta estadística interactiva y una simulación de Monte Carlo en Jupyter Notebook diseñada para optimizar, analizar y evaluar el rendimiento y consistencia competitiva del mazo personalizado **Elfnote** (enfocado en invocaciones Synchro de Niveles 7, 8 y 10, y complementado por el motor "Fallen of Albaz").

## 📊 Características Principales

1. **Carga Dinámica del Deck**: Parseo automático del archivo de la baraja (`txt.txt`) distinguiendo entre Main Deck, Extra Deck y Side Deck.
2. **Consistencia de Starters**: Cálculo exacto mediante distribución hipergeométrica de la probabilidad de abrir combos de 1 carta.
3. **Análisis Defensivo**: Probabilidad acumulada de robar 2 o más interrupciones (handtraps) en tu mano inicial para interrumpir el turno del oponente.
4. **Heatmaps Cruzados (El Balance Dorado)**: Visualización multidimensional de probabilidad de robo según el tamaño del mazo (40 a 50 cartas) y la proporción de starters frente a handtraps.
5. **Simulación de Monte Carlo (100k iteraciones)**:
   - Valor Esperado (EV) de poder de la mano inicial (escala 0-5).
   - Valor Esperado (EV) de handtraps robadas.
   - Histograma de distribución de poder de apertura.
   - Gráfico de barras horizontales con las probabilidades de robar cada combo individual.
6. **Clasificación de Manos**:
   - Top 15 de manos más recurrentes con conteo de handtraps exacto.
   - Top 20 de manos de mayor poder.
7. **Dispersión y Correlación de Pearson**: Análisis para comprobar si las manos de mayor poder son también las más probables (consistencia de combo) o si representan combinaciones raras.
8. **Simulador de Torneo Bo3**: Proyección competitiva de 100,000 torneos suizos a 8 rondas para estimar la probabilidad de entrar a Top Cut (>= 6-2) e Invictos (8-0).

## 🚀 Requisitos y Configuración

El proyecto requiere **Python 3.8+** y las siguientes librerías de análisis de datos:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `jupyter` o `notebook`

### Instalación

1. Clona este repositorio:
   ```bash
   git clone https://github.com/OBueno2785/elfnote-probability-calculator.git
   cd elfnote-probability-calculator
   ```

2. Instala las dependencias necesarias:
   ```bash
   pip install -r requirements.txt
   ```
   *(Nota: Puedes crear un entorno virtual antes de instalar).*

3. Asegúrate de colocar tu lista de mazo en un archivo llamado `txt.txt` en la raíz del proyecto. El formato del archivo debe seguir la estructura:
   ```text
   Main Deck:
   3x Elfnote Lucina
   3x Elfnote Tinia
   ...
   Extra Deck:
   1x ...
   ```

4. Inicia Jupyter Notebook y abre el archivo para explorar los análisis:
   ```bash
   jupyter notebook Probability_Calculator_Elfnote.ipynb
   ```

## 📈 Resultados del Análisis de Referencia (Deck de 42 Cartas)

En base a la baraja inicial de 42 cartas, se obtuvieron los siguientes resultados destacados en la simulación:
- **Consistencia Base de Combos**: **93.41%**
- **Valor Esperado de Poder de Mano (EV)**: **3.82 / 5.00**
- **Valor Esperado de Handtraps por Mano**: **1.67**
- **Correlación Probabilidad vs. Poder**: **+0.1420** (Correlación positiva débil, indicando un diseño estable de la baraja sin bricks severos de combos de alto poder).
- **Proyección Competitiva en Torneo Bo3 (8 rondas)**:
  - Probabilidad de **Top Cut (>= 6 victorias)**: **68.60%**
  - Probabilidad de **Terminar Invicto (8-0)**: **10.37%**

---
Desarrollado con fines de optimización y teoría competitiva para el juego de cartas Yu-Gi-Oh!
