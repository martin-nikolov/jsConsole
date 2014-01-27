# JavaScript Console

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/console.png)

[**See Demo**](https://rawgithub.com/flextry/jsConsole/master/JavaScript%20Console/index.html)  
[**Read about jsConsole in my personal blog**](http://flextry.wordpress.com/2014/01/26/jsconsole/)  

[**Get jsConsole [HTML + CSS + JS]**](https://github.com/flextry/jsConsole/raw/master/download/JavaScript%20Console.zip) - last modification on 25 Jan, 2014 [version 0.2]  
[**Get latest version of the library (console.js)**](https://github.com/flextry/jsConsole/raw/master/download/Library%20v0.2.zip) - 25 Jan, 2014 [version 0.2]  
[**Get jsConsole Solution prepared for 10 tasks**](https://github.com/flextry/jsConsole/raw/master/download/JavaScript%20Console%20-%20Solution.zip) - 25 Jan, 2014 [version 0.2]

In connection with **JavaScript** course in [**Telerik Academy**](http://academy.telerik.com/) I decided to implement a simple **JavaScript Console** (similar appearance to `cmd` in Win8), that the aim is writing **JavaScript** without need for modify existing **HTML** and **CSS**. Structural logic (**HTML**), presentational logic (**CSS**) and business logic (**JavaScript**) are completely separated, providing more compactness.

I provide a library (**console.js**) with pre-implemented **JavaScript** functions that take care of the modification of **HTML** code, simulation of IO operations, some mathematical operations, methods for easier parsing arrays, etc.

I have made an association with the **C#** language - functions are with **C#** similar names in PascalCase for division from **JavaScript** functions and entry point - Main method.

### Table of Contents
- **[Requirements for working with the console](#requirements-for-working-with-the-console)**  
- **[Pre-implemented functions](#pre-implemented-functions)**  
- **[Using most important functions](#using-most-important-functions)**  
    - [SetFontSize](#setfontsizepixels)
    - [SetConsoleSize](#setconsolesizeheight-width)
    - [ConsoleClear](#consoleclear)
    - [ReadLine](#readlinetextmessage-defaultvalue-idname)
    - [Write and WriteLine](#writemessage-and-writelinemessage)
    - [Format](#formatstr)
    - [GetRandomInt](#getrandomintmin-max)
    - [GetRandomFloat](#getrandomfloatmin-max-precision)
    - [AccumulatePixels](#accumulatepixelspx1-px2)
    - [SplitBySeparator](#splitbyseparatorstring-separators)
    - [ParseIntCollection](#parseintcollectionstring-separators)
    - [ParseFloatCollection](#parsefloatcollectionstring-separators)
    - [ParseElementsToInt](#parseelementstointcollection)
    - [ParseElementsToFloat](#parseelementstofloatcollection)
    - [SetSolveButton](#setsolvebuttonevents-textmessage)

## Requirements for working with the console

Everything you need is:

`HTML-document` structuring console, the contents are "pouring" in the **div-element** with id = "content" (surrounded in yellow).

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/html.png)

`CSS-document` with pre-defined styles.

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/css-file.png)

`Library (console.js)` with pre-implemented **JavaScript** functions for easier work with console.
- removing the library does not affect on **HTML** and **CSS** logic, but in this case you should have to take care of automatically loading of methods, to simulate IO operations, etc..

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/js-library.png)

Script executing the logic of your program (eg script.js).

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/demo.png)

How it looks:

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/demo-result.png)

## Pre-implemented functions

 ```js
/* jsConsole Library © Martin Nikolov - Version [0.2] */
 
//
// Library Methods ('public methods' you can use)
//
function SetFontSize(pixels) { ... }
 
function SetConsoleSize(height, width) { ... }
 
//
// Console Clear Methods
//
function ConsoleClear() { ... }
 
function ClearElementChildren(htmlElement) { ... }
 
//
// Console Reading Methods
//
function ReadLine(textMessage, defaultValue, idName) { ... }
 
function ReadLineFromElement(fromElement, textMessage, defaultValue, idName) { }
 
//
// Console Writing Methods
//
function Write(message) { ... }
 
function WriteLine(message) { ... }
 
function WriteToElement(message, toElement) { ... }
 
function WriteLineToElement(message, toElement) { ... }
 
function Format(str) { ... }
 
//
// Math
//
function GetRandomInt(min, max) { ... }
 
function GetRandomFloat(min, max, toFixed) { ... }

function AccumulatePixels(px1, px2) { ... }
 
//
// Collection elements Parser
//
function SplitBySeparator(string, separators) { ... }
 
function ParseIntCollection(string, separators) { ... }
 
function ParseFloatCollection(string, separators) { ... }
 
function ParseElementsToInt(collection) { ... }
 
function ParseElementsToFloat(collection) { ... }
 
//
// Set Solve Problems Button Methods
//
function SetSolveButton(events, textMessage) { ... }
 
function SetSolveButtonToElement(toElement, events, textMessage) { ... }
 ```  

## Using most important functions

### SetFontSize(pixels)

```js
taskName = "SetFontSize";
 
function Main(bufferElement) {
 
    SetFontSize(35);
    WriteLine("Large text!")
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/font-size-demo.png)

### SetConsoleSize(height, width)

```js
taskName = "SetConsoleSize";
 
function Main(bufferElement) {
 
    SetConsoleSize(50, 400);
    WriteLine("Text!")
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/console-size-demo.png)

### ConsoleClear()

```js
taskName = "ConsoleClear";
 
function Main(bufferElement) {
 
    for (var i = 0; i < 10; i++) {
        WriteLine("SPAM! SPAM!");
        WriteLine("SPAM! SPAM!");
    }
 
    ConsoleClear();
 
    WriteLine("Off-topic");
    WriteLine("Off-topic");
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/console-clear-demo.png)

### ReadLine(textMessage, defaultValue, idName)

```js
taskName = "ReadLine";
 
function Main(bufferElement) {
 
    var msg1 = ReadLine("Enter message: ");
 
    // With default value
    var msg2 = ReadLine("Enter message: ", "Input with text");
 
    // With default value and set id to the input:text
    var msg2 = ReadLine("Enter message: ",
                        "Input with text and Id", "special-message");
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/readline-demo.png)

### Write(message) and WriteLine(message)

```js
taskName = "Write and WriteLine";
 
function Main(bufferElement) {
 
    WriteLine('JUST');
    WriteLine('EXAMPLE');
 
    WriteLine();
 
    Write("ONE ");
    Write("LINE");
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/write-methods-demo.png)

### Format(str)

```js
taskName = "Format";
 
function Main(bufferElement) {
 
    var firstName = "John";
    var secondName = "Snow";
 
    WriteLine(Format("Hello, {0} {1}!", firstName, secondName));
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/format-demo.png)

### GetRandomInt(min, max)

```js
taskName = "GetRandomInt";
 
function Main(bufferElement) {
 
    for (var i = 0; i < 5; i++) {
        WriteLine(GetRandomInt(-10, 10));
    };
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/getrandomint-demo.png)

### GetRandomFloat(min, max, precision)

```js
taskName = "GetRandomFloat";
 
function Main(bufferElement) {
 
    for (var i = 0; i < 2; i++) {
        WriteLine(GetRandomFloat(-10, 10));
    };
 
    WriteLine();
 
    for (var i = 0; i < 2; i++) {
        WriteLine(GetRandomFloat(-10, 10, 7));
    };
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/getrandomfloat-demo.png)

### AccumulatePixels(px1, px2)

```js
taskName = "AccumulatePixels";
 
function Main(bufferElement) {
 
    var a = AccumulatePixels('20px', 30); // 20 + 30 = 50px
    var b = AccumulatePixels('20px', '30px'); // 20 + 30 = 50px
    var c = AccumulatePixels(20, 30); // 20 + 30 = 50px
 
    WriteLine('20px + 30 = ' + a);
    WriteLine('20px + 30px = ' + b);
    WriteLine('20 + 30 = ' + c);
    WriteLine();
 
    var d = AccumulatePixels('-20px', 30); // -20 + 30 = 10px
    var e = AccumulatePixels('20px', -30); // 20 + (-30) = -10px
    var f = AccumulatePixels(-20, -30); // -20 + (-30) = -50px
 
    WriteLine('-20px + 30 = ' + d);
    WriteLine('20px + (-30) = ' + e);
    WriteLine('-20 + (-30) = ' + f);
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/accumulate-pixels-demo.png)


### SplitBySeparator(string, separators)

```js
taskName = "SplitBySeparator";
 
function Main(bufferElement) {
 
    var text = "{ 1, 2, 3, 4, 5 }";
 
    var separators = [',', ' ', '{', '}'];
    var numbers = SplitBySeparator(text, separators); // Array of strings
 
    for (var i = 0; i < numbers.length; i++) {
        WriteLine(numbers[i]);
    };
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/splitbyseparator-demo.png)

### ParseIntCollection(string, separators)

```js
taskName = "ParseIntCollection";
 
function Main(bufferElement) {
 
    var text = "{ 1, 2, 3, 4, 5 }";
 
    var separators = [',', ' ', '{', '}'];
    var numbers = ParseIntCollection(text, separators); // Array of integers
 
    for (var i = 0; i < numbers.length; i++) {
        WriteLine(numbers[i] + 1);
    };
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/parseintcollection-demo.png)

### ParseFloatCollection(string, separators)

```js
taskName = "ParseFloatCollection";
 
function Main(bufferElement) {
 
    var text = "{ 1, 2, 3, 4, 5 }";
 
    var separators = [',', ' ', '{', '}'];
    var numbers = ParseFloatCollection(text, separators); // Array of floats
 
    for (var i = 0; i < numbers.length; i++) {
        WriteLine(numbers[i] + 0.1);
    };
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/parsefloatcollection-demo.png)

### ParseElementsToInt(collection)

```js
taskName = "ParseElementsToInt";
 
function Main(bufferElement) {
 
    var numbers = ['1', '2', '3', '4', '5'];
    numbers = ParseElementsToInt(numbers); // Array of integers
 
    for (var i = 0; i < numbers.length; i++) {
        WriteLine(numbers[i] + 1);
    };
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/parseelementstoint-demo.png)

### ParseElementsToFloat(collection)

```js
taskName = "ParseElementsToFloat";
 
function Main(bufferElement) {
 
    var numbers = ['1.1', '2.2', '3.3', '4.4', '5.5'];
    numbers = ParseElementsToFloat(numbers); // Array of floats
 
    for (var i = 0; i < numbers.length; i++) {
        WriteLine((numbers[i] + 0.1).toFixed(1));
    };
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/parseelementstofloat-demo.png)

### SetSolveButton(events, textMessage)
- If we have functions that have to be performed after data input, we use `SetSolveButton`.  In the the parameter **events** lists the functions to be performed after pressing the button.
- **Notes**: To access the data entered by the user (or pass it to function) is necessary to access the property **value** of the object stores data entered by the user. In the examples below to get the value of the variable _**firstName**_ must access the property **value** - **firstName.value** returns an object of type _**String**_.

```js
taskName = "SetSolveButton";
 
function Main(bufferElement) {
 
    var firstName = ReadLine("First name: ");
    var secondName = ReadLine("Second name: ");
 
     SetSolveButton(function () {
        Regard(firstName.value, secondName.value);
        // Function 2
        // Function 3
    });
}
 
function Regard(firstName, secondName) {
    WriteLine(Format("Hello, {0} {1}!", firstName, secondName));
}
```

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/solvebutton-demo.png)
