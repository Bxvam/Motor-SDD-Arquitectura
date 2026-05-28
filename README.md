# Motor SDD (Spec-Driven Development) - v3.0

Un motor de compilación basado en Ingeniería de Prompts que transforma especificaciones técnicas redactadas en Markdown (`.md`) en matrices de requerimientos modulares en formato Excel (`.xlsx`), listas para QA y Arquitectura.

## ¿Qué resuelve esta herramienta?
La redacción manual de requerimientos en Excel es propensa a errores, recorta contexto técnico y consume horas de desarrollo. Este motor automatiza el proceso utilizando IA para leer el documento, entender la lógica de negocio, separar los criterios de aceptación y compilar un libro de Excel unificado mediante un script de Python ejecutado en la nube.

## Características Principales
- **100% Agnóstico:** Funciona con cualquier archivo `.md`.
- **Arquitectura Modular:** Transforma automáticamente los títulos principales (`##`) en pestañas individuales dentro del Excel.
- **Jerarquía Preservada:** Anida requerimientos bajo sus respectivos módulos (`###`).
- **Extracción Inteligente:** Aísla prioridades, clasifica los requerimientos (Funcional, No Funcional, Restricción, Hitos) y separa el criterio de aceptación o notas técnicas de forma automática.
- **Formato Industrial:** El Excel de salida se autogenera con colores corporativos, bordes, ajuste de texto (`wrap_text=True`) y anchos de columna dinámicos.

## Cómo utilizarlo en el equipo (Vía Claude)

Dado que en el equipo utilizamos Claude, el flujo de trabajo es inmediato gracias a su capacidad de ejecutar código (Artifacts/Analysis).

1. Abre un nuevo chat en **Claude**.
2. Copia todo el contenido del archivo `sdd_skill_v3.txt` incluido en este repositorio y pégalo como tu primer mensaje para inicializar el motor.
3. Arrastra tu documento `.md` al chat o pega el texto.
4. Claude analizará semánticamente el documento, escribirá un script de `openpyxl` en su servidor, y te devolverá un **archivo .xlsx único** listo para descargar.

## Estructura recomendada del documento Markdown
Para que el motor parsee correctamente tu documento, asegúrate de seguir esta estructura básica:

```md
## Nombre del Módulo (Se convertirá en pestaña)
### Submódulo o Pantalla (Se irá a la columna 'Componente')
- El sistema debe hacer X acción → Este es el criterio de validación. Prioridad Alta.
