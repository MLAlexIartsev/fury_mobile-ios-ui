
![check](https://cloud.githubusercontent.com/assets/17389431/20752168/a6bcce6e-b6de-11e6-83f1-9e1d638acd9d.gif)


Un MLCheckBox es un widget que tiene dos estados, on y off. El uso del mismo, combinado con el MLCheckList provee una estructura de selección de items. 
 
# Check Box

## Uso

#### Creación

###### Por XIB

para agregar un radio button a un xib, seguir los siguientes pasos:

1. Agreagar una vista al xib
2. Ponerle como custom class la clase MLRadioButton

![screen shot 2016-06-15 at 12 49 29 pm](https://cloud.githubusercontent.com/assets/17389431/16086978/c276a97e-32f7-11e6-8d82-af90463b0970.png)


###### Por código usando Autolayout
Para crearlo usando Autolayouts, inicializar el botón con el siguiente método:

```objective-c
[[MLCheckBox alloc] init];
```
y luego aplicarle los constraints

#### Observaciones
El radio button preferentemente tiene que ser cuadrado de 15x15

###### Jerarquía

![mlcheckboxclassdiagram](https://cloud.githubusercontent.com/assets/17389431/16456122/2c3e5316-3ded-11e6-8d5d-811580fff541.png)

###### Ejemplo de uso:
- Inicializando el check button
``` objective-c
MLCheckBox *checkBox = [[MLCheckBox alloc] init];
```
- Seteándole el estado luego de que fue creado
``` objective-c
[checkBox off];
```

- Verificando el estado
``` objective-c
[checkBox isOff];
```

# Check List

## Uso

#### Creación

###### Con check buttons

Se puede crear un check list con un **NSArray** de **MLCheckBox** y ésto crea el **MLCheckList** con todos los estados de los check buttons en **clear**

``` objective-c
MLCheckBox *checkBox0 = [[MLCheckBox alloc] init];
MLCheckBox *checkBox1 = [[MLCheckBox alloc] init];
MLCheckBox *checkBox2 = [[MLCheckBox alloc] init];    

MLCheckList *checkList = [MLCheckList checkListWithCheckBoxes:@[checkBox0, checkBox1, checkBox2]];
```

###### Con longitud
Se puede crear un check list con una longitud y ésto creara internamente una lista de **MLCheckBox**.

``` objective-c
[MLCheckList checkListWithCheckBoxCount:4]
```

Luego se puede acceder a ésta lita de la siguiente manera:

``` objective-c
[checkList checkBoxes]
```

#### Observaciones
Si el check list se crea con 0 elementos o elementos negativos, éste lanzará una exception.


#### Interfáz

``` objective-c
/**
 *  MLCheckList manage the multiple selection of an array of MLCheckBox
 */
@interface MLCheckList : NSObject

/**
 *  Static initialiser that returns an instance of MLCheckList.
 *  This method might be called only if you want to create the
 *  MLRadioButton objects, if you already have this object, whether you initialised theme in the
 *  xib file or by code, you might initialise the MLCheckList with
 *  checkListWithCheckBoxes: initialiser
 *
 *  @parms checkBoxCount    the amount of MLRadioButton objects that might initialise
 *  the return instance
 */
+ (instancetype)checkListWithCheckBoxCout:(NSUInteger)checkBoxCount;

/**
 *  Static initialiser that returns an instance of MLCheckList.
 *  This method might be called only if you already have the
 *  MLCheckBox objects, if you dont have this object, you might initialise
 *  the MLCheckList with radioButtonCollectionWithRadioButtonCount: initialiser
 *
 *  @parms checkBoxes    An array of MLCheckBox
 */
+ (instancetype)checkListWithCheckBoxes:(NSArray *)checkBoxes;

/**
 *  Returns an array of MLCheckBox
 */
- (NSArray *)checkBoxes;

/**
 *  Toggles de state of the MLCheckBox to on if its current state is off, or to off if its current state is on
 */
- (void)toggleCheckBoxAtIndex:(NSUInteger)index;

/**
 *  Returns the indexes in an array of the currently MLCheckBox with state in on
 */
- (NSArray *)indexesOfSelectedCheckBoxes;

@end
```

#### Ejemplo de uso:
- Inicializando el check list
``` objective-c
MLCheckList *checkList = [MLCheckList checkListWithCheckBoxCount:3];
```
- Seleccionando un radio button en particular
``` objective-c
[checkList toggleRadioButtonAtIndex:2];
```

- Obteniendo el índice del radio button seleccionado
``` objective-c
NSArray *indexesOfSelectedCheckBoxes = [checkList indexesOfSelectedCheckBoxes];
```