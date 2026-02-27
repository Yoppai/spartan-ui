# Spartan UI Skill for AI Agents

Este repositorio contiene una **Skill** diseñada para agentes de IA (como Claude, GPT, etc.) que facilita la integración, configuración y desarrollo con [Spartan UI](https://spartan.ng/) en proyectos Angular.

## 🚀 ¿Qué es esta Skill?

Esta skill enseña a tu asistente de IA exactamente cómo trabajar con el ecosistema de Spartan UI. No es solo documentación; es un conjunto de instrucciones estructuradas que permiten al agente:

- **Instalar correctamente** las dependencias de Spartan (Brain y Helm).
- **Configurar Tailwind CSS v4** con el preset de Spartan.
- **Generar componentes** Helm y personalizarlos.
- **Implementar temas** dinámicos usando OKLCH.
- **Manejar formularios reactivos** siguiendo las mejores prácticas de Spartan.

## 🛠️ Estructura de la Skill

- `SKILL.md`: El cerebro de la skill. Contiene los flujos de trabajo, comandos de la CLI y guías de arquitectura.
- `references/components/`: Guías detalladas para +50 componentes (Accordion, Alert, Dialog, Table, etc.).
- `references/forms/`: Best practices para integración con `ReactiveForms`.

## 📦 Instalación (vía skills.sh)

Si usas el CLI de `skills`, puedes añadir este conocimiento a tu agente ejecutando:

```bash
npx skills add Yoppai/spartan-ui
```

## 📖 Cómo usarla

Una vez instalada en tu entorno de desarrollo, puedes pedirle a tu IA:

- *"Configura Spartan UI en mi nuevo proyecto Angular con Tailwind v4"*
- *"Ayúdame a crear una tabla de datos usando Spartan Helm"*
- *"¿Cómo implemento el modo oscuro usando el servicio de Spartan?"*
- *"Genera un formulario de login con los componentes Input y Button de Spartan"*

## 🤝 Contribuciones

Si encuentras formas de mejorar las instrucciones o quieres añadir ejemplos de nuevos componentes, ¡los PRs son bienvenidos!

---
Desarrollado para potenciar el desarrollo de Angular con IA. Basado en [spartan.ng](https://spartan.ng/).
