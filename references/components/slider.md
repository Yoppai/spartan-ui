# Slider Component

Entrada donde el usuario selecciona un valor o un rango de valores deslizando un tirador (thumb).

## Instalación

```bash
ng g @spartan-ng/cli:ui slider
```

## Uso Básico

### Importación

```typescript
import { HlmSliderImports } from '@spartan-ng/helm/slider';
```

### Template

```html
<hlm-slider [(ngModel)]="valor" [min]="0" [max]="100" />
```

## Ejemplos

### Selección de Rango (Range)

Usa un array de dos valores en los signals/variables.

```typescript
public readonly value = signal([25, 50]);
```

```html
<hlm-slider [(value)]="value" />
```

### Orientación Vertical

```html
<hlm-slider orientation="vertical" class="h-48" />
```

### Con Marcas (Ticks)

```html
<hlm-slider [showTicks]="true" [step]="10" />
```

## API Reference

### Helm (Estilos)

- `hlm-slider`: Componente principal que envuelve la lógica.
  - **Inputs**: `value`, `min`, `max`, `step`, `disabled`, `orientation`, `showTicks`.

### Brain (Lógica)

- `BrnSliderTrack`: El carril por el que se desliza.
- `BrnSliderRange`: Parte resaltada del carril.
- `BrnSliderThumb`: El tirador circular.
- `BrnSliderTick`: Marcas visuales de pasos.
