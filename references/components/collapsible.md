# Collapsible Component

Componente interactivo que expande o colapsa un panel.

## Instalación

```bash
ng g @spartan-ng/cli:ui collapsible
```

## Uso Básico

### Importación

```typescript
import { HlmCollapsibleImports } from '@spartan-ng/helm/collapsible';
```

### Template

```html
<hlm-collapsible>
  <button hlmCollapsibleTrigger hlmBtn variant="outline">
    ¿Puedo usar esto en mi proyecto?
  </button>
  <hlm-collapsible-content>
    Sí. Es libre para proyectos personales y comerciales.
  </hlm-collapsible-content>
</hlm-collapsible>
```

## Ejemplos

### Animado con Tailwind

Puedes usar el estado `data-state` para controlar animaciones suaves.

```html
<hlm-collapsible>
  <button hlmCollapsibleTrigger hlmBtn variant="ghost" size="icon">
    <ng-icon name="lucideChevronsUpDown" />
  </button>
  <hlm-collapsible-content 
    class="transition-all ease-out data-[state=closed]:scale-80 data-[state=closed]:opacity-0"
  >
    Contenido animado aquí.
  </hlm-collapsible-content>
</hlm-collapsible>
```

## API Reference

### Helm (Estilos)

- `hlm-collapsible`: Contenedor principal.
- `hlmCollapsibleTrigger`: Directiva para el disparador (botón).
- `hlm-collapsible-content`: Contenedor del contenido que se oculta/muestra.

### Brain (Lógica)

- `brn-collapsible`: Primitiva lógica.
- `brnCollapsibleTrigger`: Gestiona el evento de toggle.
- `brn-collapsible-content`: Gestiona la visibilidad y accesibilidad (aria-expanded).
