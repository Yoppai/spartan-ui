# Textarea Component

Extensión del elemento `<textarea>` nativo o componente equivalente con estilos coherentes.

## Instalación

```bash
ng g @spartan-ng/cli:ui textarea
```

## Uso Básico

### Importación

```typescript
import { HlmTextareaImports } from '@spartan-ng/helm/textarea';
```

### Template

```html
<textarea hlmTextarea placeholder="Escribe tu mensaje aquí..."></textarea>
```

## Ejemplo con Label y Ayuda

```html
<div class="grid w-full gap-1.5">
  <label hlmLabel for="message">Mensaje</label>
  <textarea hlmTextarea id="message" placeholder="Escribe tu mensaje..."></textarea>
  <p class="text-sm text-muted-foreground">Tu mensaje será enviado al soporte técnico.</p>
</div>
```

## API Reference

### Helm (Estilos)

- `hlmTextarea`: Directiva aplicada a un elemento `<textarea>` para aplicar los estilos del sistema.
  - Soporta todos los atributos nativos: `disabled`, `rows`, `cols`, `placeholder`.
