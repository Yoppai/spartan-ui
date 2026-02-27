# Avatar Component

Un elemento de imagen con un respaldo (fallback) para representar a un usuario.

## Instalación

```bash
ng g @spartan-ng/cli:ui avatar
```

## Uso Básico

### Importación

```typescript
import { HlmAvatarImports } from '@spartan-ng/helm/avatar';
```

### Template

```html
<hlm-avatar>
  <img hlmAvatarImage src='/assets/avatar.png' alt='spartan logo' />
  <span hlmAvatarFallback>RG</span>
</hlm-avatar>
```

## Ejemplos

### Basic

Un componente de avatar básico con una imagen y un fallback.

```typescript
import { ChangeDetectionStrategy, Component } from '@angular/core';
import { HlmAvatarImports } from '@spartan-ng/helm/avatar';

@Component({
  selector: 'spartan-avatar-basic-preview',
  standalone: true,
  imports: [HlmAvatarImports],
  changeDetection: ChangeDetectionStrategy.OnPush,
  template: `
    <hlm-avatar>
      <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
      <span hlmAvatarFallback>RG</span>
    </hlm-avatar>
  `,
})
export class AvatarBasicPreview {}
```

### Badge (Insignia)

Usa el componente `hlm-avatar-badge` para añadir una insignia al avatar. La insignia se posiciona en la parte inferior derecha.

```typescript
import { ChangeDetectionStrategy, Component } from '@angular/core';
import { HlmAvatarImports } from '@spartan-ng/helm/avatar';

@Component({
  selector: 'spartan-avatar-badge-preview',
  standalone: true,
  imports: [HlmAvatarImports],
  changeDetection: ChangeDetectionStrategy.OnPush,
  template: `
    <hlm-avatar>
      <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" />
      <span hlmAvatarFallback>RG</span>
      <hlm-avatar-badge class="bg-red-600 dark:bg-red-800" />
    </hlm-avatar>
  `,
})
export class AvatarBadgePreview {}
```

### Badge Icon

También puedes usar un icono dentro de `hlm-avatar-badge`.

```typescript
import { ChangeDetectionStrategy, Component } from '@angular/core';
import { NgIcon, provideIcons } from '@ng-icons/core';
import { lucidePlus } from '@ng-icons/lucide';
import { HlmAvatarImports } from '@spartan-ng/helm/avatar';

@Component({
  selector: 'spartan-avatar-badge-icon-preview',
  standalone: true,
  imports: [HlmAvatarImports, NgIcon],
  providers: [provideIcons({ lucidePlus })],
  changeDetection: ChangeDetectionStrategy.OnPush,
  template: `
    <hlm-avatar class="grayscale">
      <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" />
      <span hlmAvatarFallback>RG</span>
      <hlm-avatar-badge>
        <ng-icon name="lucidePlus" />
      </hlm-avatar-badge>
    </hlm-avatar>
  `,
})
export class AvatarBadgeIconPreview {}
```

### Avatar Group

Usa el componente `hlm-avatar-group` para añadir un grupo de avatares.

```typescript
import { ChangeDetectionStrategy, Component } from '@angular/core';
import { HlmAvatarImports } from '@spartan-ng/helm/avatar';

@Component({
  selector: 'spartan-avatar-group-preview',
  standalone: true,
  imports: [HlmAvatarImports],
  changeDetection: ChangeDetectionStrategy.OnPush,
  template: `
    <hlm-avatar-group class="grayscale">
      <hlm-avatar>
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
      <hlm-avatar>
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
      <hlm-avatar>
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
    </hlm-avatar-group>
  `,
})
export class AvatarGroupPreview {}
```

### Avatar Group Count

Usa `hlm-avatar-group-count` para añadir un contador al grupo.

```typescript
import { ChangeDetectionStrategy, Component } from '@angular/core';
import { HlmAvatarImports } from '@spartan-ng/helm/avatar';

@Component({
  selector: 'spartan-avatar-group-count-preview',
  standalone: true,
  imports: [HlmAvatarImports],
  changeDetection: ChangeDetectionStrategy.OnPush,
  template: `
    <hlm-avatar-group class="grayscale">
      <hlm-avatar>
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
      <hlm-avatar>
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
      <hlm-avatar>
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
      <hlm-avatar-group-count>+3</hlm-avatar-group-count>
    </hlm-avatar-group>
  `,
})
export class AvatarGroupCountPreview {}
```

### Avatar Group Icon

También puedes usar un icono dentro de `hlm-avatar-group-count`.

```typescript
import { ChangeDetectionStrategy, Component } from '@angular/core';
import { NgIcon, provideIcons } from '@ng-icons/core';
import { lucidePlus } from '@ng-icons/lucide';
import { HlmAvatarImports } from '@spartan-ng/helm/avatar';

@Component({
  selector: 'spartan-avatar-group-icon-preview',
  standalone: true,
  imports: [HlmAvatarImports, NgIcon],
  providers: [provideIcons({ lucidePlus })],
  changeDetection: ChangeDetectionStrategy.OnPush,
  template: `
    <hlm-avatar-group class="grayscale">
      <hlm-avatar>
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
      <hlm-avatar>
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
      <hlm-avatar>
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
      <hlm-avatar-group-count>
        <ng-icon name="lucidePlus" />
      </hlm-avatar-group-count>
    </hlm-avatar-group>
  `,
})
export class AvatarGroupIconPreview {}
```

### Sizes

Usa la propiedad `size` para cambiar el tamaño del avatar.

```typescript
import { ChangeDetectionStrategy, Component } from '@angular/core';
import { HlmAvatarImports } from '@spartan-ng/helm/avatar';

@Component({
  selector: 'spartan-avatar-sizes-preview',
  standalone: true,
  imports: [HlmAvatarImports],
  changeDetection: ChangeDetectionStrategy.OnPush,
  template: `
    <div class="flex flex-wrap items-center gap-2 grayscale">
      <hlm-avatar size="sm">
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
      <hlm-avatar>
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
      <hlm-avatar size="lg">
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" class="grayscale" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
    </div>
  `,
})
export class AvatarSizesPreview {}
```

### Dropdown

Puedes usar el componente `hlm-avatar` como disparador (trigger) para un menú desplegable.

```typescript
import { ChangeDetectionStrategy, Component } from '@angular/core';
import { HlmAvatarImports } from '@spartan-ng/helm/avatar';
import { HlmButtonImports } from '@spartan-ng/helm/button';
import { HlmDropdownMenuImports } from '@spartan-ng/helm/dropdown-menu';

@Component({
  selector: 'spartan-avatar-dropdown-preview',
  standalone: true,
  imports: [HlmAvatarImports, HlmDropdownMenuImports, HlmButtonImports],
  changeDetection: ChangeDetectionStrategy.OnPush,
  template: `
    <button hlmBtn variant="ghost" size="icon" class="rounded-full" [hlmDropdownMenuTrigger]="menu">
      <hlm-avatar>
        <img hlmAvatarImage src="/assets/avatar.png" alt="@spartan-ui logo" />
        <span hlmAvatarFallback>RG</span>
      </hlm-avatar>
    </button>
    <ng-template #menu>
      <hlm-dropdown-menu>
        <hlm-dropdown-menu-group>
          <button hlmDropdownMenuItem>Profile</button>
          <button hlmDropdownMenuItem>Billing</button>
          <button hlmDropdownMenuItem>Settings</button>
        </hlm-dropdown-menu-group>
        <hlm-dropdown-menu-separator />
        <hlm-dropdown-menu-group>
          <button hlmDropdownMenuItem variant="destructive">Log out</button>
        </hlm-dropdown-menu-group>
      </hlm-dropdown-menu>
    </ng-template>
  `,
})
export class AvatarDropdownPreview {}
```

## API Reference

### Helm (Estilos)

- `hlm-avatar`: Contenedor principal.
- `hlmAvatarImage`: Directiva para la imagen del avatar.
- `hlmAvatarFallback`: Directiva para el contenido de respaldo.
- `hlm-avatar-badge`: Componente para añadir una insignia.
- `hlm-avatar-group`: Contenedor para agrupar múltiples avatares.
- `hlm-avatar-group-count`: Componente para el contador de grupo.

### Brain (Lógica)

- `brn-avatar`: Primitiva lógica.
- `brnAvatarFallback`: Gestiona la visibilidad del fallback.
- `brnAvatarImage`: Gestiona la carga y estados de error de la imagen.
