# Date Picker Documentation

Un componente potente de selección de fechas que admite selecciones individuales, múltiples y de rango.

## Instalación

```bash
ng g @spartan-ng/cli:ui date-picker
```

## Uso Básico

### Importación

```typescript
import { HlmDatePickerImports } from '@spartan-ng/helm/date-picker';
```

### Template

```html
<hlm-date-picker [min]="minDate" [max]="maxDate">
  <span>Seleccionar fecha</span>
</hlm-date-picker>
```

## Ejemplos

### Configuración Personalizada

Puedes configurar el formato de fecha y transformaciones usando `provideHlmDatePickerConfig`.

```typescript
import { provideHlmDatePickerConfig } from '@spartan-ng/helm/date-picker';

providers: [
    provideHlmDatePickerConfig({
        formatDate: (date: Date) => date.toLocaleDateString('es-ES'),
        // ... otras opciones
    }),
]
```

### Selección Múltiple

Permite a los usuarios seleccionar varias fechas con límites opcionales.

```html
<hlm-date-picker-multi
    [minSelection]="2"
    [maxSelection]="6"
    [autoCloseOnMaxSelection]="true"
>
    <span>Elegir fechas</span>
</hlm-date-picker-multi>
```

### Selector de Rango (Range)

Selecciona una fecha de inicio y una de fin.

```html
<hlm-date-range-picker [autoCloseOnEndSelection]="true">
    <span>Introduce un rango</span>
</hlm-date-range-picker>
```

### Integración con Formularios Reactivos

```html
<form [formGroup]="form">
  <hlm-date-picker formControlName="birthday">
    <span>Elige tu cumpleaños</span>
  </hlm-date-picker>
</form>
```

## API Reference

### HlmDatePicker (Selección Única)

- **Inputs**:
  - `date`: El valor seleccionado.
  - `min` / `max`: Límites de selección.
  - `disabled`: Booleano para deshabilitar.
  - `autoCloseOnSelect`: Si se cierra al elegir (Default: `true`).

### HlmDatePickerMulti (Selección Múltiple)

- **Inputs**:
  - `minSelection` / `maxSelection`: Límites de cantidad de fechas.
  - `autoCloseOnMaxSelection`: Si se cierra al alcanzar el máximo.

### HlmDateRangePicker (Rango)

- **Inputs**:
  - `date`: Tupla `[Date, Date]`.
  - `autoCloseOnEndSelection`: Si se cierra al elegir la fecha final.
