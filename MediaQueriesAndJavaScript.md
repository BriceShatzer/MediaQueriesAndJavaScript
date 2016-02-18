#Getting all media queries present in a stylesheet 


*Note: Access to the cssRules attribute is subject to the cross-origin policy*  
*Some thoughts on getting around that issue [here](http://stackoverflow.com/questions/3211536/accessing-cross-domain-style-sheet-with-cssrules)* 

```javascript
var mediaQueriesMap = new Map();

//isolate the style sheet you want to work with. 
var rules = document.styleSheets[3].cssRules;

//create the map 
Array.prototype.forEach.call(rules, function(rule,i){
    if(rule instanceof CSSMediaRule){
        var mediaQueryRule = rule.media.mediaText;
        if(mediaQueriesMap.has(mediaQueryRule)){//already has it
            //          
        } else{//adds it to the map
            mediaQueriesMap.set(mediaQueryRule,[]);
        }
        
        //add this media queries style rules to the map
        Array.prototype.forEach.call(rule.cssRules, function(styleRule,i){        
            mediaQueriesMap.get(mediaQueryRule).push(styleRule);        
        });
    }
});

//print results
var queryCountTable = []
function TableRow(text, count){
    this.mediaQuery = text;
    this.count = count;
}

for (var entry of mediaQueriesMap){
    queryCountTable.push( {mediaQuery:entry[0], count:entry[1].length} );
}

console.table(queryCountTable);

```