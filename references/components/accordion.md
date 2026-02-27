# Accordion Component

Un conjunto de encabezados interactivos apilados verticalmente que revelan cada uno una sección de contenido.

## Instalación

```bash
ng g @spartan-ng/cli:ui accordion
```

## Uso Básico

### Importación

```typescript
import { HlmAccordionImports } from '@spartan-ng/helm/accordion';
import { HlmIconImports } from '@spartan-ng/helm/icon';
import { NgIcon } from '@ng-icons/core';
import { lucideChevronDown } from '@ng-icons/lucide';
```

### Template

```html
<hlm-accordion>
  <hlm-accordion-item>
    <h3 class="contents">
      <button hlmAccordionTrigger>
        ¿Es accesible?
        <ng-icon name="lucideChevronDown" hlm hlmAccIcon />
      </button>
    </h3>
    <hlm-accordion-content>
      Sí. Cumple con el patrón de diseño WAI-ARIA.
    </hlm-accordion-content>
  </hlm-accordion-item>
</hlm-accordion>
```

## Ejemplos

### Multiple and Opened

El input `type` se puede establecer en `'multiple'` para permitir que se abran varios elementos al mismo tiempo. El input `isOpened` se puede usar para establecer el estado inicial de un elemento del acordeón.

```html
<hlm-accordion type="multiple" class="pb-4">
  <hlm-accordion-item [isOpened]="true">
    <h3 class="contents">
      <button hlmAccordionTrigger>
        ¿Está abierto por defecto?
        <ng-icon name="lucideChevronDown" hlm hlmAccIcon />
      </button>
    </h3>
    <hlm-accordion-content>Sí, este item empieza abierto.</hlm-accordion-content>
  </hlm-accordion-item>
  
  <hlm-accordion-item>
    <h3 class="contents">
      <button hlmAccordionTrigger>
        ¿Puedo abrir varios?
        <ng-icon name="lucideChevronDown" hlm hlmAccIcon />
      </button>
    </h3>
    <hlm-accordion-content>Sí, porque el tipo es "multiple".</hlm-accordion-content>
  </hlm-accordion-item>
</hlm-accordion>
```

### Is it animated? (With Signals)

El acordeón está animado por defecto. Puedes controlar el estado mediante señales (signals).

```typescript
import { Component, signal } from '@angular/core';
import { NgIcon } from '@ng-icons/core';
import { HlmAccordionImports } from '@spartan-ng/helm/accordion';
import { HlmButtonImports } from '@spartan-ng/helm/button';
import { HlmIconImports } from '@spartan-ng/helm/icon';

@Component({
  selector: 'spartan-accordion-demo',
  standalone: true,
  imports: [HlmButtonImports, HlmAccordionImports, HlmIconImports, NgIcon],
  template: `
    <hlm-accordion type="multiple" class="pb-4">
      <hlm-accordion-item [isOpened]="thirdOpened()">
        <h3 class="contents">
          <button hlmAccordionTrigger>
            ¿Está animado?
            <ng-icon name="lucideChevronDown" hlm hlmAccIcon />
          </button>
        </h3>
        <hlm-accordion-content>
          Sí. Está animado por defecto, pero puedes desactivarlo si prefieres.
        </hlm-accordion-content>
      </hlm-accordion-item>
    </hlm-accordion>
    <button hlmBtn (click)="toggleThird()">Alternar Tercer Item</button>
  `,
})
export class AccordionDemo {
  protected readonly thirdOpened = signal(false);
  toggleThird() {
    this.thirdOpened.set(!this.thirdOpened());
  }
}
```

## API Reference

### Helm (Estilos)

- `hlm-accordion`: Contenedor principal. Soporta el input `type` (`single` | `multiple`).
- `hlm-accordion-item`: Envuelve cada sección. Soporta el input `isOpened` (boolean).
- `hlmAccordionTrigger`: Directiva para el botón que abre la sección.
- `hlm-accordion-content`: Contenedor del contenido revelado.
- `hlmAccordionIcon` / `hlmAccIcon`: Directiva para el icono de flecha.

### Brain (Lógica)

- `brn-accordion`: Primitiva lógica.
- `brnAccordionItem`: Controla el estado abierto/cerrado.
- `brn-accordion-content`: Gestiona la visibilidad y accesibilidad del contenido.
