# Sidebar Component

Componente de navegación lateral altamente personalizable y responsive. Soporta estados colapsibles, menús anidados y persistencia mediante cookies.

## Instalación

```bash
ng g @spartan-ng/cli:ui sidebar
```

## Configuración de Colores (CSS)

El sidebar utiliza variables CSS dedicadas para facilitar su personalización independiente del resto de la app.

```css
:root {
  --sidebar: oklch(0.985 0 0);
  --sidebar-foreground: oklch(0.145 0 0);
  --sidebar-primary: oklch(0.205 0 0);
  --sidebar-primary-foreground: oklch(0.985 0 0);
  --sidebar-accent: oklch(0.97 0 0);
  --sidebar-accent-foreground: oklch(0.205 0 0);
  --sidebar-border: oklch(0.922 0 0);
  --sidebar-ring: oklch(0.708 0 0);
}
```

## Uso Básico

### Estructura del Layout

El sidebar requiere un componente contenedor y el servicio para gestionar su estado.

```typescript
import { HlmSidebarImports } from '@spartan-ng/helm/sidebar';
```

```html
<div hlmSidebarWrapper>
  <hlm-sidebar>
    <div hlmSidebarHeader>Título Logo</div>
    <div hlmSidebarContent>
      <div hlmSidebarGroup>
        <div hlmSidebarGroupLabel>Menú</div>
        <div hlmSidebarGroupContent>
          <ul hlmSidebarMenu>
            <li hlmSidebarMenuItem>
              <a hlmSidebarMenuButton href="/home">
                <ng-icon hlm name="lucideHouse" />
                <span>Inicio</span>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </div>
    <div hlmSidebarFooter>Usuario</div>
  </hlm-sidebar>
  
  <main hlmSidebarInset>
    <button hlmSidebarTrigger>Abrir/Cerrar</button>
    <ng-content />
  </main>
</div>
```

## Atajos de Teclado

- **Windows/Linux**: `Ctrl + B` para alternar el sidebar.
- **macOS**: `⌘ + B` para alternar el sidebar.

## API Reference (Helm)

- `hlm-sidebar`: El contenedor lateral.
- `hlmSidebarWrapper`: Directiva para el contenedor que engloba sidebar y contenido principal.
- `hlmSidebarTrigger`: Botón para expandir/colapsar.
- `hlmSidebarInset`: Directiva para el área de contenido principal que se desplaza con el sidebar.
- `hlmSidebarMenu`: Lista `<ul>` interna del sidebar.
- `hlmSidebarMenuItem`: Cada elemento `<li>` de la lista.
- `hlmSidebarMenuButton`: El elemento interactivo dentro del item.

### HlmSidebarService (Signals)

- `open`: boolean (Estado en desktop).
- `openMobile`: boolean (Estado en móvil).
- `isMobile`: boolean (Detecta si el viewport es < 768px).
- `toggleSidebar()`: Función para alternar el estado.
