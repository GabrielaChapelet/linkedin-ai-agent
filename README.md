# LinkedIn Content AI Agent 🚀

Agente automatizado diseñado para asistir en la estrategia de contenidos profesionales (*Build in Public*) en LinkedIn, enfocado en el sector del Desarrollo de Aplicaciones Web (DAW) y software de gestión empresarial (ERP/CRM).

El sistema implementa una arquitectura híbrida *Human-in-the-Loop*: el agente procesa ideas en bruto, aplica lógica de redacción técnica/negocio y genera borradores programados, manteniendo siempre la supervisión y validación humana previa a la publicación.

---

## 🎯 Objetivos del Proyecto

- **Consistencia de marca profesional:** Mantener presencia activa en LinkedIn documentando el aprendizaje técnico en DAW sin sobrecarga operativa diaria.
- **Enfoque en Lógica de Negocio:** Posicionar publicaciones que unan la operativa administrativa/empresarial con el desarrollo de software (Java, SQL, ERP/CRM).
- **Control de Calidad (Anti-Clichés IA):** Aplicar reglas estrictas de procesamiento de lenguaje para evitar tono robótico, adjetivos inflados o estructuras repetitivas.
- **Automatización Segura:** Integración mediante APIs oficiales en modo borrador (*Draft*), mitigando riesgos de publicación no supervisada.

---

## 🛠️ Arquitectura y Tecnologías

El flujo de trabajo se compone de herramientas gratuitas integradas sin coste de infraestructura:

| Módulo | Herramienta | Rol en el Sistema |
| :--- | :--- | :--- |
| **Canal de Entrada** | Telegram Bot API | Captura rápida de ideas, notas de voz o fragmentos de código desde el móvil. |
| **Orquestador** | Make / n8n | Enrutamiento de datos, control de flujo y conexión entre servicios. |
| **Motor de Lenguaje (LLM)** | Google Gemini API | Transformación de notas en bruto a publicaciones estructuradas según prompt maestro. |
| **Planificador** | Buffer API | Gestión del calendario editorial y almacenamiento en bandeja de borradores (*Drafts*). |
| **Supervisión** | Human-in-the-Loop | Revisión visual y aprobación final en 30 segundos previa a la publicación. |

---

## 📋 Directrices de Redacción (Prompt Engineering)

Para garantizar un tono auténtico, técnico y sin sesgo corporativo genérico, el agente opera bajo directrices estrictas:

- **Prohibición de clichés de IA:** Restricción de términos comodín como *«ahondar»*, *«crucial»*, *«apasionante»*, *«tapiz»* o fórmulas como *«no es solo X, sino Y»*.
- **Cero grandilocuencia:** Presentación de datos, errores y aprendizajes concretos de clase/proyectos; eliminación de adjetivos inflados.
- **Verbos directos y prosa fluida:** Uso de lenguaje activo y eliminación de listas mecánicas con negrita en cada línea.
- **Cierre constructivo:** Finalización con preguntas abiertas sobre arquitectura o procesos de negocio para fomentar el debate técnico.

---

## 📂 Estructura del Repositorio

```text
├── README.md               # Documentación general y arquitectura del proyecto
├── prompts/                # Directrices del sistema y plantillas de redacción
│   └── linkedin_prompt.md  # System prompt y reglas de estilo
├── blueprints/             # Exportación del flujo lógico (.json) para Make/n8n
└── docs/                   # Diagramas de arquitectura y capturas del flujo# linkedin-ai-agent
Agente automatizado para la creación y curación de contenidos en LinkedIn orientado a perfiles tecnológicos y software de gestión.
