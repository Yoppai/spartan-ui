# Card Component

Muestra una tarjeta con encabezado, contenido y pie de página.

## Instalación

```bash
ng g @spartan-ng/cli:ui card
```

## Uso Básico

### Importación

```typescript
import { HlmCardImports } from '@spartan-ng/helm/card';
```

### Template

```html
<section hlmCard>
  <div hlmCardHeader>
    <h3 hlmCardTitle>Título de la Tarjeta</h3>
    <p hlmCardDescription>Descripción detallada aquí.</p>
    <div hlmCardAction>
      <button hlmBtn variant="ghost">Opciones</button>
    </div>
  </div>
  <div hlmCardContent>
    Este es el contenido principal de la tarjeta.
  </div>
  <div hlmCardFooter>
    <button hlmBtn class="w-full">Acción Principal</button>
  </div>
</section>
```

## Ejemplos

### Tarjeta Pequeña (Compacta)

Usa la propiedad `size="sm"` para una apariencia más compacta.

```html
<hlm-card size="sm">
  <hlm-card-header>
    <h3 hlmCardTitle>Sm Card</h3>
  </hlm-card-header>
  <div hlmCardContent>Contenido reducido.</div>
</hlm-card>
```

### Tarjeta con Imagen

Puedes integrar imágenes y estados de mezcla de colores.

```html
<hlm-card class="relative overflow-hidden pt-0">
  <img src="https://images.unsplash.com/photo..." alt="Cover" class="aspect-video w-full object-cover" />
  <hlm-card-header>
    <div hlmCardAction>
      <span hlmBadge variant="secondary">Nuevo</span>
    </div>
    <h3 hlmCardTitle>Evento de Diseño</h3>
    <p hlmCardDescription>Charla práctica sobre APIs.</p>
  </hlm-card-header>
</hlm-card>
```

## API Reference

### Helm (Estilos)

- `hlmCard`: Directiva/Componente contenedor.
  - **Inputs**: `size` (`default` | `sm`).
- `hlmCardHeader`: Cabecera de la tarjeta.
- `hlmCardTitle`: Estilo para el título.
- `hlmCardDescription`: Estilo para la descripción.
- `hlmCardAction`: Contenedor para acciones en la cabecera (derecha).
- `hlmCardContent`: Área de contenido principal.
- `hlmCardFooter`: Pie de la tarjeta.
