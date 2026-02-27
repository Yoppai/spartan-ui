# Switch Component

Control que permite al usuario alternar entre dos estados: activado o desactivado.

## Instalación

```bash
ng g @spartan-ng/cli:ui switch
```

## Uso Básico

### Importación

```typescript
import { HlmSwitch } from '@spartan-ng/helm/switch';
import { HlmLabel } from '@spartan-ng/helm/label';
```

### Template

```html
<label hlmLabel class="flex items-center gap-2">
  <hlm-switch id="airplane-mode" />
  Modo avión
</label>
```

## Ejemplos

### Con NgModel o Reactive Forms

```html
<hlm-switch [(ngModel)]="isNotificationsEnabled" />
```

## API Reference

### Helm (Estilos)

- `hlm-switch`: El componente de toggle principal.
  - **Inputs**: `disabled`, `checked`, `id`.
- `hlm-switch-thumb`: El círculo que se desplaza lateralmente.

### Brain (Lógica)

- `BrnSwitch`: Gestiona los estados de checked, tab index y la emisión del evento `checkedChange`.
