
![switch](https://cloud.githubusercontent.com/assets/17389431/20752170/a6d7f96e-b6de-11e6-95b3-dca8204ca585.gif)

Un MLSwitch es un widget que tiene dos estados, fill y clear. 

## Uso

#### Creación

###### Por XIB

para agregar un radio button a un xib, seguir los siguientes pasos:

1. Agreagar una vista al xib
2. Ponerle como custom class la clase MLSwitch

![screen shot 2016-06-23 at 10 56 42 am](https://cloud.githubusercontent.com/assets/17389431/16340000/0a096cc6-39fc-11e6-9117-7e69ffaf4f71.png)

###### Por código usando Autolayout
Para crearlo usando Autolayouts, inicializar el botón con el siguiente método:

```objective-c
[[MLSwitch alloc]init];
```
y luego aplicarle los constraints

#### Jerarquía

![mlswitchclassdiagram](https://cloud.githubusercontent.com/assets/17389431/16456118/2a12211c-3ded-11e6-83c8-c53c5f35e100.png)

#### Ejemplo de uso
- Inicializando el switch
``` objective-c
MLSwitch *mlSwitch = [[MLSwitch alloc]init];
```
- Seteándole el estado luego de que fue creado
``` objective-c
[mlSwitch off];
```

- Verificando el estado
``` objective-c
[mlSwitch isOff];
```
