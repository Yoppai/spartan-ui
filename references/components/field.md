# Field Documentation

Permite combinar etiquetas, controles y texto de ayuda para componer campos de formulario accesibles y grupos de entrada.

## Instalación

```bash
ng g @spartan-ng/cli:ui field
```

## Uso Básico

### Importación

```typescript
import { HlmFieldImports } from '@spartan-ng/helm/field';
```

### Template (Anatomía)

```html
<div hlmField>
  <label hlmFieldLabel for="full-name">Nombre completo</label>
  <input hlmInput id="full-name" type="text" placeholder="John Doe" />
  <p hlmFieldDescription>Este nombre aparecerá en facturas y correos.</p>
  <hlm-field-error>El nombre es obligatorio.</hlm-field-error>
</div>
```

## Agrupación (Field Groups)

Utiliza `hlmFieldGroup` para agrupar campos relacionados y `hlmFieldSet` para una agrupación semántica.

```html
<fieldset hlmFieldSet>
  <legend hlmFieldLegend>Perfil</legend>
  <div hlmFieldGroup>
    <div hlmField>
       <!-- Campo 1 -->
    </div>
    <hlm-field-separator />
    <div hlmField>
       <!-- Campo 2 -->
    </div>
  </div>
</fieldset>
```

## Validación y Errores

Para indicar un estado de error, añade `data-invalid` al contenedor `hlmField`.

```html
<div hlmField data-invalid="true">
  <label hlmFieldLabel for="email">Email</label>
  <input hlmInput id="email" type="email" aria-invalid="true" />
  <hlm-field-error>Introduce un email válido.</hlm-field-error>
</div>
```

## API Reference

### Helm (Estilos)

- `hlmField`: Envoltorio principal de un campo.
  - **Inputs**: `orientation` (`vertical` | `horizontal`).
- `hlmFieldLabel`: Directiva para etiquetas.
- `hlmFieldDescription`: Directiva para texto de ayuda.
- `hlm-field-error`: Componente para mensajes de validación.
- `hlmFieldGroup`: Envoltorio para un conjunto de campos.
- `hlmFieldSet`: Envoltorio semántico (`fieldset`).
- `hlmFieldLegend`: Título del fieldset (`legend`).
- `hlm-field-separator`: Línea divisoria entre campos de un grupo.
- `hlm-field-content`: Flex column para agrupar label y description (opcional).
