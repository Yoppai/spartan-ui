# Scroll Area Component

Aumenta la funcionalidad de desplazamiento nativa para un estilo personalizado y coherente en todos los navegadores. Basado en `ngx-scrollbar`.

## Instalación

```bash
ng g @spartan-ng/cli:ui scroll-area
```

## Uso Básico

### Importación

```typescript
import { HlmScrollAreaImports } from '@spartan-ng/helm/scroll-area';
```

### Template

```html
<ng-scrollbar hlm class="h-72 w-48 rounded-md border" appearance="compact">
  <div class="p-4">
    <!-- Contenido largo aquí -->
    @for (tag of tags; track tag) {
      <div class="text-sm">{{ tag }}</div>
      <hlm-separator class="my-2" />
    }
  </div>
</ng-scrollbar>
```

## Ejemplos

### Desplazamiento Horizontal

```html
<ng-scrollbar hlm class="w-full whitespace-nowrap rounded-md border">
  <div class="flex w-max space-x-4 p-4">
     <!-- Elementos horizontales -->
  </div>
</ng-scrollbar>
```

## API Reference

### Helm (Estilos)

- `hlmScrollArea`: Directiva aplicada sobre el componente `ng-scrollbar`.
  - **Selectores**: `ng-scrollbar[hlm]`, `ng-scrollbar[hlmScrollbar]`.

### Dependencia Externa

Este componente envuelve `ngx-scrollbar`. Todas las propiedades nativas de `ngx-scrollbar` (como `appearance`, `visibility`, `track`) están disponibles.
