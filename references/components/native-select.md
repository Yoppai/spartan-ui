# Native Select Component

Elemento `<select>` nativo de HTML con estilos integrados para una apariencia consistente con el sistema de diseño.

## Instalación

```bash
ng g @spartan-ng/cli:ui native-select
```

## Uso Básico

### Importación

```typescript
import { HlmNativeSelectImports } from '@spartan-ng/helm/native-select';
```

### Template

```html
<hlm-native-select>
  <option hlmNativeSelectOption value="">Selecciona una fruta</option>
  <option hlmNativeSelectOption value="apple">Manzana</option>
  <option hlmNativeSelectOption value="banana">Plátano</option>
</hlm-native-select>
```

## Ejemplos

### Con Grupos (OptGroup)

```html
<hlm-native-select>
  <optgroup hlmNativeSelectOptGroup label="Ingeniería">
    <option hlmNativeSelectOption value="frontend">Frontend</option>
    <option hlmNativeSelectOption value="backend">Backend</option>
  </optgroup>
  <optgroup hlmNativeSelectOptGroup label="Ventas">
    <option hlmNativeSelectOption value="sales-rep">Ventas</option>
  </optgroup>
</hlm-native-select>
```

## Native Select vs Select

- Usa **Native Select** para un comportamiento nativo del navegador, mejor rendimiento o dropdowns optimizados para móviles.
- Usa **Select** para estilos personalizados avanzados, animaciones o interacciones complejas.

## API Reference

### Helm (Estilos)

- `hlm-native-select`: Envoltorio para el select nativo del navegador.
- `hlmNativeSelectOption`: Directiva para los elementos `<option>`.
- `hlmNativeSelectOptGroup`: Directiva para los elementos `<optgroup>`.
