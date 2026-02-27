# Empty Component

Utilízalo para mostrar un estado vacío de forma elegante y consistente.

## Instalación

```bash
ng g @spartan-ng/cli:ui empty
```

## Uso Básico

### Importación

```typescript
import { HlmEmptyImports } from '@spartan-ng/helm/empty';
```

### Template

```html
<div hlmEmpty>
  <div hlmEmptyHeader>
    <div hlmEmptyMedia variant="icon">
      <ng-icon name="lucideFolderCode" />
    </div>
    <div hlmEmptyTitle>No hay proyectos aún</div>
    <div hlmEmptyDescription>
      No has creado ningún proyecto todavía. Empieza creando tu primer proyecto.
    </div>
  </div>
  <div hlmEmptyContent>
    <div class="flex gap-2">
      <button hlmBtn>Crear Proyecto</button>
      <button hlmBtn variant="outline">Importar Proyecto</button>
    </div>
  </div>
</div>
```

## Ejemplos

### Con Borde (Outline)

Usa clases de utilidad de borde para un estilo minimalista.

```html
<div hlmEmpty class="border border-dashed">
  <div hlmEmptyHeader>
     ...
  </div>
</div>
```

### Con Fondo Degradado (Background)

```html
<div hlmEmpty class="from-muted/50 to-background h-full w-full bg-gradient-to-b">
  ...
</div>
```

## API Reference

### Helm (Estilos)

- `hlmEmpty`: Contenedor principal.
- `hlmEmptyHeader`: Contenedor para el icono/media, título y descripción.
- `hlmEmptyMedia`: Contenedor para el elemento visual.
  - **Inputs**: `variant` (`icon` | `avatar` | `avatar-group`).
- `hlmEmptyTitle`: Estilo para el título.
- `hlmEmptyDescription`: Estilo para el texto de ayuda.
- `hlmEmptyContent`: Contenedor para acciones (botones, enlaces).
