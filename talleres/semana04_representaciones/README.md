# Taller · Comparación de representaciones

Una hora. Se trabaja sobre `notebooks/02_representaciones.ipynb`, en Codespaces y dentro del
repositorio de vuestro equipo.

Continúa el bloque 2.2 del Tema 2.

---

## La tarea

Dada una reseña, **recuperar las más parecidas del corpus**. Es la tarea que hay debajo de
buscar quejas del mismo tipo, agrupar incidencias por causa o encontrar menciones equivalentes
de un producto.

Sobre esa tarea se comparan tres representaciones: **bolsa de palabras**, **TF-IDF** y
**embeddings**. Una representación no es mejor por ser más moderna: es mejor si ordena mejor
los resultados de la tarea que os interesa.

---

## Antes de empezar

En la terminal del codespace:

```bash
wget https://raw.githubusercontent.com/mespinosa-cunef/pln-marketing-talleres/main/notebooks/02_representaciones.ipynb -P notebooks/
pip install -r requirements.txt
```

La primera celda descarga **`es_core_news_md`**, que es el modelo de spaCy que sí trae vectores
de palabra. El `es_core_news_sm` del taller anterior tiene **cero vectores** y no sirve aquí.
Tarda un par de minutos: lanzadla nada más abrir el notebook.

---

## Las diez secciones

| | Sección | Qué se obtiene |
|---|---|---|
| 1 | El corpus de trabajo | Cinco reseñas para seguir los cálculos |
| 2 | Bolsa de palabras | La matriz documento-término |
| 3 | Coseno y vecinos con BoW | El primer resultado, y por qué falla |
| 4 | Ponderación TF-IDF | Los pesos y su efecto en el orden |
| 5 | Embeddings de palabras | Similitud entre términos que no coinciden |
| 6 | De palabras a documentos | Composición por media y **cobertura** |
| 7 | Las tres, una al lado de la otra | Comparación sobre la misma consulta |
| 8 | El fallo que hay que conocer | Antónimos próximos |
| 9 | Sobre el corpus real | Las tres sobre 800 reseñas |
| 10 | Registro | La tabla para la bitácora |

Las secciones **7, 8 y 9** son las que no se pueden saltar.

---

## Tres resultados que vais a obtener

- **La bolsa de palabras recupera una reseña positiva** cuando la consulta es una queja, solo
  porque comparten la palabra *producto*. La coincidencia literal no distingue el sentido.
- **TF-IDF baja los cosenos y casi no cambia el orden.** Una puntuación más baja no indica un
  método peor: lo que se evalúa es el orden de los resultados.
- **Los embeddings sitúan `caro` y `barato` a 0,79**, y dos reseñas de sentimiento opuesto
  resultan muy similares. Miden relación temática, no polaridad.

Y uno más, que es el importante: **sobre el corpus real el resultado se invierte** y ganan las
representaciones por recuento. Con un solo ejemplo no se distingue un método bueno de uno
afortunado.

---

## Antes de salir

- [ ] Habéis comparado las tres representaciones con **al menos tres consultas distintas**.
- [ ] Para cada una hay **un acierto y un fallo** anotados, con la reseña concreta.
- [ ] La tabla de la sección 10 está en `docs/bitacora.md`, con la elección provisional y su
      motivo en términos de la tarea.
- [ ] El notebook está confirmado en el repositorio.

La elección **no es definitiva**: en el Hito 1 se documenta la exploración; la representación y
el modelo base se defienden en el Hito 2.
