# Estado de Trivia Croydonistas 2026

<!--start: description-->
Monitoreo y página de estado de producción de la Trivia Croydonistas 2026, con
[Upptime](https://upptime.js.org): GitHub Actions revisa cada servicio cada 5 minutos, cada caída
abre un issue (GitHub avisa por email a quien esté asignado) y la página se publica en GitHub
Pages. Todo gratis.
<!--end: description-->

## [📈 Estado en vivo](https://antisacsor.github.io/croydonista-status/): <!--live status--> **🟩 Todos los servicios en línea**

<!--start: status pages-->
<!--end: status pages-->

<!--start: docs-->
## Qué se monitorea

| Servicio | URL | Se considera caído si… |
| --- | --- | --- |
| API | `https://api.massivespace.pro/health` | no responde o falta `"status":"ok"` |
| Base de datos (Postgres) | `https://api.massivespace.pro/health` | falta `"db":true` |
| Caché y sesiones (Redis) | `https://api.massivespace.pro/health` | falta `"redis":true` |
| App de la participante | `https://trivia.massivespace.pro` | no responde o no trae la app (`<div id="root">`) |
| Panel de administración | `https://admin.massivespace.pro` | no responde con 401 (está tras autenticación básica de nginx) |

## Cómo funciona

- **Configuración:** solo `.upptimerc.yml`. Los workflows de `.github/workflows` son de la
  plantilla de Upptime; no se editan a mano.
- **Alertas:** cada caída abre un issue asignado a `pepe0062` y se cierra solo al recuperarse.
  Para recibir el email: GitHub → Settings → Notifications → "Issues" y "Actions" con email activo,
  y *Watch* en este repo.
- **Sin token personal:** todo usa el `GITHUB_TOKEN` del workflow. `Setup CI` y
  `Update Template CI` están desactivados. Para actualizar la plantilla, copiar `.github/` desde
  [upptime/upptime](https://github.com/upptime/upptime).
<!--end: docs-->
