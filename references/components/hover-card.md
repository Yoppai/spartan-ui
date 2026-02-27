# Hover Card Component

Permite a los usuarios videntes previsualizar el contenido disponible detrás de un enlace.

## Instalación

```bash
ng g @spartan-ng/cli:ui hover-card
```

## Uso Básico

### Importación

```typescript
import { HlmHoverCardImports } from '@spartan-ng/helm/hover-card';
```

### Template

```html
<hlm-hover-card>
  <button hlmBtn variant="link" hlmHoverCardTrigger>@spartan-ng</button>
  <hlm-hover-card-content *hlmHoverCardPortal>
    Una colección de componentes Angular open source construidos sobre Tailwind y CDK.
  </hlm-hover-card-content>
</hlm-hover-card>
```

## API Reference

### Helm (Estilos)

- `hlm-hover-card`: Componente contenedor.
- `hlmHoverCardTrigger`: Directiva para el elemento que activa el popover al pasar el mouse.
- `hlm-hover-card-content`: Contenedor del contenido que se muestra.
- `*hlmHoverCardPortal`: Directiva estructural necesaria para el renderizado del portal.

### Brain (Lógica)

- `BrnHoverCard`: Gestiona el retardo (delay) de apertura y cierre, y el posicionamiento.
- `BrnHoverCardTrigger`: Detecta los eventos de mouse enter/leave.
