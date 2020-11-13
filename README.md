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

  ```jsx
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
