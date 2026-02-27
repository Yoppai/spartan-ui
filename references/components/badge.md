# Badge Component

Permite que un componente parezca una insignia (badge/etiqueta).

## Instalación

```bash
ng g @spartan-ng/cli:ui badge
```

## Uso Básico

### Importación

```typescript
import { HlmBadgeImports } from '@spartan-ng/helm/badge';
```

### Template

```html
<span hlmBadge variant="default">Badge</span>
```

## Ejemplos

### Variantes

Usa la propiedad `variant` para cambiar el estilo de la insignia.

```typescript
import { ChangeDetectionStrategy, Component } from '@angular/core';
import { HlmBadgeImports } from '@spartan-ng/helm/badge';

@Component({
  selector: 'spartan-badge-variants',
  standalone: true,
  imports: [HlmBadgeImports],
  template: `
    <div class="flex flex-wrap gap-2">
      <span hlmBadge>Default</span>
      <span hlmBadge variant="secondary">Secondary</span>
      <span hlmBadge variant="destructive">Destructive</span>
      <span hlmBadge variant="outline">Outline</span>
      <span hlmBadge variant="ghost">Ghost</span>
    </div>
  `,
})
export class BadgeVariantsPreview {}
```

### Con Icono

```html
<span hlmBadge variant="secondary">
  <ng-icon name="lucideBadgeCheck" /> Verificado
</span>
```

### Con Spinner

```html
<span hlmBadge variant="outline">
  Cargando <hlm-spinner class="text-xs" />
</span>
```

### Como Enlace

```html
<a hlmBadge routerLink="/perfil">Perfil</a>
<a hlmBadge variant="secondary" href="https://spartan.ng" target="_blank">
  Spartan <ng-icon name="lucideArrowUpRight" />
</a>
```

### Colores Personalizados

Puedes personalizar los colores añadiendo clases de Tailwind.

```html
<span hlmBadge class="bg-blue-50 text-blue-700 dark:bg-blue-950 dark:text-blue-300">
  Azul Personalizado
</span>
```

## API Reference

### Helm (Estilos)

- `hlmBadge`: Directiva principal.
  - **Inputs**:
    - `variant`: `default` | `secondary` | `destructive` | `outline` | `ghost`.
