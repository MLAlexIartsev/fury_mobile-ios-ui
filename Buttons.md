## Uso

#### Creación

###### Por XIB
Para agregar un botón por xib, seguir los siguientes pasos:

1. Agregar una vista al xib
2. Ponerle como custom class la clase MLButton

![captura de pantalla 2016-02-23 a las 9 46 14](https://cloud.githubusercontent.com/assets/8038502/13251977/4e9f159c-da12-11e5-88ff-ce1b4829de3d.png)

###### Por código usando Autolayout
Para crealo usando Autolayouts, inicializar el botón con el siguiente método:
```objective-c
MLButton *button = [[MLButton alloc] initWithConfig:[MLButtonStylesFactory configForButtonType:MLButtonTypePrimaryAction]];
```

y luego aplicarle las constraints.

### Custom Style
Se puede crear un botón sin utilizar los estilos predeterminados. Creando un objeto del tipo `MLButtonConfig` se pueden configurar los distintos estados.
Cada estado es del tipo `MLButtonConfigStyle` el cual permite configurar tres propiedades 
* `contentColor`
* `backgroundColor`
* `borderColor`

## Estilos
Existen distintos estilos predefinidos para los botones.

#### Botón de acción principal
Es el estilo por defecto.

![captura de pantalla 2016-02-23 a las 10 15 55](https://cloud.githubusercontent.com/assets/8038502/13252686/dd1f515c-da16-11e5-8643-e39cda17ca9b.png)

###### Ejemplo de uso:
``` objective-c
[[MLButton alloc] initWithConfig:[MLButtonStylesFactory configForButtonType:MLButtonTypePrimaryAction]];
```

#### Botón de acción secundaria

![captura de pantalla 2016-02-23 a las 10 16 19](https://cloud.githubusercontent.com/assets/8038502/13252703/ee3467d4-da16-11e5-9e00-2099fab8c9be.png)

###### Ejemplo de uso:
``` objective-c
[[MLButton alloc] initWithConfig:[MLButtonStylesFactory configForButtonType:MLButtonTypeSecondaryAction]];
```

#### Botón de opción principal

![captura de pantalla 2016-02-23 a las 10 17 23](https://cloud.githubusercontent.com/assets/8038502/13252713/f72cc0f2-da16-11e5-8b87-95059a4bd649.png)

#### Botón de opción secundaria

![captura de pantalla 2016-02-23 a las 10 20 47](https://cloud.githubusercontent.com/assets/8038502/13252753/2c00aed8-da17-11e5-90c8-db13525a6b14.png)

###### Ejemplo de uso:
``` objective-c
[[MLButton alloc] initWithConfig:[MLButtonStylesFactory configForButtonType:MLButtonTypeSecondaryOption]];
```