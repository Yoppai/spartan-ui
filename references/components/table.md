# Table Component

Componente de tabla semántico y responsive con soporte para cabeceras, pies de página y captions.

## Instalación

```bash
ng g @spartan-ng/cli:ui table
```

## Uso Básico

### Importación

```typescript
import { HlmTableImports } from '@spartan-ng/helm/table';
```

### Template

```html
<div hlmTableContainer>
  <table hlmTable>
    <caption hlmCaption>Lista de transacciones recientes</caption>
    <thead hlmTHead>
      <tr hlmTr>
        <th hlmTh>ID</th>
        <th hlmTh>Usuario</th>
        <th hlmTh class="text-right">Monto</th>
      </tr>
    </thead>
    <tbody hlmTBody>
      @for (item of items; track item.id) {
        <tr hlmTr>
          <td hlmTd>{{ item.id }}</td>
          <td hlmTd>{{ item.user }}</td>
          <td hlmTd class="text-right">{{ item.amount }}</td>
        </tr>
      }
    </tbody>
    <tfoot hlmTFoot>
      <tr hlmTr>
        <td hlmTd colspan="2">Total</td>
        <td hlmTd class="text-right">$1,200.00</td>
      </tr>
    </tfoot>
  </table>
</div>
```

## API Reference

### Helm (Estilos)

- `hlmTableContainer`: Directiva para el wrapper que permite scroll horizontal si es necesario.
- `hlmTable`: Aplicado a la etiqueta `<table>`.
- `hlmTHead`: Aplicado a `<thead>`.
- `hlmTBody`: Aplicado a `<tbody>`.
- `hlmTFoot`: Aplicado a `<tfoot>`.
- `hlmTr`: Aplicado a `<tr>`.
- `hlmTh`: Aplicado a `<th>`.
- `hlmTd`: Aplicado a `<td>`.
- `hlmCaption`: Aplicado a `<caption>`.

> [!TIP]
> Para tablas más complejas con ordenamiento, filtrado y paginación, utiliza el componente [Data Table](file:///e:/Projects/skills/.agents/skills/spartan-ui/references/components/data-table.md).
