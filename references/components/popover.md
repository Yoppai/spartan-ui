# Popover Component

Muestra contenido rico en un portal, activado por un botón. Ideal para formularios rápidos o información flotante.

## Instalación

```bash
ng g @spartan-ng/cli:ui popover
```

## Uso Básico

### Importación

```typescript
import { HlmPopoverImports } from '@spartan-ng/helm/popover';
```

### Template

```html
<hlm-popover>
  <button hlmPopoverTrigger hlmBtn variant="outline">Abrir Popover</button>
  <hlm-popover-content *hlmPopoverPortal="let ctx" class="w-80 p-4">
    <div class="grid gap-4">
      <h4 class="font-medium leading-none">Ajustes</h4>
      <p class="text-sm text-muted-foreground">Configura las dimensiones del panel.</p>
    </div>
  </hlm-popover-content>
</hlm-popover>
```

## API Reference

### Helm (Estilos)

- `hlm-popover`: Contenedor principal.
- `hlmPopoverTrigger`: Directiva para el elemento disparador.
- `hlm-popover-content`: Contenedor para el contenido flotante.
- `hlmPopoverPortal`: Directiva estructural para teletransportar el contenido al final del DOM.

### Brain (Lógica)

- `BrnPopover`: Gestiona el posicionamiento absoluto, clics fuera para cerrar y accesibilidad.
  - **Inputs**: `align`, `sideOffset`, `offsetX`.
