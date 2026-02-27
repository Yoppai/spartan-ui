# Dialog Component

Una ventana superpuesta sobre la ventana principal u otra ventana de diálogo, que vuelve inerte el contenido subyacente.

## Instalación

```bash
ng g @spartan-ng/cli:ui dialog
```

## Uso Básico

### Importación

```typescript
import { HlmDialogImports } from '@spartan-ng/helm/dialog';
```

### Template

```html
<hlm-dialog>
  <button hlmDialogTrigger hlmBtn variant="outline">Abrir Diálogo</button>
  <hlm-dialog-content *hlmDialogPortal="let ctx">
    <hlm-dialog-header>
      <h3 hlmDialogTitle>Editar Perfil</h3>
      <p hlmDialogDescription>Realiza cambios en tu perfil aquí. Haz clic en guardar cuando termines.</p>
    </hlm-dialog-header>
    <hlm-dialog-footer>
      <button hlmBtn variant="outline" hlmDialogClose>Cancelar</button>
      <button hlmBtn type="submit">Guardar cambios</button>
    </hlm-dialog-footer>
  </hlm-dialog-content>
</hlm-dialog>
```

## Ejemplos

### Uso Declarativo (Stateful)

Puedes controlar el estado del diálogo (open/closed) mediante la propiedad `state`.

```typescript
protected readonly _state = signal<'open' | 'closed'>('closed');
```

```html
<hlm-dialog [state]="_state()">
  <hlm-dialog-content *hlmDialogPortal="let ctx">
     ...
  </hlm-dialog-content>
</hlm-dialog>
```

### Dentro de un Menú

Es común abrir un diálogo desde una opción de un menú desplegable.

```html
<button hlmDropdownMenuItem [hlmDialogTriggerFor]="editDialog">
  Editar
</button>

<hlm-dialog #editDialog>
  ...
</hlm-dialog>
```

## API Reference

### Helm (Estilos)

- `hlm-dialog`: Componente contenedor.
- `hlmDialogTrigger`: Directiva para el botón que abre el diálogo.
- `hlm-dialog-content`: Contenedor del contenido modal.
- `*hlmDialogPortal`: Directiva estructural necesaria para el contenido.
- `hlm-dialog-header` / `hlm-dialog-footer`: Secciones de la modal.
- `hlmDialogTitle` / `hlmDialogDescription`: Estilos para el texto.
- `hlmDialogClose`: Directiva para cerrar el diálogo al hacer clic.

### Brain (Lógica)

- `BrnDialog`: Primitiva que gestiona el foco, el bloqueo del scroll y la accesibilidad.
- `BrnDialogTrigger`: Gestiona la apertura y el estado `aria-haspopup`.
