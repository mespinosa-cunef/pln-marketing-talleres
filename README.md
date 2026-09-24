# Talleres · PLN y sus aplicaciones en marketing

Material de los talleres de la asignatura **Procesamiento del Lenguaje Natural y sus
aplicaciones en marketing** (G260) · Grado en Ciencia de Datos · CUNEF Universidad.

Curso 2026-27 · María Soledad Espinosa Ruiz

---

## Cómo se usa

Los talleres son las sesiones de una hora de los jueves. Tres carpetas, cada una con un
cometido:

- **`notebooks/`** — lo que se ejecuta en cada taller. Es lo que hay que descargar.
- **`talleres/`** — la guía de cada sesión: qué hay que hacer y qué hay que entregar.
- **`plantilla_proyecto/`** — el esqueleto del repositorio de cada equipo. Se copió una vez,
  en el taller de la semana 2, y no se vuelve a tocar.

**Cada semana:** descargad el notebook que toque de `notebooks/` y colocadlo en la carpeta
`notebooks/` de vuestro propio repositorio. Ahí es donde se ejecuta, porque al lado tiene
`data/` y `requirements.txt`.

---

## Contenido

```
notebooks/              Los notebooks de los talleres, en orden de ejecución
├── 00_comprobacion_entorno.ipynb    Semana 2
├── 01_preprocesamiento.ipynb        Semana 3
└── 02_representaciones.ipynb        Semana 4

plantilla_proyecto/     El esqueleto del repositorio de cada equipo
├── README.md               Portada del proyecto; se evalúa en cada hito
├── requirements.txt        Librerías con versión fijada
├── .gitignore              Impide subir claves y datos crudos
├── .env.example            Plantilla para las claves de API
├── notebooks/              Aquí van los notebooks que descarguéis
├── data/                   Capas raw · sample · clean · analytic
└── docs/bitacora.md        Registro de decisiones; de aquí sale la memoria

talleres/               Una carpeta por sesión, con su guía
├── semana02_github/         Repositorio y entorno de trabajo
├── semana03_preprocesamiento/   Preprocesamiento del corpus
└── semana04_representaciones/  Comparación de representaciones
```

## Talleres

| Semana | Taller | Material |
|---|---|---|
| 2 | Repositorio y entorno de trabajo | [guía](talleres/semana02_github/README.md) · `notebooks/00_comprobacion_entorno.ipynb` |
| 3 | Preprocesamiento del corpus | [guía](talleres/semana03_preprocesamiento/README.md) · `notebooks/01_preprocesamiento.ipynb` |
| 4 | Comparación de representaciones | [guía](talleres/semana04_representaciones/README.md) · `notebooks/02_representaciones.ipynb` |

---

## Entorno

El entorno de trabajo es **GitHub Codespaces**, dentro del propio repositorio del equipo.

```bash
pip install -r requirements.txt
python -m spacy download es_core_news_sm    # el modelo de español, una sola vez
```

## La regla que no se puede romper

**Las claves de acceso no se suben nunca al repositorio.** Un token es una contraseña, y una
vez subido queda en el historial de git aunque se borre en el commit siguiente. Van en un
fichero `.env`, que `.gitignore` excluye.
