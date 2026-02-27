# Select Component

Control que permite al usuario alternar entre opciones en un menú desplegable. Construido sobre Material CDK Overlay.

## Instalación

```bash
ng g @spartan-ng/cli:ui select
```

## Uso Básico

### Importación

```typescript
import { BrnSelectImports } from '@spartan-ng/brain/select';
import { HlmSelectImports } from '@spartan-ng/helm/select';
```

### Template

```html
<brn-select placeholder="Selecciona una opción">
  <hlm-select-trigger class="w-[180px]">
    <hlm-select-value />
  </hlm-select-trigger>
  <hlm-select-content>
    <hlm-option value="apple">Manzana</hlm-option>
    <hlm-option value="banana">Plátano</hlm-option>
    <hlm-option value="blueberry">Arándano</hlm-option>
  </hlm-select-content>
</brn-select>
```

## Ejemplos

### Template de Valor Personalizado

```html
<hlm-select-value>
  <div class="flex items-center gap-2" *brnSelectValue="let value">
    <ng-icon [name]="value.icon" />
    {{ value.label }}
  </div>
</hlm-select-value>
```

## API Reference

### Helm (Estilos)

- `hlm-select-trigger`: El botón que abre el select.
- `hlm-select-content`: El panel desplegable.
- `hlm-option`: Una opción individual.
- `hlm-select-value`: Muestra el valor seleccionado.
- `hlm-select-group` / `hlm-select-label`: Para agrupar opciones.

### Brain (Lógica)

- `BrnSelect`: Lógica principal basada en `ListKeyManager`.
- `BrnSelectTrigger` / `BrnSelectContent`: Gestión de posición y accesibilidad.
