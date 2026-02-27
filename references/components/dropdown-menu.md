# Dropdown Menu Component

Muestra un menú al usuario — como un conjunto de acciones o funciones — activado por un botón.

## Instalación

```bash
ng g @spartan-ng/cli:ui dropdown-menu
```

## Uso Básico

### Importación

```typescript
import { HlmDropdownMenuImports } from '@spartan-ng/helm/dropdown-menu';
```

### Template

```html
<button [hlmDropdownMenuTrigger]="menu" hlmBtn>Mi Cuenta</button>

<ng-template #menu>
  <hlm-dropdown-menu class="w-56">
    <hlm-dropdown-menu-label>Cuenta</hlm-dropdown-menu-label>
    <hlm-dropdown-menu-separator />
    <hlm-dropdown-menu-group>
      <button hlmDropdownMenuItem>
        Perfil
        <hlm-dropdown-menu-shortcut>⇧⌘P</hlm-dropdown-menu-shortcut>
      </button>
      <button hlmDropdownMenuItem>Facturación</button>
    </hlm-dropdown-menu-group>
    <hlm-dropdown-menu-separator />
    <button hlmDropdownMenuItem [hlmDropdownMenuTrigger]="sub">
      Invitar usuarios
      <hlm-dropdown-menu-item-sub-indicator />
    </button>
  </hlm-dropdown-menu>
</ng-template>

<ng-template #sub>
  <hlm-dropdown-menu>
    <button hlmDropdownMenuItem>Email</button>
    <button hlmDropdownMenuItem>Mensaje</button>
  </hlm-dropdown-menu>
</ng-template>
```

## Ejemplos

### Checkboxes y Radio Groups

Puedes integrar estados de selección dentro del menú.

```html
<button hlmDropdownMenuCheckbox [checked]="showStatusBar" (triggered)="toggleStatus()">
  <hlm-dropdown-menu-checkbox-indicator />
  Barra de estado
</button>

<hlm-dropdown-menu-separator />

<hlm-dropdown-menu-group>
  @for (pos of positions; track pos) {
    <button hlmDropdownMenuRadio [checked]="pos === selected" (triggered)="selected = pos">
      <hlm-dropdown-menu-radio-indicator />
      {{ pos }}
    </button>
  }
</hlm-dropdown-menu-group>
```

## API Reference

### Helm (Estilos)

- `hlm-dropdown-menu`: Contenedor principal.
- `hlmDropdownMenuTrigger`: Directiva para el disparador.
- `hlmDropdownMenuItem`: Item individual.
- `hlm-dropdown-menu-label`: Etiqueta de sección.
- `hlm-dropdown-menu-separator`: Línea divisoria.
- `hlm-dropdown-menu-shortcut`: Texto para atajos de teclado.
- `hlmDropdownMenuCheckbox` / `Radio`: Items con estado de selección.
- `hlm-dropdown-menu-checkbox-indicator` / `radio-indicator`: Iconos de estado.
- `hlm-dropdown-menu-item-sub-indicator`: Icono de flecha para submenús.

### Brain (Lógica)

Basado en el CDK de Angular para la gestión de menús y accesibilidad.
