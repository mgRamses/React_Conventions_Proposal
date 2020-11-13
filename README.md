# React_Conventions_Proposal
Recopilación de buenas prácticas para React en proyectos de mediana a gran escala.

### Mantener componentes pequeños y orientados a una función específica.

1. Un solo componente debe representar un fragmento específico de su página o modificar un comportamiento particular.

1. Los componentes deben tener una función específica y ser independientes, esto favorece las pruebas y el mantenimiento.

1. Cada pequeño componente podrá ser usado a través de múltiples proyectos.

### La reutilización es importante, mantener la creación de nuevos componentes al mínimo requerido.

1. Si algún componente se vuelve enorme, difícil de manejar y difícil de mantener, es mejor dividirlo en tantos componentes más pequeños como sea necesario.

1. Los componentes deben ser lo suficientemente abstractos, pero no demasiado complejos.

### DRY. Consolida código duplicado.

1. Escudriñar el código en busca de patrones y similitudes.

  ```elixir
    const buttons = ['facebook', 'twitter', 'youtube'];

    return (
    <div>
      {
        buttons.map( (button) => {
          return (
            <IconButton
              onClick={doStuff( button )}
              iconClass={button}
            />
          );
        } )
      }
    </div>
   );
   ```
### Comment only where necessary
Las ventajas de comentar código lo mínimo posible son: 

1. Mantendrá el código visualmente libre de desorden.

1. Evitará un posible conflicto entre el comentario y el código si modifica el código en algún momento posterior.

### Nombrar el componente después dela función

### Usar mayúsuclas para los nombres de componentes

### Cuidado con las otras convenciones de nomenclatura

### Separar el manejo de esatdo del renderizado

### Usar librerías de snippets

### Escribir pruebas para todo el código

### Utilizar un linter, romper con líneas demasiado largas

## Naming

- ***Extensiones***: Usar la extensión .jsx para los componentes.
- ***Nombre de archivos***: Usar PascalCase para los nombres de archivos. 
- ***Nombres de referencias***: Usar PascalCase para componentes de React y camelCase para sus instancias. 
    ```jsx
    // no recomendado
    import reservationCard from './ReservationCard';

    // Recomendado
    import ReservationCard from './ReservationCard';

    // no recomendado
    const ReservationItem = <ReservationCard />;

    // Recomendado
    const reservationItem = <ReservationCard />;
    ```
- ***Nombres de componentes**: Usar el nombre del archivo como el nombre del componente. Por ejemplo, ReservationCard.jsx deberá de tener un nombre de referencia de ReservationCard. 
    ```jsx
    // bad
    import Footer from './Footer/Footer';

    // bad
    import Footer from './Footer/index';

    // good
    import Footer from './Footer';
    ```
- ***Nombres de componentes de orden superior***: 

- ***Nombre de props***: Evita usar 
    ```jsx
    // bad
    <MyComponent style="fancy" />

    // bad
    <MyComponent className="fancy" />

    // good
    <MyComponent variant="fancy" />
    ```
