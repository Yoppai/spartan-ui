# Button Component

Muestra un botón o un componente que parece un botón.

## Instalación

```bash
ng g @spartan-ng/cli:ui button
```

## Uso Básico

### Importación

```typescript
import { HlmButtonImports } from '@spartan-ng/helm/button';
```

### Template

```html
<button hlmBtn>Click aquí</button>
```

## Ejemplos

### Variantes

```html
<button hlmBtn>Primary</button>
<button hlmBtn variant="secondary">Secondary</button>
<button hlmBtn variant="destructive">Destructive</button>
<button hlmBtn variant="outline">Outline</button>
<button hlmBtn variant="ghost">Ghost</button>
<button hlmBtn variant="link">Link</button>
```

### Tamaños y Formas

```html
<button hlmBtn size="sm">Pequeño</button>
<button hlmBtn size="lg">Grande</button>
<button hlmBtn size="icon" class="size-8">
  <ng-icon name="lucideChevronRight" />
</button>
```

### Con Icono y Spinner

```html
<!-- Con Icono -->
<button hlmBtn variant="outline" size="sm">
  <ng-icon hlm size="sm" name="lucideGitBranch" /> Nueva Rama
</button>

<!-- Con Spinner -->
<button hlmBtn disabled>
  <hlm-spinner /> Cargando
</button>
```

### Como Enlace Externo (Anchor)

```html
<a hlmBtn href="https://github.com" target="_blank" variant="outline">
  GitHub
</a>
```

## API Reference

### Helm (Estilos)

- `hlmBtn`: Directiva principal.
  - **Inputs**:
    - `variant`: `default` | `secondary` | `destructive` | `outline` | `ghost` | `link`.
    - `size`: `default` | `sm` | `lg` | `icon`.

### Brain (Lógica)

- `brnButton`: Directiva primitiva para mayor accesibilidad y comportamiento base.
