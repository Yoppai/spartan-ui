# Carousel Component

Un carrusel con movimiento y gestos táctiles, construido sobre **Embla Carousel**.

## Instalación

```bash
ng g @spartan-ng/cli:ui carousel
```

## Uso Básico

### Importación

```typescript
import { HlmCarouselImports } from '@spartan-ng/helm/carousel';
```

### Template

```html
<hlm-carousel>
  <hlm-carousel-content>
    <hlm-carousel-item>Item 1</hlm-carousel-item>
    <hlm-carousel-item>Item 2</hlm-carousel-item>
    <hlm-carousel-item>Item 3</hlm-carousel-item>
  </hlm-carousel-content>
  <button hlm-carousel-previous></button>
  <button hlm-carousel-next></button>
</hlm-carousel>
```

## Ejemplos

### Tamaños y Columnas

Usa clases de Tailwind como `basis` para controlar cuántos elementos se muestran.

```html
<hlm-carousel-item class="md:basis-1/2 lg:basis-1/3">
  ...
</hlm-carousel-item>
```

### Orientación Vertical

Soporta orientación vertical mediante la propiedad `orientation`.

```html
<hlm-carousel orientation="vertical" class="w-full max-w-xs">
  <hlm-carousel-content class="-mt-1 h-[200px]">
    <hlm-carousel-item class="pt-1 md:basis-1/2">
       ...
    </hlm-carousel-item>
  </hlm-carousel-content>
</hlm-carousel>
```

### Con Plugins (Autoplay)

Integración con plugins de Embla como Autoplay.

```typescript
import Autoplay from 'embla-carousel-autoplay';

export class MyComponent {
  public plugins = [Autoplay({ delay: 3000 })];
}
```

```html
<hlm-carousel [plugins]="plugins">...</hlm-carousel>
```

### Contador de Diapositivas

Muestra el índice actual y el total.

```html
<hlm-carousel>
  ...
  <hlm-carousel-slide-display />
</hlm-carousel>
```

## API Reference

### Helm (Estilos)

- `hlm-carousel`: Contenedor principal.
  - **Inputs**:
    - `orientation`: `horizontal` | `vertical`.
    - `options`: Opciones de Embla.
    - `plugins`: Plugins de Embla.
- `hlm-carousel-content`: Contenedor de los items.
- `hlm-carousel-item`: Item individual.
- `hlm-carousel-previous` / `hlm-carousel-next`: Botones de navegación.
- `hlm-carousel-slide-display`: Indicador de estado del slide.
