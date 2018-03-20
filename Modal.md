## Uso

#### Agregar el modal

```objective-c
+ (instancetype)showModalWithViewController:(UIViewController *)innerViewController title:(NSString *)title actionTitle:(NSString *)actionTitle actionBlock:(void (^)())actionBlock secondaryActionTitle:(NSString *)secondaryTitle secondaryActionBlock:(void (^)())secondaryActionBlock dismissBlock:(void (^)())dismissBlock;
```

- innerViewController: ViewController que se quiere mostrar en el modal

- title: título del modal, si viene el nil el modal se presenta sin título

- actionTitle: título del botón del modal

- actionBlock: bloque a ejecutar cuando se presione el botón (si el actionTitle o el actionBlock son nil no se mostrará el botón)

- secondaryTitle: título del botón secundario

- secondaryActionBlock: bloque a ejecutar cuando se presione el botón secundario (si el secondaryTitle o el secondaryActionBlock son nil no se mostrará el botón secundario)

- dismissBlock: Bloque a ejecutar cuando el modal desaparece.

Existen otras variantes del mismo método que permiten mostrar el modal pasándole menos parámetros. Se muestran alguno de ellos más adelante.

#### Ocultar el modal

```objective-c
- (void)dismissModal;
```
Esto permite ocultar el modal programáticamente.

#### Consideraciones acerca de la vista
El view controller que se le envía al modal debe tener AUTOLAYOUT, sino no funcionará. A su vez,su ancho no puede estar fijo, debe tener las constraints necesarias para que el mismo se adapte a su vista padre.

Otra observación es que el blur de la vista del modal es estática. Esto significa que cualquier animación que se corra detrás de la vista del modal no se podrá ver.

## Estilos
#### Modal simple
![simulator screen shot - iphone 6 - 2018-03-20 at 17 40 06](https://user-images.githubusercontent.com/10763919/37681736-45a4fe0e-2c66-11e8-8ac8-f423a64d96f5.png)

###### Ejemplo de uso
```objective-c
[MLModal showModalWithViewController:[[ViewController alloc] init]];
```
#### Configuraciones extra

###### Agregarle título
![simulator screen shot - iphone 6 - 2018-03-20 at 17 40 08](https://user-images.githubusercontent.com/10763919/37681788-694a11a0-2c66-11e8-9af0-0c85f568edf5.png)

```objective-c
[MLModal showModalWithViewController:[[ViewController alloc] init] title:@"Title"];;
```

###### Agregarle título y un botón


```objective-c
[MLModal showModalWithViewController:[[ViewController alloc] init] title:@"Title" actionTitle:@"Button" actionBlock: ^{}];
```

###### Agregarle título y dos botones
![simulator screen shot - iphone 6 - 2018-03-20 at 17 40 11](https://user-images.githubusercontent.com/10763919/37681845-977fbc28-2c66-11e8-8525-f87cba6936e5.png)

```objective-c
[MLModal showModalWithViewController:[[ViewController alloc] init] title:@"Title" actionTitle:@"Button" actionBlock: ^{} secondaryActionTitle:@"Apply" secondaryActionBlock: ^{} dismissBlock:nil];
```