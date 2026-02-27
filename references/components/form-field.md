# Form Field Component

Añade capacidades de validación, pistas (hints) y estados de error a tus controles de formulario.

## Instalación

```bash
ng g @spartan-ng/cli:ui form-field
```

## Uso Básico

### Importación

```typescript
import { HlmFormFieldImports } from '@spartan-ng/helm/form-field';
import { HlmInputImports } from '@spartan-ng/helm/input';
```

### Template

```html
<hlm-form-field>
  <input hlmInput type="email" placeholder="Email" />
  <hlm-hint>Esta será tu dirección de contacto principal.</hlm-hint>
</hlm-form-field>
```

## Ejemplos

### Gestión de Errores (Error State)

Muestra un mensaje cuando el control es inválido.

```typescript
public name = new FormControl('', Validators.required);
```

```html
<hlm-form-field>
  <input [formControl]="name" hlmInput type="text" placeholder="Tu nombre" />
  <hlm-error>El nombre es obligatorio</hlm-error>
</hlm-form-field>
```

### Con Formularios Reactivos

```html
<form [formGroup]="form">
  <hlm-form-field>
    <input formControlName="email" hlmInput placeholder="Email" />
    <hlm-error>Email no válido</hlm-error>
  </hlm-form-field>
</form>
```

### ErrorStateMatcher (Personalización)

Puedes cambiar cuándo se muestran los errores (ej: al ensuciar el campo) usando el `ErrorStateMatcher`.

```typescript
import { ErrorStateMatcher, ShowOnDirtyErrorStateMatcher } from '@spartan-ng/brain/forms';

providers: [
  { provide: ErrorStateMatcher, useClass: ShowOnDirtyErrorStateMatcher }
]
```

## API Reference

### Helm (Estilos)

- `hlm-form-field`: Contenedor principal.
- `hlm-error`: Componente para mostrar mensajes de error.
- `hlm-hint`: Componente para mostrar pistas o ayudas.

### Brain (Lógica)

- `BrnFormField`: Gestiona la lógica de estado de error basada en el estado del control de formulario.
