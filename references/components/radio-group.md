# Radio Group Component

Conjunto de botones de opción (radio buttons) donde solo uno puede estar seleccionado a la vez.

## Instalación

```bash
ng g @spartan-ng/cli:ui radio-group
```

## Uso Básico

### Importación

```typescript
import { HlmRadioGroupImports } from '@spartan-ng/helm/radio-group';
import { HlmLabelImports } from '@spartan-ng/helm/label';
```

### Template

```html
<hlm-radio-group>
  <div class="flex items-center gap-3">
    <hlm-radio value="opcion1" id="op1">
      <hlm-radio-indicator indicator />
    </hlm-radio>
    <label hlmLabel for="op1">Opción 1</label>
  </div>
  <div class="flex items-center gap-3">
    <hlm-radio value="opcion2" id="op2">
      <hlm-radio-indicator indicator />
    </hlm-radio>
    <label hlmLabel for="op2">Opción 2</label>
  </div>
</hlm-radio-group>
```

## API Reference

### Helm (Estilos)

- `hlm-radio-group`: Contenedor de las opciones.
- `hlm-radio`: Componente individual de radio.
  - **Inputs**: `value`, `id`, `disabled`.
- `hlm-radio-indicator`: El elemento visual (círculo) que indica si está seleccionado.

### Brain (Lógica)

- `BrnRadioGroup`: Gestiona la selección única, el valor del grupo y la navegación por teclado (flechas).
- `BrnRadio`: Lógica de cada opción individual.
