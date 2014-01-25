# JavaScript Console

![screenshot of console](https://raw.github.com/flextry/jsConsole/master/src/common/images/console.png)

[**See Demo**](https://rawgithub.com/flextry/jsConsole/master/JavaScript%20Console/index.html)  
[**Read about jsConsole in my personal blog**](http://flextry.wordpress.com/2014/01/26/jsconsole/  )  
[**Get jsConsole [HTML + CSS + JS]**](https://github.com/flextry/jsConsole/raw/master/download/JavaScript%20Console.zip) - last modification on 25 Jan, 2014 [version 0.1]  
[**Get latest version of the library (console.js)**](https://github.com/flextry/jsConsole/raw/master/download/Library%20v0.2.zip) - 25 Jan, 2014 [version 0.1]  
[**Get jsConsole Solution Packet prepared for 10 tasks**](https://github.com/flextry/jsConsole/raw/master/download/JavaScript%20Console%20-%20Solution.zip) - 25 Jan, 2014 [version 0.1]

Във връзка с курса по JavaScript в Telerik Academy, реших да направя една проста JavaScript конзола (на външен вид подобна на Win8), като целта е писане на JavaScript без да е нужно модифициране на съществуващия HTML и CSS. Структурната логика (HTML), презентационната логика (CSS) и бизнес логиката (JavaScript) са напълно отделени, което предоставя по-голяма компактност.

Предоставил съм и библиотека (console.js) с дефинирани JS-функции, които се грижат за модификацията на HTML-a, симулиране на входно-изходни операции, някои математически операции, методи за лесно “парсване” на масиви и др.

Направил съм асоциация със C# езика – функциите са със C# подобни имена и с главни букви за разделение от JS-функциите, и начална точка (entry point) – Main метод. Програмиста не е нужно да знае как работят функциите имплементирани в библиотеката (console.js), а единствено как да ги използва.

## Предварително имплементирани функции

 ```js
/* jsConsole Library © Martin Nikolov - Version [0.2] */
 
//
// Library Methods ('public methods' you can use)
//
function SetFontSize(pixels) { ... }
 
function SetConsoleSize(height, width) { ... }
 
function AccumulatePixels(px1, px2) { ... }
 
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
