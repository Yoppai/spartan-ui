# Toggle Component

Un botón de dos estados que puede encenderse o apagarse. Ideal para alternar preferencias visuales o selecciones simples.

## Instalación

```bash
ng g @spartan-ng/cli:ui toggle
```

## Uso Básico

### Importación

```typescript
import { HlmToggleImports } from '@spartan-ng/helm/toggle';
```

### Template

```html
<button hlmToggle aria-label="Toggle Bold">
  <ng-icon hlm name="lucideBold" />
</button>
```

## Variantes y Tamaños

### Outline con Texto

```html
<button hlmToggle variant="outline">
  <ng-icon hlm name="lucideItalic" class="mr-2" /> Cursiva
</button>
```

### Pequeño (Small)

```html
<button hlmToggle size="sm">Opción</button>
```

## API Reference

### Helm (Estilos)

- `hlmToggle`: Directiva aplicada a un botón.
  - **Inputs**:
    - `variant`: `default` | `outline`.
    - `size`: `default` | `sm` | `lg`.

### Brain (Lógica)

- `BrnToggle`: Gestiona el estado de `aria-pressed` y el ciclo de vida del click.
