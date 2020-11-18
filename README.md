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
### Comentar solo donde sea necesario
Las ventajas de comentar código lo mínimo posible son: 

1. Mantendrá el código visualmente libre de desorden.

1. Evitará un posible conflicto entre el comentario y el código si modifica el código en algún momento posterior.

1. En componentes, después de los imports comentar la función general del componente.

### Nombrar el componente después dela función

### Desestructura los props

### No utilizar `React.createElement`
A menos que se esté inicializando la App desde un archivo que no es JSX.

### Cuidado con las otras convenciones de nomenclatura

### Separar el manejo de esatdo del renderizado

### Usar useReducer si useState se vuelve complejo
Cuando empieza a haber múltiples estados a los que seguir, el uso de useState comienza a ser dificil de manejar. Al hacer uso de useState, muchas veces se tienen que declarar funciones dentro del hook para averiguar la siguiente parte del estado, además de escribir la lógica, mientras que con useReducer no se tiene que hacer eso y en su lugar se mueven a la función reductora. Solo se debe llamar al tipo de acción y listo.

### Poner en orden las cosas
Escribir los import en un orden definido ayudará a la ontención de un código limpio.
1. React import
1. Imports de librerías (en orden alfabético)
1. Imports absolutos del proyecto (en orden alfabético)
1. Imports relativos (en orden alfabético)
1. import * as
1. import './<some file>.<some ext>'
  
### Usar librerías de snippets
La principal ventaja de usar estas librerías es poder manternse al día respecto a la sintaxis del lenguaje. Sumado a esto, ayudan a poder mantener el código libre de errores. Existen distintas librerías, como ES7 React, Redux, JS Snippets, entre otras.

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
    // no recomendado
    import Footer from './Footer/Footer';

    // no recomendado
    import Footer from './Footer/index';

    // Recomendado
    import Footer from './Footer';
    ```
- ***Nombres de componentes de orden superior***: 

- ***Nombre de props***: Evita usar 
    ```jsx
    // no recomendado
    <MyComponent style="fancy" />

    // no recomendado
    <MyComponent className="fancy" />

    // Recomendado
    <MyComponent variant="fancy" />
    ```
