# 🧭 Clustering Jerárquico & DBSCAN

Píldora de conocimiento sobre aprendizaje no supervisado — cómo agrupar datos cuando nadie te dice cuántos grupos hay ni cuáles son.

**🔗 Demo en directo:** https://adrianaarang.github.io/Clustering-Jerarquico-DBSCAN/

---

## Qué hay aquí

| Archivo | Qué es |
|---|---|
| `index.html` | La web interactiva de la sesión: intuición animada, live coding simulado, laboratorio con quizzes y ficha ética. |
| `solucion_clustering.ipynb` | Notebook con la solución completa y comentada — para repasar por tu cuenta o comparar tras el reto. |
| `reto_clustering_TODO.ipynb` | El mismo notebook, pero con bloques `# TODO` para completar en directo. |
| `ficha_criterio_etico.docx` | Ficha de un párrafo sobre riesgos y límites éticos de ambos algoritmos. |

## Estructura de la sesión

1. **Contextualización e intuición** — analogías (álbum de fotos, árbol genealógico, plaza vista desde un dron) + animaciones del dendrograma y de la expansión de densidad de DBSCAN.
2. **Live coding** — construcción en directo de `AgglomerativeClustering` y `DBSCAN` con scikit-learn, con un quiz autocorregible sobre el parámetro `eps`.
3. **Reto de aplicación** — laboratorio interactivo: plantas puntos en un lienzo y comparas ambos algoritmos moviendo sus parámetros en vivo.
4. **Code review y cierre** — tabla comparativa de coste computacional y checklist de errores típicos.

## Primeros auxilios (troubleshooting)

Si algo falla mientras corres el notebook de la solución:

- **`ValueError: Found array with dim 3 (expected 2)`** → revisa `X.shape`; tiene que ser `(n_muestras, n_features)`.
- **DBSCAN devuelve casi todo `-1` (ruido)** → `eps` demasiado pequeño para la escala de tus datos, o se te olvidó escalar con `StandardScaler`.
- **`MemoryError` o se cuelga con `AgglomerativeClustering`** → el jerárquico calcula una matriz O(n²); con más de ~10-20k filas, submuestrea o usa DBSCAN.
- **Todo cae en un único cluster gigante** → prueba a cambiar `linkage='single'` por `'ward'` o `'complete'` (single es muy propenso al efecto cadena).

## Stack

Python · scikit-learn · scipy · matplotlib · HTML/CSS/JS vanilla (sin build, desplegado directo con GitHub Pages).

---

Adriana Aránguez · Bootcamp IA & Big Data, Somos F5/Fundación Tomillo
