# Taller · Preprocesamiento del corpus

Una hora. Se trabaja sobre `plantilla_proyecto/notebooks/01_preprocesamiento.ipynb`, en
Codespaces y dentro del repositorio de vuestro equipo.

Continúa el bloque 2.1 del Tema 2.

---

## Qué hay que sacar de aquí

El taller no va de escribir código: las celdas están escritas. Va de que toméis **cuatro
decisiones** y las anotéis en `docs/bitacora.md` **con el motivo**:

1. Qué tokenizador usáis.
2. Si pasáis a minúsculas, y en qué momento.
3. Qué hacéis con las stopwords.
4. Stemming o lematización.

La rúbrica del Hito 1 no pide el preprocesamiento *aplicado*: pide el preprocesamiento
**aplicado y justificado**. Ejecutar el notebook es la mitad del trabajo; la otra mitad es la
bitácora.

---

## Antes de empezar

En la terminal del codespace:

```bash
pip install -r requirements.txt
```

La primera celda del notebook descarga el modelo de español de spaCy si falta. Tarda un par
de minutos la primera vez: **lanzadla en cuanto abráis el notebook**.

---

## Los pasos

| | Sección del notebook | Qué se decide |
|---|---|---|
| 1 | Cargar el corpus | — |
| 2 | Mirar el texto crudo | Duplicados y vacíos |
| 3 | Tokenizar: NLTK frente a spaCy | **Decisión 1** |
| 4 | Minúsculas y el orden de los pasos | **Decisión 2** |
| 5 | Stopwords: las dos listas no coinciden | **Decisión 3** |
| 6 | Stemming frente a lematización | **Decisión 4** |
| 7 | Aplicar el pipeline al corpus completo | — |
| 8 | Qué ha cambiado y qué se ha perdido | — |
| 9 | Guardar y documentar | — |

**Cambiad la ruta del fichero y el nombre de la columna** en la sección 1. Si no lo hacéis, el
notebook no falla: usa un corpus de ejemplo de seis reseñas y avisa por pantalla. Comprobad
que no estáis trabajando con el ejemplo creyendo que son vuestros datos.

---

## Antes de salir

- [ ] `data/clean/corpus_preprocesado.csv` existe.
- [ ] Las cuatro decisiones están en `docs/bitacora.md`, **con el motivo**.
- [ ] Para cada decisión hay un ejemplo de vuestro corpus que la respalda.
- [ ] El notebook está confirmado en el repositorio.

`data/clean/` no se sube: lo excluye el `.gitignore`. Lo que se sube es el notebook y la
bitácora. Si queréis que el resultado sea reproducible, dejad una muestra en `data/sample/`.
