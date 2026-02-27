# Aspect Ratio Component

Muestra contenido dentro de una proporción deseada (ratio). Útil para imágenes, videos u otros elementos que deban mantener sus dimensiones relativas.

## Instalación

```bash
ng g @spartan-ng/cli:ui aspect-ratio
```

## Uso Básico

### Importación

```typescript
import { HlmAspectRatioImports } from '@spartan-ng/helm/aspect-ratio';
// O importación individual
import { HlmAspectRatioDirective } from '@spartan-ng/helm/aspect-ratio';
```

### Template

```html
<div class="max-w-xl overflow-hidden rounded-xl drop-shadow">
  <div [hlmAspectRatio]="16/9">
    <img alt="Vistas de montaña" src="/mountains.jpg" class="object-cover w-full h-full" />
  </div>
</div>
```

## API Reference

### Helm (Estilos)

- `[hlmAspectRatio]`: Directiva principal que se aplica a un contenedor.
  - **Input**: `ratio: number`. Define la proporción (ej. `16/9`, `4/3`, `1`).

### Consideraciones

- El elemento dentro del contenedor con `hlmAspectRatio` normalmente debe tener clases como `object-cover w-full h-full` si es una imagen o video para asegurar que llene el espacio correctamente.
