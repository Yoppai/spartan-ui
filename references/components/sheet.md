# Sheet Component

Extiende el componente Dialog para mostrar contenido que complementa la pantalla principal, deslizándose desde un lateral.

## Instalación

```bash
ng g @spartan-ng/cli:ui sheet
```

## Uso Básico

### Importación

```typescript
import { HlmSheetImports } from '@spartan-ng/helm/sheet';
```

### Template

```html
<hlm-sheet>
  <button hlmSheetTrigger hlmBtn variant="outline">Abrir Menu</button>
  <hlm-sheet-content *hlmSheetPortal="let ctx">
    <hlm-sheet-header>
      <h3 hlmSheetTitle>Menu Lateral</h3>
      <p hlmSheetDescription>Navega a través de las opciones.</p>
    </hlm-sheet-header>
    <!-- Contenido -->
    <hlm-sheet-footer>
      <button hlmBtn hlmSheetClose>Cerrar</button>
    </hlm-sheet-footer>
  </hlm-sheet-content>
</hlm-sheet>
```

## Lados (Sides)

Puedes configurar desde dónde aparece el Sheet usando el input `side` en el trigger.

```html
<button hlmSheetTrigger side="left" hlmBtn>Desde Izquierda</button>
<button hlmSheetTrigger side="right" hlmBtn>Desde Derecha</button>
<button hlmSheetTrigger side="top" hlmBtn>Desde Arriba</button>
<button hlmSheetTrigger side="bottom" hlmBtn>Desde Abajo</button>
```

## API Reference

### Helm (Estilos)

- `hlm-sheet`: Contenedor principal.
- `hlm-sheet-content`: Contenedor del contenido deslizable.
- `hlmSheetTrigger`: Directiva para el botón disparador.
  - **Inputs**: `side` (`top` | `bottom` | `left` | `right`).
- `hlm-sheet-header` / `hlm-sheet-footer`: Secciones de estructura.
- `hlmSheetTitle` / `hlmSheetDescription`: Estilos de texto.

### Brain (Lógica)

- `BrnSheet`: Lógica de animación y superposición (overlay).
