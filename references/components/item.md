# Item Component

Componente versátil diseñado para mostrar cualquier tipo de contenido (título, descripción, acciones) de forma estructurada.

## Instalación

```bash
ng g @spartan-ng/cli:ui item
```

## Uso Básico

### Importación

```typescript
import { HlmItemImports } from '@spartan-ng/helm/item';
```

### Template

```html
<div hlmItem>
  <div hlmItemHeader>Cabecera del Item</div>
  <div hlmItemMedia>
    <ng-icon name="lucideUser" />
  </div>
  <div hlmItemContent>
    <div hlmItemTitle>Título del Item</div>
    <p hlmItemDescription>Esta es una descripción detallada del item.</p>
  </div>
  <div hlmItemActions>
    <button hlmBtn variant="outline" size="sm">Acción</button>
  </div>
  <div hlmItemFooter>Pie del Item</div>
</div>
```

## Variantes

### Outline y Muted

```html
<div hlmItem variant="outline"> ... </div>
<div hlmItem variant="muted"> ... </div>
```

## Item vs Field

- Usa **HlmField** si necesitas mostrar una entrada de formulario (checkbox, input, select).
- Usa **HlmItem** si solo necesitas mostrar contenido informativo, títulos y acciones.

## API Reference

### Helm (Estilos)

- `hlmItem`: Contenedor principal.
  - **Inputs**: `variant` (`default` | `outline` | `muted`).
- `hlmItemHeader` / `hlmItemFooter`: Secciones superior e inferior.
- `hlmItemMedia`: Espacio para iconos, avatares o imágenes.
- `hlmItemContent`: Envoltorio para título y descripción.
- `hlmItemTitle`: Estilo para el título principal.
- `hlmItemDescription`: Estilo para el texto secundario.
- `hlmItemActions`: Contenedor para botones o disparadores.
- `hlmItemGroup`: Para agrupar múltiples items.
- `hlmItemSeparator`: Línea divisoria entre items.
