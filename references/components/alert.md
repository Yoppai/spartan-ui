# Alert Component

Muestra una llamada de atención para el usuario.

## Instalación

```bash
ng g @spartan-ng/cli:ui alert
```

## Uso Básico

### Importación

```typescript
import { HlmAlertImports } from '@spartan-ng/helm/alert';
// O importaciones individuales
import { 
  HlmAlert, 
  HlmAlertDescription, 
  HlmAlertIcon, 
  HlmAlertTitle 
} from '@spartan-ng/helm/alert';
```

### Template

```html
<div hlmAlert variant="default">
  <ng-icon hlm hlmAlertIcon name="lucideCircleCheck" />
  <h4 hlmAlertTitle>¡Éxito!</h4>
  <div hlmAlertDescription>Tus cambios han sido guardados correctamente.</div>
</div>
```

## Ejemplos

### Variante Destructiva

```html
<div hlmAlert variant="destructive">
  <ng-icon hlm hlmAlertIcon name="lucideTriangleAlert" />
  <h4 hlmAlertTitle>Error Inesperado</h4>
  <p hlmAlertDescription>Tu sesión ha expirado. Por favor, inicia sesión de nuevo.</p>
</div>
```

## API Reference

### Helm (Estilos)

- `hlmAlert`: Selector principal. Soporta el input `variant` (`default`, `destructive`).
- `hlmAlertIcon`: Directiva para el icono dentro de la alerta.
- `hlmAlertTitle`: Directiva para el título.
- `hlmAlertDescription` / `hlmAlertDesc`: Directiva para la descripción.
