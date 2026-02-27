# Context Menu Component

Muestra un menú al usuario (como un conjunto de acciones) activado por un clic derecho.

## Instalación

```bash
ng g @spartan-ng/cli:ui context-menu
```

## Uso Básico

### Importación

```typescript
import { HlmContextMenuImports } from '@spartan-ng/helm/context-menu';
import { HlmDropdownMenuImports } from '@spartan-ng/helm/dropdown-menu';
```

### Template

```html
<div [hlmContextMenuTrigger]="menu" class="border p-10">
  Haz clic derecho aquí
</div>

<ng-template #menu>
  <hlm-dropdown-menu>
    <hlm-dropdown-menu-group>
      <button hlmDropdownMenuItem>Atrás</button>
      <button hlmDropdownMenuItem>Recargar</button>
      <hlm-dropdown-menu-separator />
      <button hlmDropdownMenuItem hlmDropdownMenuSubTrigger>Guardar como...</button>
    </hlm-dropdown-menu-group>
  </hlm-dropdown-menu>
</ng-template>
```

## Ejemplos

### Con Datos (Stateful)

Puedes pasar datos al disparador para usarlos dentro del menú.

```html
<div 
  [hlmContextMenuTrigger]="menu" 
  [hlmContextMenuTriggerData]="{ $implicit: { id: 123 } }"
  class="border p-20"
>
  Derecho sobre el item 123
</div>

<ng-template #menu let-ctx>
  <hlm-dropdown-menu>
    <button hlmDropdownMenuItem (click)="edit(ctx.id)">
      Editar ID: {{ ctx.id }}
    </button>
  </hlm-dropdown-menu>
</ng-template>
```

## API Reference

### Helm (Estilos)

- `[hlmContextMenuTrigger]`: Directiva para asignar el menú a un elemento.
- `[hlmContextMenuTriggerData]`: Directiva para inyectar contexto/datos al diálogo.

> [!NOTE]
> Este componente se apoya fuertemente en las directivas de **Dropdown Menu** para construir la interfaz del menú.
