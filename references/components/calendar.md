# Calendar Component

Un componente de campo de fecha que permite a los usuarios introducir y editar fechas.

## Instalación

```bash
ng g @spartan-ng/cli:ui calendar
```

## Uso Básico

### Importación

```typescript
import { HlmCalendarImports } from '@spartan-ng/helm/calendar';
```

### Template

```html
<hlm-calendar [(date)]="selectedDate" [min]="minDate" [max]=\"maxDate" />
```

## Internacionalización (i18n)

El calendario soporta i18n mediante `BrnCalendarI18nService`.

### Configuración Global

```typescript
import { provideBrnCalendarI18n } from '@spartan-ng/brain/calendar';

bootstrapApplication(App, {
  providers: [
    provideBrnCalendarI18n({
      formatWeekdayName: (i) => ['Do', 'Lu', 'Ma', 'Mi', 'Ju', 'Vi', 'Sa'][i],
      formatHeader: (m, y) => new Date(y, m).toLocaleDateString('es-ES', { month: 'long', year: 'numeric' }),
      labelPrevious: () => 'Mes anterior',
      labelNext: () => 'Mes siguiente',
      firstDayOfWeek: () => 1,
    }),
  ],
});
```

## Ejemplos

### Selección Múltiple

Usa `hlm-calendar-multi` para permitir seleccionar varias fechas.

```html
<hlm-calendar-multi 
  [(date)]="selectedDates" 
  [minSelection]="2" 
  [maxSelection]="6" 
/>
```

### Selección de Rango

Usa `hlm-calendar-range` para seleccionar un rango de fechas.

```html
<hlm-calendar-range 
  [(startDate)]="start" 
  [(endDate)]="end" 
/>
```

### Selector de Mes y Año

Usa el input `captionLayout` para mostrar desplegables de mes y año.

```html
<hlm-calendar captionLayout="dropdown" />
```

## API Reference

### Helm (Estilos)

- `hlm-calendar`: Calendario estándar.
- `hlm-calendar-multi`: Calendario para selección múltiple.
- `hlm-calendar-range`: Calendario para selección de rango.

### Brain (Lógica)

- `BrnCalendarI18nService`: Servicio para gestionar la localización.
- `provideBrnCalendarI18n`: Función proveedora para configuración global.
- `injectBrnCalendarI18n`: Inyecta el servicio de i18n para cambios en tiempo de ejecución.
