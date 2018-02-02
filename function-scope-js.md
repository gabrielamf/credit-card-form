# Identificación de funciones
 
**Track:** _Especialización Front-End_  
**Curso:** _JS Deep Dive: Crea tu propia librería usando JavaScript_  
**Unidad:** _Fundamentos de JS_
 
## Objetivo

Leer y analizar el código javascript e identificar los diferentes tipos de funciones, siendo éstas globales y locales, function expression y function statement, ámbitos de ejecuciones, funciones en la pila de ejecución y cola de eventos.
 
## Desarrollo

#### Funcion global

Global, que no está dentro de una función. Es global respecto al entorno de ejecución de document.
```javascript
$(document).ready(function() {
    // code
})
```
#### Funciones locales

Las siguientes funciones son locales, porque están definidas dentro de otra funcion, en este caso la función mencionada linea arriba.
```javascript
 function activeButton() {  
     ...
 };

 function desactiveButton() {
     ...
 };

 function longitud(input) {
     ...
 };
 function soloNumeros(input) {
     ...
 };
 function isValidCreditCar(numberCard){
     ...
 };
```
#### Variables globales

Las siguientes variables son globales para el entorno de ejecución de document.
```javascript
  var $inputCard;
  var $inputMonth;
  var $inputYear;
  var $buttonNext;
  var regexOnlyNumbers;
  var labelErrorOrSuccessMessages;
```
#### Variables locales
Las siguientes variables son locales porque están declaradas dentro de una función, por lo tanto sólo se puede acceder a ellas dentro de la función.
```javascript
 var regex;
 var creditCardNumber;
 var arr;
 var sumaTotal;
 var index;
```
#### Funcione Callback
Es aquella función que es enviada como parámetro de otra función.
```javascript
    soloNumeros(longitud(numberCard));
```
#### Funciones statement
Son aquellas que están disponibles en todo el ambiente lexical.
```javascript
    function activeButton() {
    ...
    } 

    function desactiveButton() {  
    ...
    } 

    function longitud(input) {
    ...
    }

    function soloNumeros(input) {
    ...
    }

    function isValidCreditCard(numberCard) {
    ...
    }
```
#### Clousure
Son aquellas funciones que recuerdan el entorno donde fueron creadas.
```javascript
    $inputCard.on('input', function() {
        isValidCreditCard($(this).val().trim()); // this - hace referencia a una variable que no fue creada dentro esta función pero sí de una función padre, por eso la recuerda.
    });

    activeButton();
    desactiveButton(); // están siendo llamadas dentro de otra función, sus variables fueron declaradas fuera pero si las recuerda por el clousure.
```
#### Funciones en la pila de ejecución
```javascript
function activeButton() {}
function desactiveButton() {}
function longitud(input) {}
function soloNumeros(input) {}
function isValidCreditCar(numberCard){}
```
#### Funciones en la cola de eventos
Ésta sólo se ejecutará cuando la pila de ejecución esté vacía.
```javascript
$inputCard.on('input', function() { isValidCreditCard($(this).val().trim()); });
```