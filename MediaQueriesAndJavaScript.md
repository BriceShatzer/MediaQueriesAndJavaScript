#Getting all media queries present in a stylesheet 


*Note: Access to the cssRules attribute is subject to the cross-origin policy*  
*Some thoughts on getting around that issue [here](http://stackoverflow.com/questions/3211536/accessing-cross-domain-style-sheet-with-cssrules)* 

```javascript
var mediaQueriesMap = new Map();

var rules;


//--isolate the style sheet you want to work with. 

//set it directly by picking it from the styleSheets array. Here we're using the sheet at index 3.
rules = document.styleSheets[3].cssRules;

//set it by referencing it's url
function getStyleSheetByUrl(url){
    for (var i = document.styleSheets.length - 1; i >= 0; i--) {
        if( document.styleSheets[i].href == url){
            rules = document.styleSheets[i].cssRules;
        }
    }
}
getStyleSheetByUrl('http://www.webste.com/style.css');


//--create the map 
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

//--print results to a console table 
var reportingTable = []
for (var entry of mediaQueriesMap){
    reportingTable.push( {
        mediaQuery:entry[0], 
        occurrencesInStylesheet:entry[1].occurrences,
        countOfStyleRules:entry[1].styleRules.length
    });
}

console.table(reportingTable);


//optional - print results to a csv formated string that can be saved via a text editor
/*
var csv = '--Media Query--,--times it appears--,--style rules within this media rule--\n';
for (var entry of mediaQueriesMap){ 
    csv+=entry[0]+', '+entry[1].occurrences+', '+entry[1].styleRules.length+'\n'
}
console.log(csv);
*/



```