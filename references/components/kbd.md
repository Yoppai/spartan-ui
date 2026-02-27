# KBD Component

Muestra entradas de texto del usuario provenientes del teclado (Keyboard keys).

## Instalación

```bash
ng g @spartan-ng/cli:ui kbd
```

## Uso Básico

### Importación

```typescript
import { HlmKbdImports } from '@spartan-ng/helm/kbd';
```

### Template

```html
<kbd hlmKbd>⌘</kbd>
<kbd hlmKbd>K</kbd>
```

## Ejemplos

### Agrupación (Kbd Group)

Para mostrar combinaciones de teclas.

```html
<kbd hlmKbdGroup>
  <kbd hlmKbd>Ctrl</kbd>
  <kbd hlmKbd>K</kbd>
</kbd>
```

### Dentro de un Botón

```html
<button hlmBtn variant="outline" size="sm" class="pr-2">
  Guardar <kbd hlmKbd>⏎</kbd>
</button>
```

### En un Input Group

```html
<div hlmInputGroup>
  <input hlmInputGroupInput placeholder="Buscar..." />
  <div hlmInputGroupAddon align="inline-end">
    <kbd hlmKbd>⌘</kbd>
    <kbd hlmKbd>K</kbd>
  </div>
</div>
```

## API Reference

### Helm (Estilos)

- `hlmKbd`: Directiva para aplicar estilos a elementos `<kbd>`.
- `hlmKbdGroup`: Directiva para envolver varios elementos `hlmKbd`.
