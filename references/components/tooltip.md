# Tooltip Component

Mensaje emergente que muestra información adicional sobre un elemento al pasar el ratón o enfocar con el teclado.

## Instalación

```bash
ng g @spartan-ng/cli:ui tooltip
```

## Uso Básico

### Importación

```typescript
import { HlmTooltipImports } from '@spartan-ng/helm/tooltip';
```

### Template

```html
<button hlmTooltip="Añadir a favoritos" hlmBtn variant="outline">
  Favorito
</button>
```

## Ejemplos

### Posiciones Personalizadas

Puedes usar el input `position` para controlar dónde aparece el tooltip.

```html
<button hlmTooltip="Arriba" position="top" hlmBtn>Top</button>
<button hlmTooltip="Abajo" position="bottom" hlmBtn>Bottom</button>
<button hlmTooltip="Izquierda" position="left" hlmBtn>Left</button>
<button hlmTooltip="Derecha" position="right" hlmBtn>Right</button>
```

### Usando Plantillas (Template)

Para contenido rico con iconos o HTML complejo.

```html
<ng-template #tip>
  <div class="flex items-center gap-2">
    <ng-icon name="lucideInfo" />
    <span>Información detallada</span>
  </div>
</ng-template>

<button [hlmTooltip]="tip" hlmBtn>Info</button>
```

## API Reference

### Helm (Estilos)

- `hlmTooltip`: Directiva principal que aplica estilos y lógica.
  - **Inputs**:
    - `position`: `'top' | 'bottom' | 'left' | 'right'`.
    - `tooltipDisabled`: boolean.
    - `showDelay` / `hideDelay`: number (ms).

### Brain (Lógica)

- `BrnTooltip`: Gestión del trigger y el overlay dinámico.
