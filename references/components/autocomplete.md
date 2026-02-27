# Autocomplete Component

Entrada con autocompletado y selección de menú desplegable con opciones de filtrado.

## Instalación

```bash
ng g @spartan-ng/cli:ui autocomplete
```

## Uso Básico

```typescript
import { HlmAutocompleteImports } from '@spartan-ng/helm/autocomplete';
```

```html
<hlm-autocomplete [(search)]="search">
  <hlm-autocomplete-input placeholder="Buscar componentes" />
  <hlm-autocomplete-content *hlmAutocompletePortal>
    <hlm-autocomplete-empty>No se encontraron resultados.</hlm-autocomplete-empty>
    <div hlmAutocompleteList>
      @for (option of filteredOptions(); track $index) {
        <hlm-autocomplete-item [value]="option">
          {{ option }}
        </hlm-autocomplete-item>
      }
    </div>
  </hlm-autocomplete-content>
</hlm-autocomplete>
```

## Ejemplos

### With Clear Button

Usa la propiedad `showClear` en el input para mostrar un botón que limpia la búsqueda.

```html
<hlm-autocomplete [(search)]="search">
  <hlm-autocomplete-input placeholder="Buscar..." showClear />
  ...
</hlm-autocomplete>
```

### Disabled

Puedes deshabilitar el autocomplete usando el atributo `disabled`.

```html
<hlm-autocomplete [(search)]="search" disabled>
  <hlm-autocomplete-input placeholder="Deshabilitado" />
  ...
</hlm-autocomplete>
```

### Auto highlight

Resalta automáticamente la primera opción que coincide.

```html
<hlm-autocomplete [(search)]="search" autoHighlight>
  ...
</hlm-autocomplete>
```

### With Groups

Usa `hlmAutocompleteGroup` y `hlmAutocompleteLabel` para organizar las opciones.

```html
<hlm-autocomplete [(search)]="search">
  <hlm-autocomplete-input placeholder="Seleccionar zona horaria" />
  <hlm-autocomplete-content *hlmAutocompletePortal>
    <hlm-autocomplete-empty>No items found.</hlm-autocomplete-empty>
    <div hlmAutocompleteList>
      @for (group of filteredTimezones(); track $index) {
        <div hlmAutocompleteGroup>
          <div hlmAutocompleteLabel>{{ group.value }}</div>
          @for (timezone of group.items; track $index) {
            <hlm-autocomplete-item [value]="timezone">{{ timezone }}</hlm-autocomplete-item>
          }
        </div>
      }
    </div>
  </hlm-autocomplete-content>
</hlm-autocomplete>
```

### Object (custom label)

Personaliza el valor seleccionado para objetos proporcionando una función `itemToString`.

```typescript
type Country = { name: string; flag: string; };
public itemToString = (item: Country): string => `${item.flag} ${item.name}`;
```

```html
<hlm-autocomplete [(search)]="search" [itemToString]="itemToString">
  <hlm-autocomplete-input placeholder="Search countries" />
  <hlm-autocomplete-content *hlmAutocompletePortal>
    <div hlmAutocompleteList>
      @for (option of filteredCountries(); track $index) {
        <hlm-autocomplete-item [value]="option">{{ option.name }}</hlm-autocomplete-item>
      }
    </div>
  </hlm-autocomplete-content>
</hlm-autocomplete>
```

### Async search (Using resource)

Spartan UI se integra perfectamente con las nuevas APIs de Angular como `resource` para búsquedas asíncronas.

```typescript
import { resource, signal } from '@angular/core';
import { HlmSpinnerImports } from '@spartan-ng/helm/spinner';

public search = signal('');
public options = resource({
  defaultValue: [],
  params: () => ({ search: this.search() }),
  loader: async ({ params }) => {
    if (params.search.length === 0) return [];
    return await fetchMovies(params.search);
  },
});
```

```html
<hlm-autocomplete [(search)]="search">
  <hlm-autocomplete-input placeholder="Search movies" />
  <hlm-autocomplete-content *hlmAutocompletePortal>
    <hlm-autocomplete-status>
      @if (options.isLoading()) { <hlm-spinner /> Cargando... }
      @else if (options.hasValue()) { {{ options.value().length }} resultados }
    </hlm-autocomplete-status>
    <div hlmAutocompleteList>
      @if (options.hasValue()) {
        @for (option of options.value(); track $index) {
          <hlm-autocomplete-item [value]="option">{{ option.title }}</hlm-autocomplete-item>
        }
      }
    </div>
  </hlm-autocomplete-content>
</hlm-autocomplete>
```

### Form (Reactive Forms)

Integración con `ReactiveFormsModule` y el componente de campo de Spartan.

```typescript
public form = inject(FormBuilder).group({
  component: [null, Validators.required],
});
```

```html
<form [formGroup]="form">
  <div hlmField>
    <label hlmFieldLabel>Selecciona un componente</label>
    <hlm-autocomplete formControlName="component" [(search)]="search">
      <hlm-autocomplete-input placeholder="Ej. Accordion" />
      ...
    </hlm-autocomplete>
  </div>
</form>
```

## API Reference

### Helm (Estilos)

- `hlm-autocomplete`: Contenedor principal.
- `hlm-autocomplete-input`: Campo de entrada. Soporta `showClear`.
- `hlm-autocomplete-content`: Menú desplegable.
- `*hlmAutocompletePortal`: Directiva para el portal.
- `hlmAutocompleteList`: Contenedor de la lista.
- `hlm-autocomplete-item`: Elemento individual.
- `hlmAutocompleteGroup`: Agrupador de items.
- `hlmAutocompleteLabel`: Etiqueta de grupo.
- `hlm-autocomplete-status`: Area para estados (carga, error).

### Brain (Lógica)

- `brn-autocomplete`: Primitiva lógica.
- `itemToString`: Input para personalizar la representación en texto del objeto.
- `autoHighlight`: Input para resaltar automáticamente la primera opción.
