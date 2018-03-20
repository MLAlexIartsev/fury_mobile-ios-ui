![contextualmenudemo](https://cloud.githubusercontent.com/assets/5233702/15442016/df0590c0-1eb4-11e6-9ec3-7b5a2ae19009.png)

Menú que se despliega al hacer long press mostrando distintos circulos para cada opción rodeando la posición en la que se hizo el long press.

## Uso

Primero instanciamos el MLContextualMenu y asignamos los datasources y delegates.
``` objective-c
	MLContextualMenu *contextualMenu = [[MLContextualMenu alloc] init];
	contextualMenu.dataSource = self;
	contextualMenu.delegate = self;
```

Luego tomamos el gesturerecognizer y lo asignamos a la vista que lo va a contener, de esa forma se mantiene en memoria con la misma vista.
``` objective-c
	UILongPressGestureRecognizer *gestureRecognizer = [contextualMenu gestureRecognizerWithDelegate:self];
	[self.collectionView addGestureRecognizer:gestureRecognizer];
```

Para no interferir con el scrolling agregamos la siguiente función.
``` objective-c
- (BOOL)gestureRecognizerShouldBegin:(UIGestureRecognizer *)gestureRecognizer
{
	BOOL isScrolling = self.collectionView.isDragging || self.collectionView.isDecelerating;
	return !([gestureRecognizer isKindOfClass:[UILongPressGestureRecognizer class]] && isScrolling);
}
```

#### Datasources

Devuelve un array con los items que se van a mostrar (de tipo MLContextualMenuItem).
``` objective-c
- (NSArray<MLContextualMenuItem *> *)contextualMenu:(MLContextualMenu *)contextualMenu itemsAtPoint:(CGPoint)point;
```

Devuelve si se debe mostrar o no el ContextualMenu.
``` objective-c
- (BOOL)contextualMenu:(MLContextualMenu *)contextualMenu shouldShowMenuAtPoint:(CGPoint)point;
```

#### Delegates

Acción a realizar cuando se selecciona un item del ContextualMenu.
``` objective-c
- (void)contextualMenu:(MLContextualMenu *)contextualMenu didSelectItemAtIndex:(NSInteger)selectedIndex atPoint:(CGPoint)point;
```