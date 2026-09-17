# [Nombre del proyecto]

> Sustituid todo lo que esté entre corchetes. Este README es la portada del proyecto y
> se evalúa: es lo primero que se mira en cada hito.

**Equipo:** [Nombre 1] · [Nombre 2]
**Asignatura:** Procesamiento del Lenguaje Natural y sus aplicaciones en marketing (G260)
**Curso:** 2026-27

---

## El problema

[Una o dos frases: qué problema de marketing intentáis resolver. No "analizar la marca X",
sino una pregunta concreta que alguien podría querer responder.]

## El sistema que construimos

[Qué vais a construir, en tres o cuatro líneas. Qué entra, qué sale, y quién lo usaría.]

**Qué aporta frente a lo que ya existe:** [Herramientas comerciales que hacen algo parecido
—Brandwatch, Semrush, un LLM sin más— y en qué se diferencia lo vuestro.]

## Versión mínima y versión ambiciosa

- **Mínima:** [Lo que os comprometéis a entregar. Sobre esto se califica.]
- **Ambiciosa:** [Hasta dónde llegaríais si todo va bien.]

---

## Los datos

| | |
|---|---|
| **Fuente** | [API, dataset público, web…, con enlace] |
| **Procedencia** | [propios / de segunda mano / de terceros] |
| **Tamaño** | [nº de documentos] |
| **Periodo** | [desde – hasta] |
| **Idioma** | [ ] |
| **Fecha de recolección** | [ ] |

**Esquema de cada documento:**

| Campo | Tipo | Descripción |
|---|---|---|
| `texto` | textual | El texto del documento |
| `fecha` | formal | Fecha de publicación |
| `url` | formal | Origen, para poder volver a la fuente |
| | | |

**Limitaciones conocidas:** [Sesgo de selección, cobertura, huecos temporales, lo que sea.
Reconocerlas puntúa; ocultarlas, no.]

**Protección de datos:** [¿Hay datos personales? ¿Se puede identificar a alguien?
¿Con qué base los estáis usando?]

---

## Estructura del repositorio

```
data/raw/        Capa bruta: los datos tal como llegan. NO se sube al repositorio.
data/sample/     Muestra pequeña y anonimizada, sí versionada, para reproducir.
data/clean/      Capa limpia: sin duplicados, formatos estandarizados. No se sube.
data/analytic/   Capa analítica: agregados y resultados. No se sube.
notebooks/       Los notebooks, numerados en orden de ejecución.
docs/bitacora.md Registro de decisiones. De aquí sale la memoria final.
```

## Cómo ejecutarlo

1. [Colab: enlace al notebook · o Codespaces · o `pip install -r requirements.txt`]
2. Copiad `.env.example` a `.env` y poned vuestras claves. **`.env` no se sube.**
3. Ejecutad `notebooks/00_comprobacion_entorno.ipynb` para verificar que todo funciona.

## Uso de IA generativa

[Qué herramientas usáis y para qué. El detalle, con los prompts, va en `docs/bitacora.md`.]
