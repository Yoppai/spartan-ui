# Pagination Component

Componente de paginación con navegación por páginas, enlaces de anterior y siguiente, y soporte avanzado para gestión de estado.

## Instalación

```bash
ng g @spartan-ng/cli:ui pagination
```

## Uso Básico

### Importación

```typescript
import { HlmPaginationImports } from '@spartan-ng/helm/pagination';
```

### Template

```html
<nav hlmPagination>
  <ul hlmPaginationContent>
    <li hlmPaginationItem>
      <hlm-pagination-previous link="/prev" />
    </li>
    <li hlmPaginationItem>
      <a hlmPaginationLink link="/1">1</a>
    </li>
    <li hlmPaginationItem>
      <a hlmPaginationLink link="/2" isActive>2</a>
    </li>
    <li hlmPaginationItem>
      <hlm-pagination-ellipsis />
    </li>
    <li hlmPaginationItem>
      <hlm-pagination-next link="/next" />
    </li>
  </ul>
</nav>
```

## Paginación Avanzada (Numbered Pagination)

Spartan ofrece un componente de alto nivel para gestionar la lógica de números automáticamente.

```html
<hlm-numbered-pagination
  [(currentPage)]="page"
  [(itemsPerPage)]="pageSize"
  [totalItems]="total"
/>
```

## API Reference

### Helm (Estilos)

- `hlmPagination`: Directiva para el contenedor `<nav>`.
- `hlmPaginationContent`: Para la lista `<ul>`.
- `hlmPaginationItem`: Para cada `<li>`.
- `hlmPaginationLink`: Para enlaces de página.
  - **Inputs**: `isActive` (boolean), `link` (string).
- `hlm-pagination-previous` / `hlm-pagination-next`: Botones de navegación.
  - **Inputs**: `link` (string), `iconOnly` (boolean).
- `hlm-pagination-ellipsis`: Indicador de salto de páginas.
- `hlm-numbered-pagination`: Componente de lógica automatizada.
