# Políticas de Pull Request y Gestión de Ramas

Este documento detalla las políticas y procedimientos para el manejo de pull requests (PR) y la gestión de ramas en nuestro repositorio.

---

## Conceptos Generales

### Ramas Principales

El repositorio del proyecto consta de tres ramas principales, cada una con un propósito específico:

- **`master`**: Representa el entorno de producción. Es la rama que contiene el código que está actualmente en producción.
- **`staging`**: Actúa como el entorno de pre-producción. Está configurado de manera idéntica al entorno de producción, excepto por las variables de entorno.
- **`dev`**: Sirve como el entorno de pruebas, donde se realizan todas las integraciones y pruebas de nuevas características o fixes.

### Política de Pull Requests

Para mantener la calidad y la integridad del código en las ramas principales, se establecen las siguientes políticas de pull request:

- **Inicio desde `dev`**: Todos los nuevos desarrollos se inician desde la rama `dev`. Los desarrolladores deben asegurarse que su rama local de `dev` está actualizada **antes** de crear una nueva rama.
  
- **Creación de Nuevas Ramas**: Al comenzar el trabajo en un nuevo ticket, se debe crear una nueva rama a partir de `dev`. Esta rama contendrá los cambios necesarios para resolver el ticket.

- **Uso de `rebase`**: Antes de crear un PR, **es necesario** hacer un `rebase` con `dev` para integrar y resolver localmente cualquier conflicto surgido por cambios en `dev`.

- **Revisión por el Technical Lead**: Una vez que el trabajo en la rama del ticket esté finalizado y el `rebase` realizado, se debe crear un pull request hacia `dev`. La persona indicada para resolver esta revisión será indicada en las reuniones de equipo. En su defecto, el Technical Leader será asignado como revisor de este PR.

- **Integración en `master` y `staging`**: Las ramas `master` y `staging` se reservan para los despliegues en sus correspondientes entornos. En estos momentos, la integración de `dev` a `staging`, y posteriormente de `staging` a `master` se realizará manualmente cuando se decida hacer una subida a producción.

---

### Prácticas Recomendadas

- **Pruebas locales**: El desarrollador debe de superar localmente las pruebas unitarias correspondientes y respetar las guías de estilo del código de los diferentes *linters* que afectan al proyecto.
- **Revisiones de Código**: Cada PR debe ser examinada detalladamente por el revisor asignado.
- **Comunicación Clara**: Cualquier comentario o sugerencia durante la revisión de código debe ser comunicado de manera clara y constructiva.
- **Documentación de Cambios**: Todas los PR deben incluir una descripción clara y detallada de los cambios realizados y su propósito.

---