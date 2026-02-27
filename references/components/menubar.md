# Menubar Component

Menú persistente visualmente, común en aplicaciones de escritorio, que proporciona acceso rápido a comandos.

## Instalación

```bash
ng g @spartan-ng/cli:ui menubar
```

## Uso Básico

### Importación

```typescript
import { HlmMenubarImports } from '@spartan-ng/helm/menubar';
import { HlmDropdownMenuImports } from '@spartan-ng/helm/dropdown-menu';
```

### Template

```html
<hlm-menubar>
  <button [hlmMenubarTrigger]="fileMenu">Archivo</button>
  <button [hlmMenubarTrigger]="editMenu">Editar</button>
</hlm-menubar>

<ng-template #fileMenu>
  <hlm-dropdown-menu sideOffset="1.5">
    <button hlmDropdownMenuItem>Nueva pestaña</button>
    <button hlmDropdownMenuItem>Nueva ventana</button>
    <hlm-dropdown-menu-separator />
    <button hlmDropdownMenuItem>Imprimir</button>
  </hlm-dropdown-menu>
</ng-template>

<ng-template #editMenu>
  <hlm-dropdown-menu sideOffset="1.5">
    <button hlmDropdownMenuItem>Deshacer</button>
    <button hlmDropdownMenuItem>Rehacer</button>
  </hlm-dropdown-menu>
</ng-template>
```

## API Reference

### Helm (Estilos)

- `hlm-menubar`: Contenedor principal horizontal.
- `hlmMenubarTrigger`: Directiva para los botones de la barra que activan los menús.

> [!NOTE]
> Menubar utiliza internamente los mismos componentes y lógica que **Dropdown Menu** para sus submenús.
