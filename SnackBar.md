## Uso

Para mostrar el snackbar invocar al método
```objective-c
 + (instancetype)showWithTitle:(NSString *)title actionTitle:(NSString *)buttonTitle actionBlock:(void (^)())actionBlock type:(MLSnackbarType *)type duration:(MLSnackbarDuration)duration dismissGestureEnabled:(BOOL)dismissGestureEnabled;
```

| Parameter | Meaning |
|:----------|:--------|
**title** | título del snackbar
**buttonTitle** | texto del botón del snackbar
**actionBlock** | bloque a ejecutar cuando se presione el botón.
**type** | tipo de snackbar. Se mostrarán los distintos tipos más adelante.
**duration** | tiempo que el snackbar permanece visible. Se explicarán las duraciones más adelante.
**dismissGestureEnabled** | indica si el snackBar se puede dismissear con un gesto

Para ocultar el snackbar:

- Dismissearlo con el gesto
- Dismissearlo por código 

#### Duración

| Type | Meaning |
|:-----|:--------|
| `MLSnackbarDurationIndefinitely` | El snackbar **no desaparece** por sí solo. Para poder dismissearlo, utilizar el gesto de dismiss o dismissearlo por código. |
| `MLSnackbarDurationShort` | El snackbar desaparece luego de **2 segundos** |
| `MLSnackbarDurationLong` | El snackbar desaparece luego de **3.5 segundos** |

```objective-c
 [snackbar dismissSnackbar];
```
## Estilos
Existen tres estilos definidos. Sin embargo, es posible crear nuevos estilos para poder customizar el snackbar. Para realizarlo, extender de la clase MLSnackbarType y setear los valores para las variables.

#### Default Snackbar
![captura de pantalla 2016-02-29 a las 14 37 17](https://cloud.githubusercontent.com/assets/8038502/13403095/11802b30-def2-11e5-9522-e81dea5c4d88.png)


Para generar este estilo utilizar el método de clase
```objective-c
[MLSnackbarType defaultType];
```

#### Success Snackbar
![captura de pantalla 2016-02-29 a las 14 34 02](https://cloud.githubusercontent.com/assets/8038502/13403082/0928d7c0-def2-11e5-8a4a-ff827f9be2fd.png)

Para generar este estilo utilizar el método de clase
```objective-c
[MLSnackbarType successType];
```
 
#### Error Snackbar
![captura de pantalla 2016-02-29 a las 14 36 58](https://cloud.githubusercontent.com/assets/8038502/13403092/0f7ae33e-def2-11e5-879e-7348ff2cbb74.png)

Para generar este estilo utilizar el método de clase
```objective-c
[MLSnackbarType errorType];
```