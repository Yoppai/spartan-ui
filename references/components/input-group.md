# Input Group Component

Grupo de entrada flexible que combina inputs con complementos (addons), prefijos y sufijos.

## Instalación

```bash
ng g @spartan-ng/cli:ui input-group
```

## Uso Básico

### Importación

```typescript
import { HlmInputGroupImports } from '@spartan-ng/helm/input-group';
```

### Template (Buscador con Icono)

```html
<div hlmInputGroup>
  <input hlmInputGroupInput placeholder="Buscar..." />
  <div hlmInputGroupAddon>
    <ng-icon name="lucideSearch" />
  </div>
</div>
```

## Ejemplos

### Múltiples Complementos (Addons)

```html
<div hlmInputGroup>
  <input hlmInputGroupInput placeholder="Número de tarjeta" />
  <div hlmInputGroupAddon>
    <ng-icon name="lucideCreditCard" />
  </div>
  <div hlmInputGroupAddon align="inline-end">
    <ng-icon name="lucideCheck" class="text-green-500" />
  </div>
</div>
```

### Con Botones

```html
<div hlmInputGroup>
  <input hlmInputGroupInput placeholder="Email..." />
  <button hlmInputGroupButton hlmBtn variant="outline">Suscribirse</button>
</div>
```

## API Reference

### Helm (Estilos)

- `hlmInputGroup`: Directiva para el contenedor principal.
- `hlmInputGroupInput`: Directiva para el `<input>` dentro del grupo.
- `hlmInputGroupAddon`: Directiva para contenedores de iconos o texto.
  - **Inputs**: `align` (`inline-start` | `inline-end`). Default: `inline-start`.
- `hlmInputGroupButton`: Directiva para botones integrados en el grupo.
- `hlmInputGroupText`: Para pequeños fragmentos de texto descriptivo.
- `hlmInputGroupTextarea`: Casos especiales para áreas de texto dentro de grupos.
