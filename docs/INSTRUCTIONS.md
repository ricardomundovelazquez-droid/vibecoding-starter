# Project Instructions

> Lee este archivo primero. Actualízalo conforme evoluciona el proyecto.
> Referenciarlo en Cursor con @INSTRUCTIONS.md al inicio de cada sesión.

## Proyecto
**Nombre:** [NOMBRE DEL PROYECTO]
**Tipo:** [SaaS / App interna / Sitio web / Herramienta]
**Descripción corta:** [1-2 oraciones — qué hace y para quién]
**URL producción:** [url de vercel cuando esté live]
**Supabase project ref:** [TU_PROJECT_REF]

---

## Stack — no negociable

| Capa | Tecnología |
|------|-----------|
| Framework | Next.js 15 (App Router) |
| Lenguaje | TypeScript strict |
| Estilos | Tailwind CSS v4 |
| Componentes | shadcn/ui + Magic UI |
| Base de datos | Supabase (PostgreSQL) |
| Auth | Supabase Auth |
| Storage | Supabase Storage |
| Deploy | Vercel |
| Estado global | Zustand |
| Estado servidor | TanStack Query |
| Formularios | React Hook Form + Zod |

**Sin Figma. Sin herramientas de diseño externas. Todo es vibecoding.**

---

## Estructura del proyecto

```
src/
├── app/              → rutas y páginas (App Router)
├── components/
│   ├── ui/           → shadcn/ui + Magic UI + customs
│   └── [feature]/    → componentes por feature
├── lib/
│   ├── supabase/     → server.ts, client.ts, types.ts
│   └── utils.ts      → cn() y helpers
├── hooks/            → custom hooks (use*.ts)
├── stores/           → Zustand (*.store.ts)
└── types/            → tipos globales
supabase/
├── migrations/       → SQL de migraciones
└── functions/        → Edge Functions
docs/
├── INSTRUCTIONS.md   ← este archivo
├── PRD.md            ← qué se construye y por qué
├── SCHEMA.md         ← esquema de DB actualizado
├── DECISIONS.md      ← decisiones técnicas y su justificación
└── flows/            ← user flows por feature
```

---

## Convenciones de código

| Elemento | Convención | Ejemplo |
|----------|-----------|---------|
| Componentes | PascalCase | `UserCard.tsx` |
| Hooks | camelCase con `use` | `useProjectData.ts` |
| Stores | camelCase con `.store` | `ui.store.ts` |
| Server Actions | camelCase en `actions.ts` | `createProject` |
| Tablas DB | snake_case plural | `user_profiles` |
| Idioma del código | inglés | variables, funciones |
| Idioma de la UI | [IDIOMA DEL PROYECTO] | copy visible |

---

## Reglas críticas (nunca romper)

1. RLS habilitado en TODAS las tablas de Supabase
2. Sin `any` en TypeScript — nunca
3. Server Components por defecto — `use client` solo cuando sea necesario
4. Mutaciones solo vía Server Actions (no fetch directo desde cliente)
5. Inputs de usuario siempre validados con Zod antes de la DB
6. `SUPABASE_SERVICE_ROLE_KEY` solo en servidor, nunca `NEXT_PUBLIC_`
7. Secrets nunca en código fuente
8. Regenerar `types.ts` de Supabase después de cada migración

---

## MCPs activos
- **Supabase MCP** → gestión de DB, migraciones, RLS, tipos
- **GitHub MCP** → commits y PRs desde el agente

---

## Entornos

| Entorno | Frontend | Base de datos |
|---------|----------|---------------|
| local | localhost:3000 | supabase start |
| preview | Vercel preview (por PR) | Supabase staging |
| production | Vercel main | Supabase prod |

---

## Usuarios del producto
[Describir los tipos de usuario principales — quiénes son y qué necesitan]

---

## Estado actual del proyecto
[Actualizar conforme avanza — qué está hecho, qué está en progreso]

- [ ] Setup inicial
- [ ] Auth (login / registro)
- [ ] Feature principal
