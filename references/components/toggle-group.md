# Toggle Group Component

Grupo de botones de dos estados (toggles) que permiten seleccionar una o varias opciones.

## Instalación

```bash
ng g @spartan-ng/cli:ui toggle-group
```

## Uso Básico

### Importación

```typescript
import { HlmToggleGroupImports } from '@spartan-ng/helm/toggle-group';
```

### Template

```html
<hlm-toggle-group type="single">
  <button hlmToggleGroupItem value="a">Opción A</button>
  <button hlmToggleGroupItem value="b">Opción B</button>
  <button hlmToggleGroupItem value="c">Opción C</button>
</hlm-toggle-group>
```

## Ejemplos

### Selección Múltiple con Outline

```html
<hlm-toggle-group type="multiple" variant="outline">
  <button hlmToggleGroupItem value="bold" aria-label="Negrita">
    <ng-icon hlm name="lucideBold" />
  </button>
  <button hlmToggleGroupItem value="italic" aria-label="Cursiva">
    <ng-icon hlm name="lucideItalic" />
  </button>
</hlm-toggle-group>
```

### Tamaños (Small / Large)

```html
<hlm-toggle-group size="sm">
  <button hlmToggleGroupItem value="1">1</button>
  <button hlmToggleGroupItem value="2">2</button>
</hlm-toggle-group>
```

## API Reference

### Helm (Estilos)

- `hlm-toggle-group`: Contenedor principal.
  - **Inputs**: `type` (`single` | `multiple`), `variant` (`default` | `outline`), `size` (`default` | `sm` | `lg`).
- `hlmToggleGroupItem`: Directiva aplicada a los botones internos.

### Brain (Lógica)

- `BrnToggleGroup`: Gestiona la selección exclusiva o múltiple y los valores del grupo.
- `BrnToggleGroupItem`: Lógica individual de cada botón de opción.
