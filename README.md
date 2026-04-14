# Vibecoding Starter

Plantilla base para proyectos Next.js + Supabase + Vercel con sistema de agentes para Cursor.

## Setup en 5 pasos

### 1. Clonar y renombrar
```bash
git clone https://github.com/[tu-usuario]/vibecoding-starter.git mi-proyecto
cd mi-proyecto
```

### 2. Instalar dependencias
```bash
npm install
npx shadcn@latest init
```

### 3. Configurar variables de entorno
```bash
cp .env.example .env.local
# Editar .env.local con tus keys de Supabase
```

### 4. Configurar MCPs en Cursor
Editar `.cursor/mcp.json`:
- Reemplazar `TU_PROJECT_REF` con tu Supabase project ref
- Reemplazar `TU_GITHUB_TOKEN` con tu GitHub Personal Access Token

### 5. Completar docs/INSTRUCTIONS.md
Llenar los campos marcados con `[NOMBRE]`, `[DESCRIPCIÓN]`, etc.

---

## Cómo usar los agentes

### Iniciar cualquier task
```
@orchestrator [describe lo que quieres construir]
```
El orquestador crea el plan y activa los agentes necesarios en secuencia.

### Agentes disponibles
| Qué necesitas | Agente |
|---------------|--------|
| Definir flows o sitemap | `@ux-research` |
| Componentes UI | `@ui-design` |
| Copy de interfaz | `@copy` |
| Páginas Next.js | `@nextjs` |
| DB / Supabase | `@supabase` |
| Auth | `@auth` |
| Deploy / env vars | `@deploy` |
| Auditoría de calidad | `@auditors` |

### Modelo recomendado
Dejar en **Auto** — Cursor elige el modelo según la complejidad del task.
Esto maximiza la duración de tus tokens.

---

## Estructura de archivos importantes
```
.cursor/
├── mcp.json          → MCPs: Supabase + GitHub
└── rules/            → Agentes y reglas (no modificar)
docs/
├── INSTRUCTIONS.md   → Contexto del proyecto (LLENAR)
├── PRD.md            → Qué se construye (LLENAR)
├── SCHEMA.md         → Esquema DB (actualizar con cada migración)
└── DECISIONS.md      → Decisiones técnicas (ir completando)
```
