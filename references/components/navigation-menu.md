# Navigation Menu Component

Conjunto de enlaces para navegar por sitios web, con soporte para submenús ricos y animaciones.

## Instalación

```bash
ng g @spartan-ng/cli:ui navigation-menu
```

## Uso Básico

### Importación

```typescript
import { HlmNavigationMenuImports } from '@spartan-ng/helm/navigation-menu';
```

### Template

```html
<nav hlmNavigationMenu>
  <ul hlmNavigationMenuList>
    <li hlmNavigationMenuItem>
      <button hlmNavigationMenuTrigger>Productos</button>
      <hlm-navigation-menu-content *hlmNavigationMenuPortal>
        <ul class="grid w-[400px] gap-3 p-4 md:w-[500px] md:grid-cols-2 lg:w-[600px]">
          <li><a hlmNavigationMenuLink link="/p1">Producto 1</a></li>
          <li><a hlmNavigationMenuLink link="/p2">Producto 2</a></li>
        </ul>
      </hlm-navigation-menu-content>
    </li>
    <li hlmNavigationMenuItem>
      <a hlmNavigationMenuLink link="/about">Acerca de</a>
    </li>
  </ul>
</nav>
```

## Ejemplos

### Controlado (Value)

Puedes activar un item programáticamente usando el input `value` en el componente principal y asignando un `id` a los items.

```html
<nav hlmNavigationMenu [(value)]="activeMenu">
   ...
</nav>
```

## API Reference

### Helm (Estilos)

- `hlmNavigationMenu`: Directiva para el contenedor `<nav>`.
- `hlmNavigationMenuList`: Directiva para la lista `<ul>`.
- `hlmNavigationMenuItem`: Directiva para cada `<li>`.
- `hlmNavigationMenuTrigger`: Directiva para el botón que despliega el contenido.
- `hlm-navigation-menu-content`: Componente que contiene el submenú.
- `hlmNavigationMenuPortal`: Directiva estructural para renderizar el contenido en un portal.
- `hlmNavigationMenuLink`: Para enlaces individuales.

### Brain (Lógica)

- `BrnNavigationMenu`: Gestiona los estados de abierto/cerrado, accesibilidad de teclado y retardos de hover.
- `BrnNavigationMenuTrigger`: Gestión del foco y eventos de activación.
