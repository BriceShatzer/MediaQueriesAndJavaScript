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
        if(!mediaQueriesMap.has(mediaQueryRule)){//adds rule to the map if missing
            mediaQueriesMap.set(mediaQueryRule, {styleRules:[], occurrences:0});
        }

        //log the rule's occurance
        mediaQueriesMap.get(mediaQueryRule).occurrences++;

        //add this media queries style rules to the map
        Array.prototype.forEach.call(rule.cssRules, function(styleRule,i){        
            mediaQueriesMap.get(mediaQueryRule).styleRules.push(styleRule);        
        });
    }
});

//print results
var reportingTable = []
for (var entry of mediaQueriesMap){
    reportingTable.push( {
        mediaQuery:entry[0], 
        occurrencesInStylesheet:entry[1].occurrences,
        countOfStyleRules:entry[1].styleRules.length
    });
}

console.table(reportingTable);

```