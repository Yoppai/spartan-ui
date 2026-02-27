# Reactive Forms con Spartan UI

Guía exhaustiva para integrar componentes de Spartan UI con los Formularios Reactivos de Angular, utilizando la arquitectura de `hlm-field` para una gestión robusta de estados, validaciones y accesibilidad.

## Conceptos Clave

Spartan UI utiliza un enfoque composible donde el componente `<hlm-field>` actúa como el contenedor principal, coordinando la relación entre el control, su etiqueta, descripciones y mensajes de error.

### Anatomía de un Campo de Formulario

```html
<hlm-field>
  <label hlmFieldLabel for="username">Username</label>
  <input hlmInput id="username" formControlName="username" placeholder="Tu nombre de usuario" />
  <hlm-field-description>Nombre único para tu perfil público.</hlm-field-description>
  @if (form.controls.username.touched && form.controls.username.invalid) {
    <hlm-field-error>El nombre de usuario es obligatorio.</hlm-field-error>
  }
</hlm-field>
```

## Configuración y Setup

### 1. Importar Módulos

Asegúrate de importar `ReactiveFormsModule` y los componentes de Spartan correspondientes.

```typescript
import { ReactiveFormsModule, FormBuilder, Validators } from '@angular/forms';
import { HlmFieldImports } from '@spartan-ng/helm/field';
import { HlmInputImports } from '@spartan-ng/helm/input';
import { HlmButtonImports } from '@spartan-ng/helm/button';
```

### 2. Definir el Schema del Formulario

```typescript
form = this.fb.group({
  username: ['', [Validators.required, Validators.minLength(3)]],
  email: ['', [Validators.required, Validators.email]],
});
```

## Tipos de Campos Soportados

### Input (Texto, Email, Password)

```html
<hlm-field>
  <label hlmFieldLabel>Email</label>
  <input hlmInput formControlName="email" type="email" />
  <hlm-field-error>Introduce un email válido.</hlm-field-error>
</hlm-field>
```

### Textarea

```html
<hlm-field>
  <label hlmFieldLabel>Biografía</label>
  <textarea hlmTextarea formControlName="bio" placeholder="Cuéntanos sobre ti"></textarea>
  <hlm-field-description>Máximo 160 caracteres.</hlm-field-description>
  <hlm-field-error>La biografía es demasiado larga.</hlm-field-error>
</hlm-field>
```

### Select

```html
<hlm-field>
  <label hlmFieldLabel>Idioma</label>
  <brn-select formControlName="language" placeholder="Selecciona un idioma">
    <hlm-select-trigger>
      <hlm-select-value />
    </hlm-select-trigger>
    <hlm-select-content>
      <hlm-option value="es">Español</hlm-option>
      <hlm-option value="en">Inglés</hlm-option>
      <hlm-option value="fr">Francés</hlm-option>
    </hlm-select-content>
  </brn-select>
</hlm-field>
```

### Checkbox

Ideal para booleanos o aceptaciones de términos.

```html
<hlm-field class="flex items-center space-x-2">
  <hlm-checkbox id="terms" formControlName="terms" />
  <label hlmFieldLabel for="terms">Acepto los términos y condiciones</label>
</hlm-field>
```

### Radio Group

```html
<hlm-field>
  <hlm-radio-group formControlName="plan">
    <div class="flex items-center space-x-2">
      <hlm-radio value="free" id="free" />
      <label hlmFieldLabel for="free">Plan Gratuito</label>
    </div>
    <div class="flex items-center space-x-2">
      <hlm-radio value="pro" id="pro" />
      <label hlmFieldLabel for="pro">Plan Pro</label>
    </div>
  </hlm-radio-group>
</hlm-field>
```

### Switch

```html
<hlm-field class="flex items-center justify-between">
  <label hlmFieldLabel for="mfa">Autenticación de dos factores</label>
  <hlm-switch id="mfa" formControlName="mfa" />
</hlm-field>
```

## Validación y Errores

Spartan UI no maneja la lógica de validación (eso es responsabilidad de Angular), pero proporciona los estilos necesarios a través de `hlm-field-error`.

### Lógica Recomendada

Se recomienda mostrar errores solo cuando el campo ha sido "tocado" (`touched`) y es "inválido" (`invalid`).

```html
@if (form.controls.email.touched && form.controls.email.invalid) {
  <hlm-field-error>Email no válido</hlm-field-error>
}
```

## Acciones del Formulario

### Envío (Submit)

```html
<form [formGroup]="form" (ngSubmit)="onSubmit()">
  <!-- campos -->
  <button hlmBtn type="submit" [disabled]="form.invalid">Enviar</button>
</form>
```

### Reset
Al usar `form.reset()`, los componentes de Spartan UI volverán a su estado visual inicial (pueden cambiar el color del borde de rojo a gris, por ejemplo).

```typescript
resetForm() {
  this.form.reset();
}
```

## Demo: Formulario de Reporte de Errores Completo

```typescript
@Component({
  template: `
    <form [formGroup]="bugReportForm" (ngSubmit)="submit()" class="space-y-4">
      <hlm-field>
        <label hlmFieldLabel>Título del Error</label>
        <input hlmInput formControlName="title" />
        <hlm-field-error>El título es obligatorio.</hlm-field-error>
      </hlm-field>

      <hlm-field>
        <label hlmFieldLabel>Severidad</label>
        <brn-select formControlName="severity">
          <hlm-select-trigger class="w-full">
            <hlm-select-value />
          </hlm-select-trigger>
          <hlm-select-content>
            <hlm-option value="low">Baja</hlm-option>
            <hlm-option value="high">Alta</hlm-option>
          </hlm-select-content>
        </brn-select>
      </hlm-field>

      <hlm-field>
        <label hlmFieldLabel>Descripción</label>
        <textarea hlmTextarea formControlName="description"></textarea>
      </hlm-field>

      <div class="flex items-center space-x-2">
        <hlm-checkbox formControlName="urgent" />
        <label hlmFieldLabel>Marcar como urgente</label>
      </div>

      <button hlmBtn type="submit">Enviar Reporte</button>
    </form>
  `
})
```
