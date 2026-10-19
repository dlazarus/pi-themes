# CHANGELOG

## v0.1.0 — 2026-10-19

Primera versión publicable del proyecto. Empaqueta como **paquete de pi**
(instalable vía git) los siete temas de color que hasta ahora vivían sueltos
en el directorio de agente:

| Tema | Estilo |
| --- | --- |
| `deep-blue` | Azul profundo, frío y legible; acento cian (`#4dd8ff`). |
| `deep-green` | Verde bosque sobre fondos oscuros; acento verde-agua (`#4dd8a8`). |
| `matrix` | Verde fósforo sobre negro, estilo terminal clásica (`#00ff41`). |
| `midnight` | Azul noche sobrio, tipo Tokyo Night; acento azul lavanda (`#7aa2f7`). |
| `sunset` | Tonos cálidos (melocotón, coral, ámbar) sobre fondos oscuros rosados. |
| `vaporwave` | Rosa, cian y púrpura neón sobre violeta oscuro (`#ff71ce`). |
| `colorful` | Paleta arcoíris completa: cada rol de la interfaz, un color distinto. |

Todos los temas declaran el `$schema` oficial de pi, usan nombres de archivo
idénticos a su `name` y no dependen de ningún recurso externo: se pueden
copiar tal cual a `~/.pi/agent/themes/` o instalar como paquete.
