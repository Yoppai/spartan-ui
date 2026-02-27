# Tabs Component

Conjunto de secciones de contenido en capas (paneles) que se muestran una a la vez mediante pestañas.

## Instalación

```bash
ng g @spartan-ng/cli:ui tabs
```

## Uso Básico

### Importación

```typescript
import { HlmTabsImports } from '@spartan-ng/helm/tabs';
```

### Template

```html
<hlm-tabs tab="account" class="w-[400px]">
  <hlm-tabs-list class="grid w-full grid-cols-2">
    <button hlmTabsTrigger="account">Cuenta</button>
    <button hlmTabsTrigger="password">Seguridad</button>
  </hlm-tabs-list>
  
  <div hlmTabsContent="account">
    Configura los detalles de tu cuenta aquí.
  </div>
  
  <div hlmTabsContent="password">
    Cambia tu contraseña desde aquí.
  </div>
</hlm-tabs>
```

## Pestañas con Iconos

```html
<button hlmTabsTrigger="home">
  <ng-icon name="lucideHome" class="mr-2" /> Inicio
</button>
```

## Carga Perezosa (Lazy Loading)

Para contenidos pesados, puedes usar `hlmTabsContentLazy`.

```html
<ng-template hlmTabsContentLazy="heavy-data">
  <app-expensive-component />
</ng-template>
```

## API Reference

### Helm (Estilos)

- `hlm-tabs`: Contenedor raíz.
  - **Inputs**: `tab` (id de la pestaña activa inicial).
- `hlm-tabs-list`: Contenedor de los triggers.
- `hlmTabsTrigger`: Directiva para los botones de pestañas.
- `hlmTabsContent`: Contenedor para el contenido asociado a una pestaña.

### Brain (Lógica)

- `BrnTabs`: Gestiona la sincronización entre el trigger seleccionado y el contenido visible.
