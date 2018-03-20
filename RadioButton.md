
![radio](https://cloud.githubusercontent.com/assets/17389431/20752169/a6bda4a6-b6de-11e6-82b7-12a6159cf054.gif)

Un MLRadioButton es un widget que tiene dos estados, on y off. El uso del mismo, combinado con el MLRadioButtonCollection provee una estructura de selección de items de forma excluyente. 
 
# Radio Button

## Uso

#### Creación

###### Por XIB

para agregar un radio button a un xib, seguir los siguientes pasos:

1. Agreagar una vista al xib
2. Ponerle como custom class la clase MLRadioButton

![screen shot 2016-06-13 at 10 26 35 am](https://cloud.githubusercontent.com/assets/17389431/16090868/93ebd07e-3307-11e6-88aa-dd6f2e146ce6.png)

###### Por código usando Autolayout

Para crearlo usando Autolayouts, inicializar el botón con el siguiente método:

```objective-c
[[MLRadioButton alloc] init];
```
y luego aplicarle los constraints

#### Observaciones

El radio button preferentemente tiene que ser cuadrado de 15x15

#### Jerarquía

![mlradiobuttonclassdiagram](https://cloud.githubusercontent.com/assets/17389431/16456119/2b25c34c-3ded-11e6-837c-c655b4ef67e3.png)

#### Ejemplo de uso:

- Inicializando el radio button
``` objective-c
MLRadioButton *radioButton = [[MLRadioButton alloc] init];
```

- Seteándole el estado luego de que fue creado
``` objective-c
[radioButton off]; // Por default el MLRadioButton se seteará en off
```

- Verificando el estado
``` objective-c
[radioButton isOff];
```

# Radio Button Collection

## Uso

#### Creación

###### Con radio buttons

Se puede crear un radio button collection con un **NSArray** de **MLRadioButton** y ésto crea el **MLRadioButtonCollection** con el primer item en **fill** y el resto de los items en **clear**

``` objective-c
MLRadioButton *radioButton0 = [[MLRadioButton alloc] init];
MLRadioButton *radioButton1 = [[MLRadioButton alloc] init];
MLRadioButton *radioButton2 = [[MLRadioButton alloc] init];
    
MLRadioButtonCollection *radioButtonCollection = [MLRadioButtonCollection radioButtonCollectionWithRadioButtons:@[radioButton0, radioButton1, radioButton2]];
```

###### Con longitud

Se puede crear un radio button collection con una longitud y ésto creara internamente una lista de **MLRadioButton**.

``` objective-c
[MLRadioButtonCollection radioButtonCollectionWithRadioButtonCout:4]
```

Luego se puede acceder a ésta lita de la siguiente manera:

``` objective-c
[radioButtonCollection radioButtons]
```

#### Observaciones
Si el radio button se crea con 0 elementos o elementos negativos, éste lanzará una exception.


#### Interfáz

``` objective-c
/**
 *  MLRadioButtonCollection manage the exclusiveness of an array of MLRadioButtons
 */
@interface MLRadioButtonCollection : NSObject

/**
 *  Static initialiser that returns an instance of MLRadioButtonCollection.
 *  This method might be called only if you want to create the
 *  MLRadioButton objects, if you already have this object, whether you initialised theme in the
 *  xib file or by code, you might initialise the MLRadioButtonCollection with
 *  radioButtonCollectionWithRadioButtons: initialiser
 *
 *  @parms radioButtonCount    the amount of MLRadioButton objects that might initialise
 *  the return instance
 */
+ (instancetype)radioButtonCollectionWithRadioButtonCount:(NSUInteger)radioButtonCount;

/**
 *  Static initialiser that returns an instance of MLRadioButtonCollection.
 *  This method might be called only if you already have the
 *  MLRadioButton objects, if you dont have this object, you might initialise
 *  the MLRadioButtonCollection with radioButtonCollectionWithRadioButtonCount: initialiser
 *
 *  @parms radioButtons    An NSArray of MLRadioButtons
 */
+ (instancetype)radioButtonCollectionWithRadioButtons:(NSArray *)radioButtons;

/**
 *  Array of MLRadioButtons that will have exclusive selection
 */
- (NSArray *)radioButtons;

/**
 *  Changes the state of the MLRadioButton at the index sent by parameter and sets to off
 *  the old MLRadioButton with state in on
 *
 *  @parms index    index of selected MLRadioButton
 */
- (void)selectRadioButtonAtIndex:(NSUInteger)index;

/**
 *  Returns the index of the currently MLRadioButton with state in on
 */
- (NSUInteger)indexOfSelectedRadioButton;
```

###### Ejemplo de uso:

- Inicializando el radio button collection
``` objective-c
MLRadioButtonCollection *radioButtonCollection = [MLRadioButtonCollection radioButtonCollectionWithRadioButtonCout:3];
```

- Seleccionando un radio button en particular
``` objective-c
[radioButtonCollection selectRadioButtonAtIndex:2];
```

- Obteniendo el índice del radio button seleccionado
``` objective-c
NSUInteger indexOfSelectedRadioButton = [radioButtonCollection indexOfSelectedRadioButton];
```