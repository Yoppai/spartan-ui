# Input Component

Campo de entrada profesional con estilos coherentes con el diseño de Spartan UI.

## Instalación

```bash
ng g @spartan-ng/cli:ui input
```

## Uso Básico

### Importación

```typescript
import { HlmInputImports } from '@spartan-ng/helm/input';
```

### Template

```html
<input hlmInput type="email" placeholder="Email" />
```

## Ejemplos

### Con Etiqueta (Label)

```html
<div class="grid w-full max-w-sm items-center gap-3">
  <label hlmLabel for="email">Email</label>
  <input hlmInput type="email" id="email" placeholder="email@ejemplo.com" />
</div>
```

### Tipo Archivo (File)

```html
<input hlmInput id="picture" type="file" />
```

### Deshabilitado (Disabled)

```html
<input hlmInput disabled type="text" placeholder="No editable" />
```

### Con Botón (Suscribirse)

```html
<div class="flex w-full max-w-sm items-center gap-2">
  <input hlmInput type="email" placeholder="Email" />
  <button hlmBtn variant="outline">Suscribirse</button>
</div>
```

## API Reference

### Helm (Estilos)

- `hlmInput`: Directiva principal para aplicar estilos a elementos `<input>`.
