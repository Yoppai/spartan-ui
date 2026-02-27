# Input OTP Component

Componente de contraseña de un solo uso (One-Time Password) accesible y personalizable.

## Instalación

```bash
ng g @spartan-ng/cli:ui input-otp
```

## Uso Básico

### Importación

```typescript
import { BrnInputOtp } from '@spartan-ng/brain/input-otp';
import { HlmInputOtp, HlmInputOtpGroup, HlmInputOtpSeparator, HlmInputOtpSlot } from '@spartan-ng/helm/input-otp';
```

### Template

```html
<brn-input-otp hlmInputOtp maxLength="6">
  <div hlmInputOtpGroup>
    <hlm-input-otp-slot index="0" />
    <hlm-input-otp-slot index="1" />
    <hlm-input-otp-slot index="2" />
  </div>
  <hlm-input-otp-separator />
  <div hlmInputOtpGroup>
    <hlm-input-otp-slot index="3" />
    <hlm-input-otp-slot index="4" />
    <hlm-input-otp-slot index="5" />
  </div>
</brn-input-otp>
```

## Animación

Para habilitar la animación del cursor parpadeante, asegúrate de tener el plugin de animaciones configurado en Tailwind. Spartan recomienda usar `tw-animate-css`.

```css
@import '@spartan-ng/brain/hlm-tailwind-preset.css';
```

## API Reference

### Helm (Estilos)

- `hlmInputOtp`: Directiva principal sobre el componente `brn-input-otp`.
- `hlmInputOtpGroup`: Agrupa varios slots.
- `hlm-input-otp-slot`: Celda individual para un dígito.
  - **Inputs**: `index` (número de posición).
- `hlm-input-otp-separator`: Elemento visual para separar grupos (normalmente un guion).
- `hlm-input-otp-fake-caret`: Componente para el cursor animado.

### Brain (Lógica)

- `BrnInputOtp`: Gestiona el foco entre celdas, el pegado (paste) y la lógica de entrada.
- `BrnInputOtpSlot`: Celda lógica individual.
