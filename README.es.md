# 🧠 AI Skills — Una Guía Práctica
> De prompts a sistemas — aprende a construir skills reutilizables con IA.

🌍 Language:
[English](README.md) | [Português](README.pt-BR.md) | [Español](README.es.md)

Las skills son uno de los bloques fundamentales de los sistemas modernos de IA.

Permiten definir capacidades reutilizables y específicas para tareas que un sistema de IA puede aplicar automáticamente cuando es relevante — sin necesidad de repetir instrucciones cada vez.

⭐ Si este proyecto te ayudó, considera darle una estrella — ayuda a que otros lo descubran y apoya el trabajo.

## Skills Cheat Sheet

Una referencia visual rápida para entender cómo funcionan las skills — desde su estructura hasta su activación.

<img src="https://raw.githubusercontent.com/elisaterumi-ai/agent-skills-in-practice/main/img/skills-guide-spa.png" width="600"/>

> 💡 Úsalo como referencia rápida mientras construyes tus propias skills.

---

## Tabla de Contenidos

- [Qué son las Skills](#qué-son-las-skills)
- [Cómo Funcionan las Skills](#cómo-funcionan-las-skills)
- [Estructura de una Skill](#estructura-de-una-skill)
- [Dónde Viven las Skills](#dónde-viven-las-skills)
- [Skills vs Otras Personalizaciones](#skills-vs-otras-personalizaciones)
- [Cuándo Usar Skills](#cuándo-usar-skills)
- [Ejemplos de Uso](#ejemplos-de-uso)
- [Crear tu Primera Skill](#crear-tu-primera-skill)
- [Buenas Prácticas](#buenas-prácticas)
- [Errores Comunes](#errores-comunes)
- [Conceptos Avanzados](#conceptos-avanzados)
- [Por qué Importan las Skills](#por-qué-importan-las-skills)
- [Recursos](#recursos)
- [Reflexión Final](#reflexión-final)
- [Contribuir](#-contributing)
- [Conecta conmigo](#-connect-with-me)

---

## Qué son las Skills?

Una **skill** es un conjunto estructurado de instrucciones que enseña a un sistema de IA a realizar una tarea específica.

En Claude Code, una skill es:

- Un directorio  
- Que contiene un archivo `SKILL.md`  
- Con metadatos e instrucciones  

Una vez definida, el sistema puede descubrirla y usarla automáticamente.

> En lugar de repetir prompts, defines el comportamiento una vez — y lo reutilizas.

---

## Cómo Funcionan las Skills

Las skills siguen un flujo de **matching semántico**:

1. El sistema carga solo los **nombres y descripciones** de las skills  
2. Se recibe una solicitud del usuario  
3. El sistema compara la solicitud con las descripciones disponibles  
4. Se seleccionan las skills relevantes  
5. Se carga y ejecuta el contenido completo de la skill  

Esto significa:

- Las skills se cargan **bajo demanda**  
- **No saturan el contexto innecesariamente**  
- Se activan **solo cuando son relevantes**  

---

## Estructura de una Skill

Cada skill vive dentro de un directorio y debe contener un archivo `SKILL.md`.

### Ejemplo:

```yaml
---
name: pr-review
description: Revisa pull requests en términos de calidad de código y buenas prácticas. Usar al revisar PRs o cambios en el código.
---
```

Debajo del frontmatter, defines las instrucciones:

```yaml
Al revisar un PR:

Analizar los cambios en el código
Verificar buenas prácticas
Sugerir mejoras
Formatear la salida como feedback estructurado
```

---

## Dónde Viven las Skills

Las skills pueden existir en diferentes niveles:

### Skills Personales
- Ubicación: `~/.claude/skills`
- Disponibles en todos tus proyectos
- Ideales para flujos de trabajo personales

### Skills de Proyecto
- Ubicación: `.claude/skills` (dentro del repositorio)
- Compartidas mediante control de versiones
- Usadas como estándar del equipo

---

## Skills vs Otras Personalizaciones

| Feature           | Comportamiento         | Uso                         |
|-------------------|------------------------|------------------------------|
| **Skills**        | Carga bajo demanda     | Expertise específico         |
| **CLAUDE.md**     | Siempre cargado        | Reglas globales del proyecto |
| **Slash Commands**| Invocación manual      | Acciones explícitas          |

👉 Las skills son **automáticas y contextuales**

---

## Cuándo Usar Skills

Usa una skill cuando:

- Repites las mismas instrucciones frecuentemente
- Necesitas consistencia en la salida
- Quieres flujos reutilizables
- Deseas compartir conocimiento con tu equipo

**Regla general:**
> Si explicas lo mismo más de una vez, debería convertirse en una skill.

---

## Ejemplos de Uso

- Revisión de código  
- Formato de mensajes de commit  
- Plantillas de documentación  
- Checklists de debugging  
- Transformación de datos  
- Anonimización de textos clínicos  

👉 Explora skills listas para usar: [examples](examples)

> Algunos ejemplos están inspirados en repositorios open-source existentes.

---

## 🚀 Crear tu Primera Skill

### Paso 1 — Crear directorio

```bash
mkdir -p ~/.claude/skills/my-skill
```

### Paso 2 — Crear `SKILL.md` (o usar el template)

Crea un archivo `SKILL.md` dentro del directorio de tu skill, o cópialo desde el [template proporcionado](templates/skill-template.md).

```yaml
---
name: my-skill
description: Describe claramente qué hace la skill y cuándo debe usarse.
---
```

### Paso 3 — Añadir instrucciones

Define:

- Pasos  
- Reglas  
- Formato de salida  

---

## Buenas Prácticas

- Escribe **descripciones claras y específicas** (esto controla la activación)  
- Mantén las instrucciones **estructuradas y explícitas**  
- Define **formatos de salida esperados**  
- Evita skills demasiado genéricas  
- Mantén `SKILL.md` conciso (usa referencias si es necesario)  

---

## Errores Comunes

- Tratar las skills como simples prompts  
- Escribir descripciones vagas (la skill no se activará)  
- Sobrecargar una skill con múltiples responsabilidades  
- No definir la estructura de la salida  

---

## Conceptos Avanzados

### Campos de Metadatos

- `name` (obligatorio)  
- `description` (obligatorio)  
- `allowed-tools` (opcional)  
- `model` (opcional)  

### Progressive Disclosure

- Mantén la lógica principal en `SKILL.md`  
- Mueve contenido más extenso a:
  - `references/`  
  - `scripts/`  
  - `assets/`  

---

## Por qué Importan las Skills

Las skills transforman la forma en que construimos con IA:

- De **prompts → sistemas reutilizables**  
- De **instrucciones manuales → comportamiento automático**  
- De **experimentación → aplicaciones listas para producción**  

Son un bloque fundamental para:

- Agentes de IA  
- Pipelines de automatización  
- Sistemas escalables  

---

## Recursos

Enlaces, documentación y repositorios seleccionados:

👉 [Explorar recursos](docs/resources.md)

---

## Reflexión Final

Las skills cambian la forma de pensar:

> “¿Qué debería preguntarle al modelo?”

A:

> “¿Qué capacidad debería tener este sistema?”

---

## 🤝 Contribuir

¡Las contribuciones son bienvenidas!

Puedes ayudar:

- Añadiendo nuevas skills o casos de uso  
- Mejorando la documentación y los ejemplos  
- Reportando problemas o sugiriendo mejoras  

No dudes en abrir un issue o enviar un pull request 🚀

---

## 🔗 Conecta conmigo

Comparto insights prácticos sobre IA, agentes y aplicaciones en el mundo real:

- LinkedIn (Perfil): https://www.linkedin.com/in/elisa-terumi  
- LinkedIn (Página): https://www.linkedin.com/company/exploring-artificial-intelligence  
- Newsletter: https://exploringartificialintelligence.substack.com/  
- Medium: https://medium.com/@elisa-terumi
