# Breadcrumb Component

Muestra la ruta al recurso actual usando una jerarquía de enlaces.

## Instalación

```bash
ng g @spartan-ng/cli:ui breadcrumb
```

## Uso Básico

### Importación

```typescript
import { HlmBreadCrumbImports } from '@spartan-ng/helm/breadcrumb';
```

### Template

```html
<nav hlmBreadcrumb>
  <ol hlmBreadcrumbList>
    <li hlmBreadcrumbItem>
      <a hlmBreadcrumbLink link="/">Inicio</a>
    </li>
    <li hlmBreadcrumbSeparator></li>
    <li hlmBreadcrumbItem>
      <a hlmBreadcrumbLink link="/componentes">Componentes</a>
    </li>
    <li hlmBreadcrumbSeparator></li>
    <li hlmBreadcrumbItem>
      <span hlmBreadcrumbPage>Breadcrumb</span>
    </li>
  </ol>
</nav>
```

## Ejemplos

### Separador Personalizado

```html
<li hlmBreadcrumbSeparator>
  <ng-icon name="lucideSlash" />
</li>
```

### Con Menú Desplegable (Dropdown)

```html
<li hlmBreadcrumbItem>
  <button [hlmDropdownMenuTrigger]="menu">
    Componentes <ng-icon name="lucideChevronDown" />
  </button>
  <ng-template #menu>
    <hlm-dropdown-menu>
      ...
    </hlm-dropdown-menu>
  </ng-template>
</li>
```

### Colapsado (Ellipsis)

Usa `hlm-breadcrumb-ellipsis` para mostrar un estado colapsado cuando el breadcrumb es muy largo.

```html
<li hlmBreadcrumbItem>
  <hlm-breadcrumb-ellipsis />
</li>
```

## API Reference

### Helm (Estilos)

- `hlmBreadcrumb`: Contenedor principal (`nav`).
- `hlmBreadcrumbList`: Contenedor de la lista (`ol`).
- `hlmBreadcrumbItem`: Elemento de la lista (`li`).
- `hlmBreadcrumbLink`: Enlace dentro del item.
- `hlmBreadcrumbPage`: Representa la página actual (sin enlace).
- `hlmBreadcrumbSeparator`: Separador entre items.
- `hlm-breadcrumb-ellipsis`: Componente para representar items ocultos.
