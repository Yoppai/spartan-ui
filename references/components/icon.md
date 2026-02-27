# Icon Component

Señales visuales para mejorar la interacción del usuario. Basado en **ng-icons**.

## Instalación

```bash
ng g @spartan-ng/cli:ui icon
```

*Nota: Esto instalará `@ng-icons/core` y `@ng-icons/lucide` por defecto.*

## Uso Básico

### Importación

```typescript
import { HlmIcon } from '@spartan-ng/helm/icon';
import { NgIcon, provideIcons } from '@ng-icons/core';
import { lucideChevronRight } from '@ng-icons/lucide';

@Component({
  standalone: true,
  imports: [NgIcon, HlmIcon],
  providers: [provideIcons({ lucideChevronRight })],
  template: `
    <ng-icon hlm size="sm" name="lucideChevronRight" />
  `,
})
export class MyComponent {}
```

## Ejemplos

### Tamaños (Size)

Usa el input `size` para tamaños predefinidos o valores específicos.

```html
<ng-icon hlm size="sm" name="lucideChevronRight" />
<ng-icon hlm name="lucideChevronRight" /> <!-- base -->
<ng-icon hlm size="lg" name="lucideChevronRight" />
<ng-icon hlm size="xl" name="lucideChevronRight" />
<ng-icon hlm size="64px" name="lucideChevronRight" />
```

### Tamaño Responsivo

Puedes usar clases de Tailwind para ajustar el tamaño según el breakpoint.

```html
<ng-icon class="text-xl sm:text-4xl" name="lucideChevronRight" />
```

### Múltiples Conjuntos de Iconos

```typescript
import { lucideCircleArrowUp } from '@ng-icons/lucide';
import { remixAngularjsLine } from '@ng-icons/remixicon';

providers: [provideIcons({ lucideCircleArrowUp, remixAngularjsLine })],
```

## API Reference

### Helm (Estilos)

- `hlmIcon` (o simplemente `hlm` sobre `ng-icon`): Directiva para aplicar estilos Spartan.
  - **Inputs**:
    - `size`: `sm` | `base` | `lg` | `xl` | `string` (ej: `2rem`, `24px`).

## Iconos Disponibles

Spartan UI utiliza **Lucide** por defecto. Puedes explorar todos los iconos disponibles en la [documentación de Lucide](https://lucide.dev/icons).
