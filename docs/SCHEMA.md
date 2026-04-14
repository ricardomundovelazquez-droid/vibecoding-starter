# Database Schema

> Actualizar después de cada migración. Fuente de verdad para el Supabase Agent.
> Regenerar tipos: `supabase gen types typescript --local > src/lib/supabase/types.ts`

## Tablas

### [nombre_tabla]
| Columna | Tipo | Constraints | Descripción |
|---------|------|-------------|-------------|
| id | UUID | PK, default gen_random_uuid() | ID único |
| user_id | UUID | FK auth.users, NOT NULL | Propietario |
| created_at | TIMESTAMPTZ | NOT NULL, default NOW() | Creación |
| updated_at | TIMESTAMPTZ | NOT NULL, default NOW() | Actualización |

**RLS Policies:**
- `users_own_data`: usuarios ven/modifican solo sus registros

**Relaciones:**
- `user_id` → `auth.users.id` CASCADE DELETE

---

## Diagrama de relaciones
```
auth.users (1) ──── (N) [tabla_1]
[tabla_1]  (1) ──── (N) [tabla_2]
```

## Historial de migraciones
| Fecha | Archivo | Descripción |
|-------|---------|-------------|
| | | |
