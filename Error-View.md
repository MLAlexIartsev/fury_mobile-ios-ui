## Uso

Esta vista se utiliza para mostrar errores en pantalla completa. Para mostrar la error view invocar el siguiente método:
```objective-c
 + (MLGenericErrorView *)genericErrorViewWithImage:(UIImage *)image
                                            title:(NSString *)title
                                         subtitle:(NSString *)subtitle
                                      buttonTitle:(NSString *)buttonTitle
                                      actionBlock:(MLVoidBlock)actionBlock
```


- image: Imagen que hace referencia al error.
- title: Título del error.
- subtitle: Subtítulo del error. Información extra sobre el mismo.
- buttonTitle: Texto del botón de la error view.
- actionBlock: Bloque a ejecutar cuando se presione el botón.

Como cualquier `UIView`, requerirá ser agregada a la jerarquía de vistas, y aplicar las restricciones necesarias para visualizarse en pantalla completa.

A modo de ejemplo:
```objective-c
MLGenericErrorView *errorView = [MLGenericErrorView genericErrorViewWithImage:[UIImage imageNamed:@"MLNetworkError"]
                                                                        title:@"¡Parece que no hay Internet!"
                                                                     subtitle:@"Revisa tu conexión para seguir navegando."
                                                                  buttonTitle:@"Reintentar"
                                                                  actionBlock:^{/*actionBlock*/}];
    
errorView.translatesAutoresizingMaskIntoConstraints = NO;
[view addSubview:errorView];
    
// Setup AutoLayout constraints
NSDictionary *views = @{@"errorView":errorView};
    
[view addConstraints:[NSLayoutConstraint constraintsWithVisualFormat:@"V:|-0-[errorView]-0-|"
                                                             options:0
                                                             metrics:nil
                                                               views:views]];
    
[view addConstraints:[NSLayoutConstraint constraintsWithVisualFormat:@"H:|-0-[errorView]-0-|"
                                                             options:0
                                                             metrics:nil
                                                               views:views]];
```

## ¿Cómo ocultarla?

Para ocultarla, es necesario removerla de la superview.

Ejemplo:
```
[errorView removeFromSuperview];
```

## Estilos

Los estilos de los componentes textuales están definidos y no deben modificarse. Varían según el tamaño de la pantalla.

## Ejemplo

iPhone 4 | iPhone 5 | iPhone 6
---|---|---
![iPhone 4](https://cloud.githubusercontent.com/assets/16885901/23476225/d678eba4-fe98-11e6-9386-f232daf549b1.png) | ![iPhone 5](https://cloud.githubusercontent.com/assets/16885901/23229620/b304bd98-f91f-11e6-9c7e-54e30f3c0220.png) | ![iPhone 6](https://cloud.githubusercontent.com/assets/16885901/23229621/b3050370-f91f-11e6-9b83-3d923b4c6532.png)
