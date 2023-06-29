# Flujos de trabajo en Git para trabajar en equipo

## Gitflow
Existen dos ramas principales que deben ser creadas al inicar el repositorio.

- Rama principal: contiene el código que se encuentra en producción
- Rama develop: sería el código de preproducción con características que todavía tienen que ser probadas pero que serán lanzadas en el próximo pase a producción. Una vez el código de esta rama sea estable, sus cambios serán incorporados a la rama principal (main) para crear una nueva versión de producción.
- Ramas de apoyo: se divide en tres:
  - Feautures: nuevas características
  - Release: preparación de una nueva versión
  - Hotfix

Gitflow es el estándar de facto, aunque ya no es tan popular.

Cada commit a la rama principal se refiere a una versión de producción

**Ventajas**
Todo está controlado

**Desventajas**
No es tan ágil

## Github flow
Pensada para equipos que hacen despliegues de forma regular. Se basa en la creación de pull request que luego serán discutidas para que se integren en la rama principal.

Tiene dos ramas:
- Rama principal: es la que contiene los cambios que se despliegan regularmente.
- Cualquier otra rama
Estas ramas se van a integrar en base a una acción que se llama pull request; es pedir que tus cambios se integren.

**Ventajas**
Se integra perfectamente con todo tipo de controles de revisión automatizada.

**Desventaja**
Vas a tardar un poquito, esperar el feedback de tus compañeros para poder integrar los cambios a producción.

## Trunk Based Development
Esta estrategia es la más antigua. Se basa en que el mayor tiempo de desarrollo se concentra en una sola rama llamada trunk (tronco), que correspondería a la rama principal de las estrategias anteriores.

Con esto se evita la creación de varias ramas auxiliares.

Deben existir redes de seguridad automatizadas que puedan deshacer un pase a producción en el caso de algo haya salido mal.

**Ventajas**
- Integración continua
- Menos fricción
- Menos trabajo manual

## Ship/Show/Ask
Despliega/Muestra/Pregunta

Es una estrategia de ramas que combina la idea de crear pull request de “Github Flow” y el trabajo de “Trunk Base Development”.

Con esto se podrás realizar cambios rápidamente y pedir feedback si lo consideras necesario.

- Ship: fusionas tus cambios rápidamente con la rama principal sin revisión
- Show: es abrir una petición de cambios para que sean revisados
- Ask: abre una PR para iniciar una discusión sobre los cambios antes de fusionarlos.
