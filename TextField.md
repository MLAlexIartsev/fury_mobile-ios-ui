## Uso

#### Creación

Existen dos opciones, dependiendo si se quiere multilinea o no.

###### Caso de una sola linea

```objective-c
MLTitledSingleLineTextField * textField = [[MLTitledSingleLineTextField alloc]init];
        textField.placeholder = @"un placeholder";
        textField.title = @"un título";
```

###### Caso de más de una línea

```objective-c
MLTitledMultiLineTextField * textField = [[MLTitledMultiLineTextField alloc]init];
        textField.placeholder = @"un placeholder";
        textField.title = @"un título";
```

###### Por xib
Agregar una UIView al xib y luego definirle la clase custom MLTitledSingleLineTextField o MLTitledMultiLineTextField según corresponda.

#### Cantidad máxima de caracteres



Se puede limitar la cantidad máxima de caracteres que se pueden ingresar por código:
```objective-c
tf.maxCharacters = 30;
```

Si se deseara, se puede ocultar el contador visual tanto por código:
```objective-c
tf.charactersCountVisible = NO;
```

#### Cantidad máxima de líneas 

Se puede limitar la cantidad de líneas por código:
```java 
tf.maxLines = 2;
```
Sólo se encuentra disponible para el textField multilinea

## Estilos

#### Habilitar/Deshabilitar el text field 

Es posible deshabilitar el text field por código:
```objective-c 
tf.state = MLTitledTextFieldStateDisabled;
```

![textfield-disable](https://user-images.githubusercontent.com/10763919/37730498-9f62d00c-2d1e-11e8-8648-4ff438db2c4a.png)

Por default el textField inicia habilitado.

#### Hint

![textfield-hint](https://user-images.githubusercontent.com/10763919/37730652-fd694b7c-2d1e-11e8-8bbf-13966d670cbe.png)

Se puede setear el hint por código:
```objective-c 
tf.placeholder = @"placeholder";
```

#### Error 

![textfield-error](https://user-images.githubusercontent.com/10763919/37730731-2fd67aa8-2d1f-11e8-8804-2b91460dd808.png)

Es posible setear un error de la siguiente manera:
```objective-c 
tf.errorDescription = @"A short error description";
```

El error automáticamente se va cuando el usuario modifica el texto ingresado.

#### Label 

![screen shot 2016-06-23 at 5 44 20 pm](https://cloud.githubusercontent.com/assets/8038502/16319567/2583689a-396a-11e6-853f-9961878a0d2b.png)


Se puede setear el título por código:
```objective-c 
tf.title = @"Textfield lineas ilimitadas";
```

#### Helper

<img width="343" alt="screen shot 2018-03-21 at 3 49 27 pm" src="https://user-images.githubusercontent.com/10763919/37730894-8df03b10-2d1f-11e8-9aec-6378d8582489.png">

Se puede setear el helper por código:
```objective-c
tf.helperDescription = @"Helper Description";
```

#### Centrado

<img width="337" alt="screen shot 2018-03-21 at 11 17 08 am" src="https://user-images.githubusercontent.com/10763919/37731024-dd7ad21c-2d1f-11e8-95f5-fc744fbfbde9.png">

Se puede centrar el textfield por código:
```objective-c
tf.setupInnerTextWithAlignment:NSTextAlignmentCenter];
```
 