# Descripcion

Para seterar un error a una vista, la vista tiene que tener la siguiente jerarquia:

![](http://i62.tinypic.com/9va6u8.png)

Donde UIView es la vista a la que queremos insertarle el error y contentView es una vista que servira de anclaje para nuestro error. El error se situara por debajo de contentView, modificando el alto de UIView. Generalmente, contentView tendra el mismo frame que UIView. Esquema luego de insertar el error:

![](http://i58.tinypic.com/dwqmpi.png)

Funciona tanto para vistas con autolayout como vistas sin autolayout

# Importante

El seteo de error no adicionara el retainCount de UIView. Lo que si se genero, es un cacheo de la vista de error. Esto se hizo con NSMapTable. Como es sabido, el purgueo de los objetos de NSMapTable puede tardar mas de lo esperado. Y, al esconderse el error, se quita la UIView de este caching. Por lo que, si nos molesta este tiempo de vida extra sobre UIView, debemos quitar el error cuando no utilicemos mas esta vista.

# Ejemplo

Para setear un error:

``` objective-c
MLUIErrorSetter* errorSetter = [[MLUIErrorSetter alloc] init];
[errorSetter setError:@"Soy un error" inView:self.firstTableViewCell];
```

Para esconder un error

``` objective-c
MLUIErrorSetter* errorSetter = [[MLUIErrorSetter alloc] init];
[errorSetter hideErrorOfView:self.firstTableViewCell];
```