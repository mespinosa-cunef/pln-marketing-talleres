# Taller · Preprocesamiento y normalización de texto

Una hora. Se trabaja sobre `notebooks/01_preprocesamiento.ipynb`, en Codespaces y dentro del
repositorio de vuestro equipo.

Continúa el bloque 2.1 del Tema 2.

---

## El corpus

Trabajamos sobre un **corpus externo**: 5.000 reseñas de producto de Amazon en español,
repartidas a partes iguales entre las cinco puntuaciones. Así todos empezáis con datos, sin
depender de que vuestra recolección esté terminada.

El notebook lo descarga solo, a `data/raw/`. Cuando tengáis vuestro corpus repetiréis el mismo
procedimiento cambiando una línea.

> Procede del *Multilingual Amazon Reviews Corpus*, copia `mteb/amazon_reviews_multi` de
> Hugging Face. **Uso docente**: no se redistribuye, y `.gitignore` impide que entre en el
> repositorio.

---

## Qué hay que sacar de aquí

El taller no va de escribir código: las celdas están escritas. Va de que toméis **cuatro
decisiones** y las anotéis en `docs/bitacora.md` **con el motivo y con un ejemplo del corpus
que lo respalde**:

1. Qué tokenizador usáis.
2. Si pasáis a minúsculas, y en qué momento.
3. Qué hacéis con las stopwords.
4. Stemming o lematización.

La rúbrica del Hito 1 no pide el preprocesamiento *aplicado*: pide el preprocesamiento
**aplicado y justificado**. Ejecutar las celdas es la mitad del trabajo.

---

## Antes de empezar

Descargad el notebook a vuestro repositorio. En la terminal del codespace:

```bash
wget https://raw.githubusercontent.com/mespinosa-cunef/pln-marketing-talleres/main/notebooks/01_preprocesamiento.ipynb -P notebooks/
pip install -r requirements.txt
```

La primera celda del notebook descarga el modelo de español de spaCy si falta. Tarda un par de
minutos la primera vez: **lanzadla en cuanto abráis el notebook** y seguid leyendo mientras.

---

## Las once secciones

| | Sección | Qué se decide o se descubre |
|---|---|---|
| 1 | Descargar el corpus | Por qué `data/raw` no se versiona |
| 2 | Mirar el corpus antes de tocarlo | La línea base de siete fenómenos del texto |
| 3 | La estructura del documento | Título y cuerpo son dos señales distintas |
| 4 | Tokenizar | **Decisión 1** |
| 5 | Minúsculas y el orden | **Decisión 2** |
| 6 | Stopwords | **Decisión 3** |
| 7 | Stemming frente a lematización | **Decisión 4** + el efecto del orden |
| 8 | Montar el pipeline | Vuestras decisiones, en siete líneas |
| 9 | Qué ha cambiado y qué se ha perdido | Cuánto sobrevive de la sección 2 |
| 10 | Para qué servía todo esto | Términos de 1 estrella frente a 5 |
| 11 | Guardar y documentar | La entrada de la bitácora |

Las secciones **9 y 10 son las importantes**. Si vais con el tiempo justo, pasad rápido por la
2 y la 3, pero llegad a ellas.

---

## Tres cosas que vais a descubrir

No son curiosidades: son las tres formas en que un preprocesamiento mal justificado estropea un
proyecto.

- **El tokenizador de NLTK no separa el signo `¿`** y devuelve `¿En` como un solo token. Doce
  reseñas del corpus quedan con tokens que no existen. No da ningún error.
- **La lista de stopwords de NLTK contiene `no`, `ni`, `nada` y `sin`, pero no `nunca`,
  `tampoco` ni `jamás`.** Filtrando a ciegas, el sentido se invierte en más de la mitad del
  corpus, y de forma incoherente.
- **Lematizar antes o después de filtrar da corpus distintos.** La lista contiene `es` y `son`
  pero no `ser`, así que al lematizar primero los auxiliares se escapan del filtro y acaban
  siendo las palabras más frecuentes del corpus «limpio».

---

## Antes de salir

- [ ] `data/clean/corpus_preprocesado.csv` existe.
- [ ] La entrada **«Preprocesamiento del corpus»** de `docs/bitacora.md` está rellenada. La
      última celda del notebook imprime la tabla con vuestra configuración: pegadla y
      completad las columnas **«Por qué»** y **«Ejemplo del corpus»** de las cuatro
      decisiones. Esas dos columnas son las que se evalúan.
- [ ] Habéis ejecutado la sección 10 dos veces, con `CONSERVAR_NEGACIONES` en `True` y en
      `False`, y sabéis explicar la diferencia.
- [ ] El notebook está confirmado en el repositorio.

`data/raw/` y `data/clean/` **no se suben**: los excluye el `.gitignore`. Lo que se sube es el
notebook y la bitácora — con eso cualquiera reproduce el resultado.
