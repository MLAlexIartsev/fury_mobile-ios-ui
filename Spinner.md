## Uso

#### Creación

###### Por XIB
Para agregar un spinner por xib, seguir los siguientes pasos:

1. Agregar una vista al xib
2. Ponerle como custom class la clase MLSpinner

![captura de pantalla 2016-05-05 a las 16 13 48](https://cloud.githubusercontent.com/assets/8038502/15054174/80932a18-12dc-11e6-8fc7-656dc66d4d88.png)

#### Ejemplo de uso

###### Creádolo por código
```objective-c
//crear el spinner
MLSpinner *spinner = [[MLSpinner alloc]initWithStyle:MLSpinnerStyleWhiteBig text:@"text"];

//agregarlo a la vista padre
[self addSubview:spinner];

//agregarle constraints
[self addConstraints:[NSLayoutConstraint constraintsWithVisualFormat:@"H:|-0-[smallSpinner]-0-|" options:0 metrics:nil views:@{@"smallSpinner" : self.smallSpinner}]];
[self addConstraints:[NSLayoutConstraint constraintsWithVisualFormat:@"V:|-0-[smallSpinner]-0-|" options:0 metrics:nil views:@{@"smallSpinner" : self.smallSpinner}]];

//mostrarlo animado
[spinner showSpinner];
```

###### Creádolo por xib
```objective-c
//setearle el estilo
[spinner setStyle:MLSpinnerStyleWhiteBig];
//setearle el texto
[spinner setText:@"text"];
//mostrarlo animado
[spiner showSpinner];
```

###### Por código usando Autolayout
Para crealo usando Autolayout, inicializar el spinner con alguno de los siguientes métodos:
```objective-c
[[MLSpinner alloc] initWithStyle: MLSpinnerStyle];
```

```objective-c
[[MLSpinner alloc] initWithStyle: MLSpinnerStyle text:text];
```

y luego aplicarle las constraints.

## Estilos
Existen distintos estilos predefinidos para el spinner. Para setearle los estilos a los botones, se puede crearlos con su estilo o setearle el estilo luego de crearlos.

#### Spinners grandes
###### MLSpinnerStyleBlueBig
Es el estilo por defecto. Acepta texto (como máximo dos líneas). El color del spinner pasa de azul a amarillo.

- Sin texto

![captura de pantalla 2016-05-05 a las 16 30 26](https://cloud.githubusercontent.com/assets/8038502/15054776/80aaae4c-12df-11e6-8e7d-cd80cf545864.png)

- Con texto

![captura de pantalla 2016-05-05 a las 16 31 14](https://cloud.githubusercontent.com/assets/8038502/15054777/82362070-12df-11e6-8483-4fe86b479eca.png)

###### MLSpinnerStyleWhiteBig
Acepta texto (como máximo dos líneas). El color del spinner pasa de azul a blanco.

- Sin texto

![captura de pantalla 2016-05-05 a las 16 30 26](https://cloud.githubusercontent.com/assets/8038502/15054776/80aaae4c-12df-11e6-8e7d-cd80cf545864.png)

- Con texto

![captura de pantalla 2016-05-05 a las 16 31 02](https://cloud.githubusercontent.com/assets/8038502/15054812/ae782a84-12df-11e6-9f89-096bccb53644.png)

#### Spinners chicos
###### MLSpinnerStyleBlueSmall
No acepta texto. Por más que se le setee texto, el mismo será ignorado.

![captura de pantalla 2016-05-05 a las 16 39 57](https://cloud.githubusercontent.com/assets/8038502/15054879/0fdd7f9a-12e0-11e6-91d1-f6359c8f1666.png)

###### MLSpinnerStyleWhiteSmall
No acepta texto. Por más que se le setee texto, el mismo será ignorado.


![captura de pantalla 2016-05-05 a las 16 39 44](https://cloud.githubusercontent.com/assets/8038502/15054875/07e14f74-12e0-11e6-9898-26cb52c51dc5.png)
