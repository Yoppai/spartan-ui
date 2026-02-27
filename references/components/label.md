# Label Component

Añade un aspecto distintivo y accesibilidad a las etiquetas de los elementos de formulario.

## Instalación

```bash
ng g @spartan-ng/cli:ui label
```

## Uso Básico

### Importación

```typescript
import { HlmLabelImports } from '@spartan-ng/helm/label';
```

### Template

```html
<label hlmLabel for="email">Correo electrónico</label>
<input hlmInput id="email" type="email" />
```

## Ejemplo con Checkbox

```html
<div class="flex items-center gap-2">
  <hlm-checkbox id="terms" />
  <label hlmLabel for="terms">Acepto los términos y condiciones</label>
</div>
```

## API Reference

### Helm (Estilos)

- `hlmLabel`: Directiva para aplicar estilos de Spartan a elementos `<label>`.

### Brain (Lógica)

- `BrnLabel`: Asegura que se generen IDs únicos y se gestione correctamente la relación con los inputs para lectores de pantalla.
