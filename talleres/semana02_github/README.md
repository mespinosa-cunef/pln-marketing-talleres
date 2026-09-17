# Taller · Repositorio y entorno de trabajo

Una hora. Al terminar, cada pareja debe tener un repositorio funcionando, con los dos
miembros trabajando sobre él y el notebook de comprobación ejecutado.

Si os atascáis en un paso, levantad la mano y seguid con el siguiente: casi todos son
independientes.

---

## Paso 1 · Crear el repositorio · 10 min

**Lo hace una sola persona de la pareja.**

1. En GitHub, arriba a la derecha: **New repository**.
2. Nombre: `pln-marketing-<vuestros-apellidos>`. Sin espacios ni acentos.
3. Visibilidad: **Private**.
4. Marcad **Add a README file**.
5. **Create repository**.

Luego, en `Settings` → `Collaborators` → **Add people**, añadid a dos personas:

- **el otro miembro** de la pareja, con permiso de escritura;
- **la profesora**, con permiso de escritura.

> Si no tenéis cuenta de GitHub todavía, creadla ahora con el **correo de la universidad**:
> da acceso al paquete de estudiante.

**Comprobación:** el otro miembro recibe la invitación por correo y la acepta. Hasta que no
la acepte, no puede tocar nada.

---

## Paso 2 · Copiar la estructura de la plantilla · 10 min

La profesora os pasa la carpeta `Plantilla_Proyecto`. Copiad su contenido a vuestro
repositorio. La forma más rápida desde el navegador: `Add file` → `Upload files`, arrastrar
todo y confirmar.

Esto es lo que estáis copiando y por qué:

| | |
|---|---|
| `README.md` | La portada del proyecto. **Se evalúa en cada hito.** |
| `.gitignore` | Impide subir claves y datos crudos. No lo toquéis. |
| `.env.example` | Plantilla para vuestras claves de API. |
| `requirements.txt` | Las librerías, con versión fijada. |
| `notebooks/` | Donde van los notebooks de los talleres. Cada semana se descarga el que toque. |
| `data/raw`, `clean`, `analytic` | Las tres capas de la clase de ayer. **No se suben.** |
| `data/sample/` | Una muestra pequeña que **sí** se sube, para que el proyecto se pueda reproducir. |
| `docs/bitacora.md` | El registro de decisiones. De aquí sale la memoria. |

**Por qué `data/raw` no se sube:** por tamaño y porque puede contener datos personales,
incluso en un repositorio privado.

---

## Paso 3 · Rellenar el README · 10 min

Abrid `README.md` y sustituid lo que está entre corchetes. Hoy no hace falta terminarlo:
completad al menos el nombre del equipo, el problema y el sistema que os proponéis
construir. El resto se rellena a medida que avancéis.

**Esto es lo que presentáis el miércoles**, así que lo que escribáis aquí es el borrador de
vuestra propuesta.

---

## Paso 4 · El ciclo completo, una vez · 15 min

Este es el paso importante del taller. **Lo hace el miembro que no creó el repositorio.**

1. En GitHub, entrad en `docs/bitacora.md` y pulsad el lápiz para editar.
2. Rellenad la primera entrada: la decisión sobre vuestro caso, aunque sea provisional.
3. Abajo, en lugar de confirmar directamente, elegid **Create a new branch** y ponedle un
   nombre, por ejemplo `bitacora-caso`. Confirmad.
4. GitHub os ofrece **Compare & pull request**. Pulsadlo y cread la pull request.
5. **Ahora cambia el turno:** el otro miembro entra, revisa los cambios en la pestaña
   `Files changed`, deja un comentario y pulsa **Merge pull request**.

Acabáis de hacer el ciclo que vais a repetir todo el curso: rama, cambio, revisión del
compañero, integración.

> **Por qué así y no subiendo cambios directamente:** el historial de commits documenta el
> trabajo de cada uno, y la revisión obliga a que ambos conozcáis todo el proyecto. En la
> defensa final se pregunta a cualquiera de los dos por cualquier parte.

---

## Paso 5 · El entorno: GitHub Codespaces · 10 min

El proyecto se desarrolla en el repositorio, así que el entorno también. Codespaces abre un
entorno completo en el navegador, sin instalar nada en vuestro equipo.

1. En vuestro repositorio: botón verde `Code` → pestaña **Codespaces** →
   **Create codespace on main**.
2. Cuando abra, en la terminal: `pip install -r requirements.txt`.
3. Abrid y ejecutad `notebooks/00_comprobacion_entorno.ipynb`.
4. Los cambios se confirman desde la pestaña de control de versiones, sin salir del navegador.

**Comprobación:** el notebook debe terminar con "Entorno correcto". Si alguna librería sale
como FALTA, instaladla con el comando que el propio notebook indica.

> Cerrad el codespace cuando terminéis: el nivel gratuito tiene un límite de horas al mes.

---

## Paso 6 · Antes de salir · 5 min

Repasad esta lista antes de salir.

- [ ] El repositorio existe y es privado.
- [ ] Los dos miembros y la profesora tenéis acceso, y las invitaciones están **aceptadas**.
- [ ] La estructura de carpetas está subida.
- [ ] El `README.md` tiene, al menos, equipo, problema y sistema.
- [ ] Hay **una pull request creada, revisada y fusionada**.
- [ ] El notebook de comprobación se ejecuta sin errores.
- [ ] En el historial aparecen commits de **las dos personas**.

---

## La regla que no se puede romper

**Las claves de acceso no se suben nunca al repositorio.**

Un token es una contraseña. Y una vez subido queda en el historial de git **aunque lo
borréis en el commit siguiente**: cualquiera con acceso al repositorio puede recuperarlo.

Por eso las claves van en un fichero `.env`, que `.gitignore` excluye. Cuando tengáis
claves de verdad:

```bash
cp .env.example .env      # y editad .env con vuestras claves
```

Si alguna vez subís una clave por error: **dadla por comprometida y revocadla** en la
plataforma. Borrarla del repositorio no basta.

---

## Qué queda para el miércoles

El repositorio es solo la infraestructura. Lo que se presenta el miércoles es la
**propuesta de proyecto**: de cinco a ocho minutos por equipo, y cuenta un 5%.

Para llegar con ella hay que hacer esta semana, fuera de clase:

1. Cerrar el problema y el sistema que vais a construir.
2. Elegir la fuente de datos y **comprobar que funciona de verdad**, no en teoría.
3. Extraer una primera muestra y guardarla en `data/sample/`.
4. Anotar en la bitácora qué fuente, qué limitaciones y qué hay que mirar de protección
   de datos.

Si a mitad de semana la fuente no funciona, escribid **el jueves o el viernes**, no el lunes
por la noche.
