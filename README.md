# Talleres · PLN y sus aplicaciones en marketing

Material de los talleres de la asignatura **Procesamiento del Lenguaje Natural y sus
aplicaciones en marketing** (G260) · Grado en Ciencia de Datos · CUNEF Universidad.

Curso 2026-27 · María Soledad Espinosa Ruiz

---

## Cómo se usa

Los talleres son las sesiones de una hora de los jueves. Cada uno tiene su guía en
`talleres/`, y los notebooks que se ejecutan están en `plantilla_proyecto/notebooks/`.

**Para los equipos del proyecto:** copiad el contenido de `plantilla_proyecto/` a vuestro
repositorio. Es la estructura sobre la que se trabaja todo el semestre.

---

## Contenido

```
plantilla_proyecto/     La estructura que copia cada equipo a su repositorio
├── README.md               Portada del proyecto; se evalúa en cada hito
├── requirements.txt        Librerías con versión fijada
├── .gitignore              Impide subir claves y datos crudos
├── .env.example            Plantilla para las claves de API
├── notebooks/              Los notebooks, numerados en orden de ejecución
├── data/                   Capas raw · sample · clean · analytic
└── docs/bitacora.md        Registro de decisiones; de aquí sale la memoria

talleres/               Una carpeta por sesión, con su guía
├── semana02_github/         Repositorio y entorno de trabajo
└── semana03_preprocesamiento/   Preprocesamiento del corpus
```

## Talleres

| Semana | Taller | Material |
|---|---|---|
| 2 | Repositorio y entorno de trabajo | [guía](talleres/semana02_github/README.md) · `notebooks/00_comprobacion_entorno.ipynb` |
| 3 | Preprocesamiento del corpus | [guía](talleres/semana03_preprocesamiento/README.md) · `notebooks/01_preprocesamiento.ipynb` |

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
