# Separator Component

Separa el contenido visual o semánticamente de forma elegante.

## Instalación

```bash
ng g @spartan-ng/cli:ui separator
```

## Uso Básico

### Importación

```typescript
import { HlmSeparatorDirective } from '@spartan-ng/helm/separator';
```

### Template

```html
<div>
  <h4 class="text-sm font-medium">Descripción</h4>
  <div hlmSeparator class="my-4"></div>
  <p class="text-sm">Contenido inferior...</p>
</div>
```

## Ejemplos

### Orientación Vertical

```html
<div class="flex h-5 items-center space-x-4">
  <div>Blog</div>
  <div hlmSeparator orientation="vertical"></div>
  <div>Documentación</div>
</div>
```

## API Reference

### Helm (Estilos)

- `hlmSeparator`: Directiva para aplicar estilos a un div separador.
  - **Inputs**: `orientation` (`horizontal` | `vertical`).

### Brain (Lógica)

- `BrnSeparator`: Asegura el rol `separator` correcto y la orientación para lectores de pantalla.
  - **Inputs**: `decorative` (boolean, default: true).
