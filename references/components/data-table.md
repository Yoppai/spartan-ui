# Data Table Component

Tablas y cuadrículas de datos potentes similares a Angular Material Tables, construidas sobre **TanStack Table**.

## Instalación

1. Añade las directivas de **Table**:
   ```bash
   ng g @spartan-ng/cli:ui table
   ```

2. Instala la librería de **TanStack Table** para Angular:
   ```bash
   npm install @tanstack/angular-table
   ```

## Sobre Data Table

Spartan UI no proporciona un componente `hlm-data-table` único, sino que ofrece los estilos base (`hlmTable`) y recomienda el uso de **TanStack Table** para la gestión de lógica (filtrado, ordenación, paginación).

### Ejemplos de Integración

Para implementar una tabla de datos completa, debes configurar el `createAngularTable` de TanStack y usar los componentes de tabla de Spartan para el renderizado.

Temas comunes:
- **Visibilidad de Columnas**: Gestionado por el estado de TanStack.
- **Filtros de Columna**: Inputs vinculados a la API de filtrado de TanStack.
- **Selección de Filas**: Checkboxes integrados en las celdas de la tabla (`hlm-checkbox`).

## Recursos

- [TanStack Table Angular Docs](https://tanstack.com/table/v8/docs/framework/angular/angular-table): Documentación oficial de la lógica de tablas.
- [Spartan UI Table](file:///e:/Projects/skills/.agents/skills/spartan-ui/references/components/table.md): Guía de las directivas de estilo para tablas.

## Recomendación

Para tablas complejas con paginación y búsqueda, consulta el código fuente del ejemplo **Tasks** en el sitio de Spartan UI para ver una implementación real completa.
