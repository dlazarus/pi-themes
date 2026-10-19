# pi-themes

Colección de **7 temas de color** para [pi](https://pi.dev) (`@earendil-works/pi-coding-agent`).
Se distribuyen como **paquete de pi**: los instalas desde GitHub y aparecen directamente
en el selector de temas, sin copiar ficheros a mano.

## Los temas

| Tema | Estilo | Acento |
| --- | --- | --- |
| `deep-blue` | Azul profundo, frío y legible | `#4dd8ff` |
| `deep-green` | Verde bosque sobre fondos oscuros | `#4dd8a8` |
| `matrix` | Verde fósforo sobre negro, terminal clásica | `#00ff41` |
| `midnight` | Azul noche sobrio, tipo Tokyo Night | `#7aa2f7` |
| `sunset` | Tonos cálidos (melocotón, coral, ámbar) | `#f4a988` |
| `vaporwave` | Rosa, cian y púrpura neón sobre violeta | `#ff71ce` |
| `colorful` | Arcoíris: cada rol de la interfaz, un color | `#ff5fa2` |

Todos los temas están diseñados para **terminales oscuras** y declaran el
[schema oficial de pi](https://pi.dev/schemas/theme.schema.json), así que tu editor
los valida y autocompleta.

---

## Requisitos

- **pi coding agent** instalado (`pi` en el PATH).

---

## Instalación

### Vía recomendada (paquete de pi desde GitHub)

```bash
pi install git:github.com/dlazarus/pi-themes
```

Para fijar una versión concreta (recomendado si quieres estabilidad):

```bash
pi install git:github.com/dlazarus/pi-themes@v0.1.0
```

Se instala en tu agente personal (`~/.pi/agent/settings.json`) y los temas quedan
disponibles en **cualquier** carpeta en la que abras pi. Para actualizar:
`pi update --extensions`. Para quitarlo: `pi remove git:github.com/dlazarus/pi-themes`.

### Otras vías

```bash
# Probarlos una sola vez sin instalarlos
pi -e git:github.com/dlazarus/pi-themes

# Copia manual: los JSON son autocontenidos
git clone https://github.com/dlazarus/pi-themes
mkdir -p ~/.pi/agent/themes
cp pi-themes/themes/*.json ~/.pi/agent/themes/
# y dentro de pi:  /reload
```

> Los temas son solo JSON: no ejecutan código. Aun así, revisa siempre el código
> de cualquier paquete antes de instalarlo.

> **Nota si el repositorio es privado**: la instalación vía git requiere tu
> autenticación en GitHub (por ejemplo `gh auth login`, o usar la URL SSH
> `git:git@github.com:dlazarus/pi-themes`). La copia manual con `git clone`
> funciona con cualquier método que ya uses para clonar tus repos privados.

---

## Uso

### Elegir un tema

Abre `/settings` y selecciona **Theme**. La elección se guarda en
`~/.pi/agent/settings.json` como `"theme": "midnight"`, por ejemplo.

```bash
# O elegirlo solo para una invocación, sin tocar el ajuste guardado
pi --use-theme vaporwave

# O un par claro/oscuro automático (primero claro, segundo oscuro)
pi --use-theme light/midnight
```

### Personalizar un tema

Copia el JSON que te guste a `~/.pi/agent/themes/mi-tema.json`, cambia el campo
`name` a `mi-tema` y ajusta los colores:

- `vars`: paleta reutilizable (hex, OKLCH, OKHSL o índices ANSI 0–255).
- `colors`: asigna cada color a un rol de la interfaz (`accent`, `border*`,
  `toolPendingBg`, `md*`, `syntax*`…).

Si editas el tema **activo** desde `~/.pi/agent/themes/<name>.json`, pi lo
recarga en caliente; desde cualquier otro sitio, ejecuta `/reload`.

Pi valida los temas al arrancar y en `/reload`, y reporta los inválidos.

---

## Estructura del repositorio

```
pi-themes/
├── package.json          # manifiesto del paquete de pi (palabra clave: pi-package)
├── themes/
│   ├── colorful.json
│   ├── deep-blue.json
│   ├── deep-green.json
│   ├── matrix.json
│   ├── midnight.json
│   ├── sunset.json
│   └── vaporwave.json
├── CHANGELOG.md
└── LICENSE               # AGPL-3.0
```

---

## Licencia

AGPL-3.0-only — Copyright (C) 2026 dlazarus.

Este programa es software libre: puede redistribuirlo y/o modificarlo bajo los términos de la [GNU Affero General Public License](https://www.gnu.org/licenses/agpl-3.0.html) publicada por la Free Software Foundation (versión 3).

Se distribuye sin garantía de ningún tipo. Los trabajos derivados que se expongan a usuarios por una red deben publicar también su código fuente.
