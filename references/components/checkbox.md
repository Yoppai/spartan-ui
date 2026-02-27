# Checkbox Component

Control que permite al usuario alternar entre marcado y no marcado.

## Instalación

```bash
ng g @spartan-ng/cli:ui checkbox
```

## Uso Básico

### Importación

```typescript
import { HlmCheckboxImports } from '@spartan-ng/helm/checkbox';
```

### Template

```html
<hlm-checkbox id="terms" />
<label hlmLabel for="terms">Acepto los términos y condiciones</label>
```

## Ejemplos

### Con Estados Iniciales y Deshabilitado

```html
<hlm-checkbox checked disabled />
```

### Integración con Formularios (Reactive Forms)

```typescript
public form = inject(FormBuilder).group({
  accept: [false],
});
```

```html
<form [formGroup]="form">
  <hlm-checkbox formControlName="accept" />
</form>
```

## API Reference

### Helm (Estilos)

- `hlm-checkbox`: Componente de checkbox con estilos Spartan.

### Brain (Lógica)

- `brn-checkbox`: Primitiva lógica que gestiona la accesibilidad y el estado.
