# Spinner Component

Muestra un indicador de carga animado para informar al usuario que la aplicación está procesando algo.

## Instalación

```bash
ng g @spartan-ng/cli:ui spinner
```

## Uso Básico

### Importación

```typescript
import { HlmSpinnerImports } from '@spartan-ng/helm/spinner';
```

### Template

```html
<hlm-spinner />
```

## Personalización

### Tamaño y Color

Utiliza las clases estándar de Tailwind CSS de `text-size` y `text-color`.

```html
<hlm-spinner class="text-xs text-blue-500" />
<hlm-spinner class="text-4xl text-red-600" />
```

### Dentro de Botones

```html
<button hlmBtn disabled>
  <hlm-spinner class="mr-2" />
  Cargando...
</button>
```

## API Reference

### Helm (Estilos)

- `hlm-spinner`: Componente visual del spinner.
  - **Inputs**:
    - `icon`: string (default: `lucideLoader`). Requiere registro previo con `provideIcons`.
    - `aria-label`: string (default: `Loading`).
