## Uso
Para poder utilizar los colores y fuentes de la lib debemos importar la clase `MLStyleSheetManager` y acceder a la property `styleSheet` la cual nos va a proveer de los colores y fuentes inyectadas o por default las que posee la lib.

### Colores
primary color
```objective-c
MLStyleSheetManager.styleSheet.primaryColor
```

light primary color
```objective-c
MLStyleSheetManager.styleSheet.lightPrimaryColor
```

secondary color
```objective-c
MLStyleSheetManager.styleSheet.secondaryColor
```

secondary color pressed
```objective-c
MLStyleSheetManager.styleSheet.secondaryColorPressed
```

secondary color disabled
```objective-c
MLStyleSheetManager.styleSheet.secondaryColorDisabled
```

success color
```objective-c
MLStyleSheetManager.styleSheet.successColor
```

error color
```objective-c
MLStyleSheetManager.styleSheet.errorColor
```

black color
```objective-c 
MLStyleSheetManager.styleSheet.blackColor
```

dark grey color
```objective-c
MLStyleSheetManager.styleSheet.darkGreyColor
```

grey color
```objective-c
MLStyleSheetManager.styleSheet.greyColor
```

mid grey color
```objective-c
MLStyleSheetManager.styleSheet.midGreyColor
```

light grey color
```objective-c
MLStyleSheetManager.styleSheet.lightGreyColor
```

white color
```objective-c
MLStyleSheetManager.styleSheet.whiteColor
```

modal background color
```objective-c
MLStyleSheetManager.styleSheet.modalBackgroundColor
```

modal tint color
```objective-c
MLStyleSheetManager.styleSheet.modalTintColor
```

### Fuentes
regular font
```objective-c
[MLStyleSheetManager.styleSheet regularSystemFontOfSize:kMLFontsSizeLarge];
```

bold font
```objective-c
[MLStyleSheetManager.styleSheet boldSystemFontOfSize:kMLFontsSizeLarge];
```

thin font
```objective-c
[MLStyleSheetManager.styleSheet thinSystemFontOfSize:kMLFontsSizeLarge];
```

light font
```objective-c
[MLStyleSheetManager.styleSheet lightSystemFontOfSize:kMLFontsSizeLarge];
```

medium font
```objective-c
[MLStyleSheetManager.styleSheet mediumSystemFontOfSize:kMLFontsSizeLarge];
```

semibold font
```objective-c
[MLStyleSheetManager.styleSheet semiboldSystemFontOfSize:kMLFontsSizeLarge];
```

extrabold font
```objective-c
[MLStyleSheetManager.styleSheet extraboldSystemFontOfSize:kMLFontsSizeLarge];
```

black font
```objective-c
[MLStyleSheetManager.styleSheet blackSystemFontOfSize:kMLFontsSizeLarge];
```