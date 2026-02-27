# Skeleton Component

Se utiliza para mostrar un marcador de posición (placeholder) mientras el contenido real se está cargando, mejorando la percepción de velocidad de la aplicación.

## Instalación

```bash
ng g @spartan-ng/cli:ui skeleton
```

## Uso Básico

### Importación

```typescript
import { HlmSkeletonImports } from '@spartan-ng/helm/skeleton';
```

### Template

```html
<div class="flex items-center space-x-4">
  <hlm-skeleton class="h-12 w-12 rounded-full" />
  <div class="space-y-2">
    <hlm-skeleton class="h-4 w-[250px]" />
    <hlm-skeleton class="h-4 w-[200px]" />
  </div>
</div>
```

## Ejemplos

### Esqueleto de Tarjeta (Card)

```html
<div class="flex flex-col space-y-3">
  <hlm-skeleton class="h-[125px] w-[250px] rounded-xl" />
  <div class="space-y-2">
    <hlm-skeleton class="h-4 w-[250px]" />
    <hlm-skeleton class="h-4 w-[200px]" />
  </div>
</div>
```

## API Reference

### Helm (Estilos)

- `hlm-skeleton`: Componente que aplica el color de fondo animado (pulse).
- `hlmSkeleton`: Directiva equivalente para aplicar a elementos nativos.
