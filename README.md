# Motor SDD (Spec-Driven Development)

Motor de automatización basado en Ingeniería de Prompts para convertir especificaciones técnicas en Markdown (`.md`) a matrices de requerimientos estandarizadas en Excel (`.xlsx`). 

> **Nota para el equipo de Celestial:** Esta herramienta está optimizada para **VS Code + GitHub Copilot**. Al clonar este repositorio, el archivo de configuración `.github/copilot-instructions.md` se detectará automáticamente, permitiendo ejecutar el compilador sin configuraciones adicionales.

## ¿Qué resuelve esta herramienta?
Elimina la creación manual de matrices de requerimientos. Automatiza la extracción semántica de reglas de negocio, prioridades y criterios de aceptación, generando un libro de Excel profesional con formato corporativo, pestañas modulares por componente y ajuste dinámico de celdas.

## Modos de Uso

### Opción A: Modo Nativo (VS Code / Copilot) - **RECOMENDADO**
Para desarrolladores que buscan automatización total sin salir del editor:
1. Asegúrate de tener el archivo `.github/copilot-instructions.md` en la raíz de tu proyecto.
2. Invoque el chat de Copilot (`Ctrl + I` o `Ctrl + Alt + I`).
3. Escribe el comando: **"Ejecuta el compilador SDD para este archivo"**.
4. La IA procesará el Markdown y guardará el archivo `.xlsx` automáticamente en la raíz del proyecto.

### Opción B: Modo Rápido (Web - Claude)
Ideal para pruebas rápidas fuera del entorno de desarrollo:
1. Copia el contenido de `sdd_skill_v3.txt`.
2. Pégalo en un nuevo chat de Claude y arrastra tu archivo `.md`.
3. Descarga el Excel resultante desde el *Artifact* generado.

## Estructura del Markdown
Para una correcta compilación, utiliza la siguiente jerarquía en tus documentos:
```markdown
## Nombre del Módulo (Se convertirá en pestaña de Excel)
### Submódulo (Columna 'Componente')
- El sistema debe hacer X → Criterio de validación. Prioridad Alta.
