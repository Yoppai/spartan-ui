# Combobox Component

Entrada combinada con una lista de elementos predefinidos para seleccionar. Soporta búsqueda, filtrado y selección múltiple.

## Instalación

```bash
ng g @spartan-ng/cli:ui combobox
```

## Uso Básico

### Importación

```typescript
import { HlmComboboxImports } from '@spartan-ng/helm/combobox';
```

### Template (Selección Única)

```html
<hlm-combobox>
  <hlm-combobox-input placeholder="Selecciona un framework" />
  <hlm-combobox-content *hlmComboboxPortal>
    <hlm-combobox-empty>No se encontraron resultados.</hlm-combobox-empty>
    <div hlmComboboxList>
      @for (framework of frameworks; track framework.value) {
        <hlm-combobox-item [value]="framework">{{ framework.label }}</hlm-combobox-item>
      }
    </div>
  </hlm-combobox-content>
</hlm-combobox>
```

## Ejemplos

### Selección Múltiple con Chips

Usa `hlm-combobox-multiple` y `hlm-combobox-chips`.

```html
<hlm-combobox-multiple [(value)]="values">
  <hlm-combobox-chips>
    <ng-template hlmComboboxValues let-values>
      @for (value of values; track $index) {
        <hlm-combobox-chip [value]="value">{{ value }}</hlm-combobox-chip>
      }
    </ng-template>
    <input hlmComboboxChipInput />
  </hlm-combobox-chips>
  <hlm-combobox-content *hlmComboboxPortal>
     ... listado de items ...
  </hlm-combobox-content>
</hlm-combobox-multiple>
```

### Con Grupos y Etiquetas

```html
<div hlmComboboxList>
  @for (group of timezoneGroups; track group.name) {
    <div hlmComboboxGroup>
      <div hlmComboboxLabel>{{ group.name }}</div>
      @for (item of group.items; track item) {
        <hlm-combobox-item [value]="item">{{ item }}</hlm-combobox-item>
      }
    </div>
  }
</div>
```

### Búsqueda Asíncrona (Async Search)

Usa la directiva `[(search)]` y gestiona la carga de datos.

```html
<hlm-combobox [(search)]="search">
  <hlm-combobox-input placeholder="Buscar usuarios..." showClear />
  <hlm-combobox-content *hlmComboboxPortal>
    @if (loading()) {
      <hlm-combobox-status><hlm-spinner /> Cargando...</hlm-combobox-status>
    }
    <div hlmComboboxList>
       @for (user of users(); track user.id) {
         <hlm-combobox-item [value]="user">{{ user.name }}</hlm-combobox-item>
       }
    </div>
  </hlm-combobox-content>
</hlm-combobox>
```

## API Reference

### Helm (Estilos)

- `hlm-combobox`: Contenedor para selección única.
- `hlm-combobox-multiple`: Contenedor para selección múltiple.
- `hlm-combobox-input`: Campo de entrada de búsqueda.
- `hlm-combobox-chips`: Contenedor de chips para selección múltiple.
- `hlm-combobox-item`: Elemento de la lista.
- `hlmComboboxList`: Directiva para la lista de items.
- `hlmComboboxGroup` / `hlmComboboxLabel`: Para agrupar items.
- `hlm-combobox-empty`: Se muestra cuando no hay resultados.

### Brain (Lógica)

- `provideBrnComboboxConfig`: Permite configurar filtros globales y lógica de comparación.
