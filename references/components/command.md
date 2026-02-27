# Command Documentation

Menú de comandos rápido y componible para Angular, optimizado para ser usado como paleta de comandos.

## Instalación

```bash
ng g @spartan-ng/cli:ui command
```

## Uso Básico

### Importación

```typescript
import { HlmCommandImports } from '@spartan-ng/helm/command';
```

### Template

```html
<hlm-command class="rounded-lg border shadow-md">
  <hlm-command-input placeholder="Escribe un comando..." />
  <hlm-command-list>
    <div *hlmCommandEmptyState hlmCommandEmpty>No hay resultados.</div>
    <hlm-command-group>
      <hlm-command-group-label>Sugerencias</hlm-command-group-label>
      <button hlm-command-item value="Calendar">
        <ng-icon name="lucideCalendar" class="mr-2" /> Calendario
      </button>
      <button hlm-command-item value="Settings">
        <ng-icon name="lucideCog" class="mr-2" /> Ajustes
      </button>
    </hlm-command-group>
  </hlm-command-list>
</hlm-command>
```

## Ejemplos

### Command Dialog (Paleta de Comandos)

Ideal para abrirse con un atajo de teclado (ej: `⌘ + J`).

```html
<hlm-command-dialog [state]="state()" (stateChange)="stateChanged($event)">
  <hlm-command>
    <hlm-command-input placeholder="Buscar comandos..." />
    <hlm-command-list>
      <div *hlmCommandEmptyState hlmCommandEmpty>Nada encontrado.</div>
      <hlm-command-group>
        <button hlm-command-item (selected)="commandSelected('print')">Imprimir</button>
      </hlm-command-group>
    </hlm-command-list>
  </hlm-command>
</hlm-command-dialog>
```

### Como Combobox (Popover)

Puedes usar `hlm-command` dentro de un popover para crear un buscador de selección.

```html
<hlm-popover sideOffset="5">
  <button hlmPopoverTrigger hlmBtn variant="outline">Seleccionar...</button>
  <hlm-command *hlmPopoverPortal hlmPopoverContent class="p-0">
    <hlm-command-input placeholder="Buscar..." />
    <hlm-command-list>
      @for (item of items; track item.id) {
        <button hlm-command-item [value]="item.id">{{ item.label }}</button>
      }
    </hlm-command-list>
  </hlm-command>
</hlm-popover>
```

## API Reference

### Brain API

- `BrnCommandItem`:
  - **Inputs**: `value` (string), `disabled` (boolean).
  - **Outputs**: `selected` (emite cuando se elige el item).
- `BrnCommand`:
  - **Inputs**: `search` (string), `disabled` (boolean).

### Helm API

- `hlm-command`: Contenedor principal.
- `hlm-command-input`: Input de búsqueda integrado.
- `hlm-command-list`: Lista de resultados.
- `hlm-command-item`: Item seleccionable.
- `hlm-command-shortcut`: Estilo para mostrar atajos de teclado (ej: ⌘P).
- `hlm-command-dialog`: Wrapper para usar como diálogo modal.
