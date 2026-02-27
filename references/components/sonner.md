# Sonner Component

Componente de notificaciones (toast) basado en `ngx-sonner`.

## Instalación

```bash
ng g @spartan-ng/cli:ui sonner
```

## Uso Básico

### Importación

```typescript
import { toast } from 'ngx-sonner';
import { HlmToasterImports } from '@spartan-ng/helm/sonner';
```

### Template

Carga el componente `<hlm-toaster />` una sola vez en el componente raíz (normalmente `app.component.ts`).

```html
<hlm-toaster />
<button hlmBtn (click)="showToast()">Mostrar Notificación</button>
```

### Lógica

```typescript
showToast() {
  toast('Evento exitoso', {
    description: 'La operación se completó correctamente.',
    action: {
      label: 'Deshacer',
      onClick: () => console.log('Deshaciendo...'),
    },
  });
}
```

## API Reference

### Helm (Estilos)

- `hlm-toaster`: Componente que gestiona el renderizado de todos los toasts activos.
  - Soporta propiedades de `ngx-sonner` como `position`, `expand`, `richColors`, etc.
