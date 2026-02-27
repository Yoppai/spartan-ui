# Progress Component

Muestra un indicador del progreso de una tarea, típicamente como una barra de progreso.

## Instalación

```bash
ng g @spartan-ng/cli:ui progress
```

## Uso Básico

### Importación

```typescript
import { HlmProgressImports } from '@spartan-ng/helm/progress';
```

### Template

```html
<hlm-progress value="33">
  <hlm-progress-indicator />
</hlm-progress>
```

## Animación Indeterminada (Indeterminate)

Para tareas donde no se conoce el progreso exacto.

```html
<hlm-progress value="0">
  <hlm-progress-indicator class="animate-indeterminate" />
</hlm-progress>
```

> [!IMPORTANT]
> La animación `animate-indeterminate` requiere importar `@spartan-ng/brain/hlm-tailwind-preset.css` en tus estilos globales o definir los keyframes manualmente en tu configuración de CSS.

## API Reference

### Helm (Estilos)

- `hlm-progress`: Contenedor de la barra.
  - **Inputs**: `value` (0-100).
- `hlm-progress-indicator`: Elemento visual que crece según el valor.

### Brain (Lógica)

- `BrnProgress`: Maneja los atributos `aria-valuenow`, `aria-valuemin` y `aria-valuemax`.
