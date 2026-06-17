# Modulo 2 - SDD - Entrega

## Parte A
*Micro-tarea:* bugreport extractor tool
*Pilar 1 — Herramienta:* Voy a elegir Terminal-CLI Agentic
Elijo esta porque estoy creando un mini-proyecto de 0. Dado a que no tengo experiencia con Node.js y que se puede completar en poco tiempo (1/2 min max) creo que es la mejor opción.
*Pilar 2 — Contexto:* He mencionado que está dentro de un contenedor de docker vacío preparado con Node.js 20.22 he obviado detalles no relevantes como la estructura del docker-compose, como están montados los volumenes, etc
*Pilar 3 — Prompt:*
```md
You are inside an empty docker container with Node.js 20.22.
 
Implement a small generic bugreport extraction tool. It should be a cli tool configured with flags that extracts the bugreport and all compressed files inside the main one. The tool should recursivelly extract the file into the output directory and only keep the original bugreport compressed file, every other compressed file should be removed to keep the folder structure clean.

You are done when you are able to build the tool, and use it to extract an example bugreport created by yourself. The bugreport must be a .zip with multiple .tar.gz inside. each tar.gz must have different folder structures with some files you can just create empty.

- Don't implement any feature that has not been explicitly stated
- Command tool must be fast and reliable, showing usefull messages when failing.
- The tool is supposed to be a proof of concept, not a full on project. We don't need to unit test.

When in doubt, or if something unexpected happens, stop execution and ask me.
```

*Resultado:*
Comencé en modo Plan y a la segunda iteración le di permiso para comenzar.

Hubo un fallo en mitad de la ejecución en la que se dio cuenta de que no tenía algunas herramientas necesarias instaladas (`zip`), pero correctamente pausó la ejecución y preguntó como continuar como le dije en el promt. Tras eso todo fue fluido.

Si lo tuviese que volver a hacer usaría otro lenguaje que fuese yo más familiar para poder revisar y verificar el código más fácilmente. También creo que el prompt es mejorable.

## Parte B

```bash
root@81f677165ab8:/usr/src/app# openspec --version
1.4.1
root@81f677165ab8:/usr/src/app# tree
.
|-- Dockerfile
|-- ai4devs-openspect-sandbox-202606-roo
|   |-- ENTREGA.md
|   |-- README.md
|   `-- openspec
|       |-- changes
|       |   `-- archive
|       |-- config.yaml
|       `-- specs
|-- docker-compose.yml
|-- node_modules
`-- openspec
    |-- changes
    |   `-- archive
    |-- config.yaml
    `-- specs

11 directories, 6 files
root@81f677165ab8:/usr/src/app#
```

- Me sorpredió que en el comando de exploración tengan el uso de diagramas ASCII como parte del promt. En mi experiencia los diagramas no son el fuerte de los LLM.
- Parece que definir una sección de **Steps** es un estandar en este framework.
- No se si es estandar, pero me gusta que se definan opciones estandarizadas en el frontmatter de los skill aparte de el nombre y descripción:
---
license: MIT
compatibility: Requires openspec CLI.
metadata:
  author: openspec
  version: "1.0"
  generatedBy: "1.4.1"
--- 