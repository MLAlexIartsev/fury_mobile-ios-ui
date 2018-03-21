## Uso

Este componente tiene 2 utilidades adicionales a usar un `UITextView` básico:
* Contener un placeholder (aka hint).
* Poder crecer en tamaño desde un mínimo hasta un máximo de líneas.

Ambas funciones son opcionales. Tanto el `UITextView` contenido como el `UILabel` que hace al placeholder están expuestos para cualquier control o cambio que un determinado escenario requiera.

#### Creación

La creación debe hacerse desde **Interface Builder** (IB) a partir de un `UIView` y cambiando la clase a `MLTextView`.
Como se muestra en la imagen:

![screen shot 2017-05-23 at 3 13 35 pm](https://cloud.githubusercontent.com/assets/5380895/26373462/0813814e-3fd8-11e7-8bef-d4013b27b1d6.png)

Luego se debe agregar un constraint de height al componente con cualquier prioridad **Low** o **High** (no Required).

Varios de los parámetros de configuración pueden cambiarse desde **Attribute Inspector**.

## Cambio de configuración

Ya sea que se cambia la font, alguno de los valores de mínimo y máximo, de tamaño variable a fijo o cualquier otro cambio de configuración es necesario llamar a la función `styleHasChanged` para que esos cambios se terminen de aplicar.

Ejemplo:
```objective-c
[self.mlTextView.textView setFont:[UIFont ml_extraboldSystemFontOfSize:26]];
[self.mlTextView.textViewPlaceholder setFont:[UIFont ml_extraboldSystemFontOfSize:26]];
self.mlTextView.flexibleSize = false;
[self.mlTextView styleHasChanged]; // <--- This
```

Si los cambios se hacen desde IB no hace falta llamar al método.


#### Placeholder y texto

Si se desea setear un texto para que quede de placeholder, se puede indicar desde IB con el atributo **Placeholder** o bien desde código. El texto del textview también puede setearse desde ambos lugares:

```objective-c
self.mlTextView.placeholder = @"Un placeholder";
self.mlTextView.text = @"Un texto";
```

Es importante notar que si bien se puede acceder al `UITextView` y al `UILabel` contenidos, no es recomendable setear los textos sin usar los métodos provistos.

En cambio, la fuente y propiedades adicionales de ambos componentes si deben indicarse directamente como se indica en [Cambio de configuración](https://github.com/mercadolibre/mobile-ios_ui/wiki/TextView#cambio-de-configuraci%C3%B3n).

El placeholder no puede ocupar mas de una línea, si es mas largo se elipsea el final. Podria cambiarse tocando el UILabel interior pero no se recomienda.


#### Tamaño fijo o variable

Por default el tamaño es variable. Se puede cambiar desde IB o bien por código (`flexibleSize`). Es importante tener en cuenta que una vez cambiado a fijo (`flexibleSize = NO`) no puede volver a activarse. Al hacer el cambio hace falta llamar a `styleHasChanged`:
```objective-c
self.mlTextView.flexibleSize = false;
[self.mlTextView styleHasChanged]; 
```

Si el tamaño es fijo, el mismo se va a fijar por las constraints externas. Si el `MLTextView` que va a usarse es fijo y de un alto inamobible, uno tendería a ponerle un constraint de height **Required** y, si bien va a funcionar, se sugiere ponerlo simplemente **High** y dejar `flexibleSize` en false. 


#### Cantidad de líneas

Los parámetros para controlar la cantidad de líneas se pueden setear tanto desde IB como desde código. Si se elige el último es importante llamar a `styleHasChanged` luego:
```objective-c
self.mlTextView.minLines = 2;
self.mlTextView.maxLines = 4;
[self.mlTextView styleHasChanged]; 
```

Por default `minLines` es 1 y `maxLines` es 1 que implicaría algo muy similar a tamaño fijo con la diferencia de que el tamaño del `MLTextView` va a adaptarse hasta tener la altura de una línea para la font elegida ignorando el constraint externo de altura.

Tanto `minLines` como `maxLines` son ignorados si es tamaño es fijo.

Ambos deben ser mayores a cero y `maxLines` mayor que `minLines`.

## Limitaciones

Actualmente no se puede:
* Volver `flexibleSize` a true una vez que fue cambiado a false.
* Evitar crear la constraint externa de height.
* Setear el texto por IB.
* Cambiar la font por IB.
* Ver la preview del componente renderizado en IB.


## Usos comunes

Se adjunta video de uso común. Puede verse en [MLMessages](https://github.com/mercadolibre/myml-ios_messages) la herramienta en uso. Ambas pantallas (la de escribir y la de adjuntar archivos) contienen un `MLTextView`, una con tamaño variable y la otra fijo.

![Ejemplo de uso](https://cloud.githubusercontent.com/assets/5380895/26373443/f755b5fc-3fd7-11e7-9887-c2a5680ca504.gif)

