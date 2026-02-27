# Alert Dialog Component

Un cuadro de diálogo modal que interrumpe al usuario con contenido importante y espera una respuesta.

## Instalación

```bash
ng g @spartan-ng/cli:ui alert-dialog
```

## Uso Básico

### Importación

```typescript
import { HlmAlertDialogImports } from '@spartan-ng/helm/alert-dialog';
```

### Template

```html
<hlm-alert-dialog>
  <button id="edit-profile" hlmAlertDialogTrigger>Mostrar Diálogo</button>
  <hlm-alert-dialog-content *hlmAlertDialogPortal="let ctx">
    <hlm-alert-dialog-header>
      <h2 hlmAlertDialogTitle>¿Estás absolutamente seguro?</h2>
      <p hlmAlertDialogDescription>
        Esta acción no se puede deshacer. Esto eliminará permanentemente tu cuenta y borrará tus datos de nuestros servidores.
      </p>
    </hlm-alert-dialog-header>
    <hlm-alert-dialog-footer>
      <button hlmAlertDialogCancel (click)="ctx.close()">Cancelar</button>
      <button hlmAlertDialogAction (click)="ctx.close()">Continuar</button>
    </hlm-alert-dialog-footer>
  </hlm-alert-dialog-content>
</hlm-alert-dialog>
```

## API Reference

### Helm (Estilos)

- `hlm-alert-dialog`: Componente principal.
- `hlmAlertDialogTrigger`: Directiva para el botón que abre el diálogo.
- `hlm-alert-dialog-content`: Contenedor del contenido del diálogo.
- `*hlmAlertDialogPortal`: Directiva para el portal de contenido (necesaria para el contexto `ctx`).
- `hlm-alert-dialog-header`: Contenedor del encabezado.
- `hlmAlertDialogTitle`: Directiva para el título.
- `hlmAlertDialogDescription`: Directiva para la descripción.
- `hlm-alert-dialog-footer`: Contenedor del pie de página.
- `hlmAlertDialogCancel`: Directiva para el botón de cancelar.
- `hlmAlertDialogAction`: Directiva para el botón de acción (continuar).

### Brain (Lógica)

- `brn-alert-dialog`: Primitiva lógica.
- `brnAlertDialogTrigger`: Controla la apertura del diálogo.
- `brn-alert-dialog-content`: Gestiona el estado y la accesibilidad del contenido modal.
