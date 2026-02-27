# Resizable Component

Grupo de paneles horizontales y verticales que el usuario puede redimensionar mediante tiradores (handles).

## Instalación

```bash
ng g @spartan-ng/cli:ui resizable
```

## Uso Básico

### Importación

```typescript
import { HlmResizableImports } from '@spartan-ng/helm/resizable';
```

### Template

```html
<hlm-resizable-group class="h-[200px] w-full rounded-lg border" direction="horizontal">
  <hlm-resizable-panel [defaultSize]="30">
    <div class="flex h-full items-center justify-center p-6">Panel 1</div>
  </hlm-resizable-panel>
  <hlm-resizable-handle />
  <hlm-resizable-panel [defaultSize]="70">
    <div class="flex h-full items-center justify-center p-6">Panel 2</div>
  </hlm-resizable-panel>
</hlm-resizable-group>
```

## Ejemplo Vertical

```html
<hlm-resizable-group direction="vertical">
  <hlm-resizable-panel>Arriba</hlm-resizable-panel>
  <hlm-resizable-handle />
  <hlm-resizable-panel>Abajo</hlm-resizable-panel>
</hlm-resizable-group>
```

## API Reference

### Helm (Estilos)

- `hlm-resizable-group`: Contenedor principal.
  - **Inputs**: `direction` (`horizontal` | `vertical`).
- `hlm-resizable-panel`: Un panel individual dentro del grupo.
  - **Inputs**: `defaultSize` (number), `minSize` (number), `maxSize` (number).
- `hlm-resizable-handle`: La barra que el usuario arrastra para redimensionar.

### Brain (Lógica)

- `BrnResizableGroup`: Gestiona la lógica de cálculo de tamaños y persistencia opcional.
- `BrnResizableHandle`: Gestiona los eventos de mouse y touch para el redimensionamiento.
