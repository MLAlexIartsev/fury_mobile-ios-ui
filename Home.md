## Como utilizar la Lib

La lib de UI gestiona los colores y fuentes a través del `MLStyleSheetManager`, todos los componentes de la lib consultan a este manager para poder tomar el estilo de colores y tipografías correspondiente.
Esto nos permite utilizar la librería dándole el estilo adecuado dependiendo la app que la va a utilizar.

El `MLStyleSheetManager` se configura al inicio de la aplicación con una clase que herede de `MLStyleSheetDefault` o una clase que implemente el protocolo `MLStyleSheetProtocol` 

### Ej de inicialización:
```objective-c
MLStyleSheetManager.styleSheet = [MLStyleSheetDefault new];
```

### MLStyleSheetDefault
Esta clase implementa el protocolo `MLStyleSheetProtocol` y declara colores default y la fuente default del sistema (San Francisco), es utilizada por la lib de UI en la testApp y se puede heredar de esta clase para inicializar el `MLStyleSheetManager` si solo se quiere sobreescribir algunos colores o fuentes.

### MLStyleSheetProtocol
Este protocolo declara todos los colores y tipos de fuentes que se deberán implementar para que todos los componentes luego los utilicen

![testapp 1](https://cloud.githubusercontent.com/assets/17389431/16657989/f6e4324a-443a-11e6-91fa-283eb53ddca6.gif)