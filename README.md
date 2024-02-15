# Patrón Compound Component en React

Este repositorio contiene un ejemplo de cómo aplicar el patrón Compound Component en React para crear componentes reutilizables y flexibles. El patrón Compound Component permite encapsular la lógica y la presentación de un conjunto de componentes relacionados, facilitando su uso y mantenimiento.

## Estructura del proyecto

El proyecto está estructurado de la siguiente manera:

- **src/components/**: Contiene los componentes relacionados con el producto.

  - **ProductCard.tsx**: Componente principal que actúa como contenedor para los componentes hijos.
  - **ProductImage.tsx**: Componente para mostrar la imagen del producto.
  - **ProductTitle.tsx**: Componente para mostrar el título del producto.
  - **ProductButtons.tsx**: Componente para mostrar los botones de incremento y decremento del producto.

- **src/hooks/**: Contiene el hook `useProduct` para manejar el estado del producto.

- **src/interfaces/**: Contiene las interfaces relacionadas con el producto.

- **src/pages/**: Contiene la página `ShoppingPage.tsx` donde se utiliza el componente `ProductCard` para mostrar productos en una tienda.

## Uso del patrón Compound Component

El patrón Compound Component se utiliza en el componente `ProductCard` para encapsular la lógica y presentación de los componentes relacionados con el producto. Los componentes `ProductImage`, `ProductTitle` y `ProductButtons` se utilizan dentro de `ProductCard` y se comunican a través de un contexto compartido (`ProductContext`).

En la página `ShoppingPage`, se muestra cómo utilizar el componente `ProductCard` para renderizar diferentes productos con sus respectivas imágenes, títulos y botones de incremento y decremento.

## Ejemplo de uso

```tsx
import {
  ProductCard,
  ProductImage,
  ProductTitle,
  ProductButtons,
} from "../components/";

const product = {
  id: "1",
  title: "Coffee Mug X",
  img: "/coffee-mug.png",
};

export const ShoppingPage = () => {
  return (
    <div>
      <h1>Shopping Store</h1>
      <hr />

      <div style={{ display: "flex", flexDirection: "row", flexWrap: "wrap" }}>
        <ProductCard product={product}>
          <ProductImage />
          <ProductTitle title="Coffee Mug XXX" />
          <ProductButtons />
        </ProductCard>

        <ProductCard product={product}>
          <ProductImage />
          <ProductTitle />
          <ProductButtons />
        </ProductCard>
      </div>
    </div>
  );
};
```
