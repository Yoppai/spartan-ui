# Button Group Component

Muestra un grupo de botones relacionados.

## Instalación

```bash
ng g @spartan-ng/cli:ui button-group
```

## Uso Básico

### Importación

```typescript
import { HlmButtonGroupImports } from '@spartan-ng/helm/button-group';
import { HlmButtonImports } from '@spartan-ng/helm/button';
```

### Template

```html
<div hlmButtonGroup aria-label="Grupo de botones">
  <button hlmBtn variant="outline">Boton 1</button>
  <button hlmBtn variant="outline">Boton 2</button>
  <button hlmBtn variant="outline">Boton 3</button>
</div>
```

## Ejemplos

### Orientación Vertical

```html
<div hlmButtonGroup orientation="vertical">
  <button hlmBtn variant="outline">Arriba</button>
  <button hlmBtn variant="outline">Abajo</button>
</div>
```

### Grupos Anidados (Pagination style)

```html
<div hlmButtonGroup>
  <div hlmButtonGroup>
    <button hlmBtn variant="outline" size="sm">1</button>
    <button hlmBtn variant="outline" size="sm">2</button>
  </div>
  <div hlmButtonGroup>
    <button hlmBtn variant="outline" size="icon-sm">Next</button>
  </div>
</div>
```

### Con Separador

Usa `hlm-button-group-separator` para dividir botones visualmente, especialmente en variantes que no tienen borde propio como `secondary`.

```html
<div hlmButtonGroup>
  <button hlmBtn variant="secondary">Copiar</button>
  <hlm-button-group-separator />
  <button hlmBtn variant="secondary">Pegar</button>
</div>
```

### Split Button

```html
<div hlmButtonGroup>
  <button hlmBtn variant="secondary">Acción Principal</button>
  <hlm-button-group-separator />
  <button hlmBtn variant="secondary" size="icon">
    <ng-icon name="lucideChevronDown" />
  </button>
</div>
```

### Input Group (Con Texto e Input)

```html
<div hlmButtonGroup>
  <span hlmButtonGroupText>https://</span>
  <input hlmInput placeholder="dominio.com" />
  <button hlmBtn variant="outline">Suscribirse</button>
</div>
```

## API Reference

### Helm (Estilos)

- `hlmButtonGroup`: Directiva contenedora.
  - **Inputs**: `orientation` (`horizontal` | `vertical`).
- `hlm-button-group-separator`: Componente divisor.
- `hlmButtonGroupText`: Directiva para texto decorativo dentro del grupo.
