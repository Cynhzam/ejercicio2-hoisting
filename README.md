# ejercicio2-hosting
Requerimiento : El código muestra el mensaje JS coders love its callbacks, mientras que el resultado debería ser JS developers love its closures.

En el código inicial se puede observar que el resultado es: JS coders love its callbacks, 
esto sucede porque tenemos dos scope (uno global y otro local) que tienen el mismo nombre, 
cuando el código comienze a ejecutarse el hoisting hará que la variable local sea elevada al inicio, 
pero solo la declara mas no le da un valor (undefined), entonces cuando la ejecuta esta toma como 
verdadera la primera condición y nos retorna "JS coders love its callbacks", es decir que la función 
prioriza el valor de la variable local que de la global, razón por la cual el retorno tomo el valor "callbacks".
```javascript
var feature = 'closures'; 
(function () {     
	if ( typeof feature === 'undefined' ){         
		var feature = 'callbacks';         
		console.log('JS coders love its ' + feature );     
	} else {         
		console.log('JS developers love its ' + feature );     
	} 
})();
"JS coders love its callbacks"
```
Para la solución lo que se realizó, fue dejar a la variable global, por eso a la que era local se le quitó el var,
por eso al ejecutar tomar el valor de la global (closures), y al comparar no es 'undefined', es por eso que nos da el 
resultado "JS developers love its closures".
```javascript
var feature = 'closures'; 
(function () {     
    if ( typeof feature === 'undefined' ){
      feature = 'callbacks';
      console.log('JS coders love its ' + feature );     
    } else {         
      console.log('JS developers love its ' + feature );     
    } 
})();
```
"JS developers love its closures"
