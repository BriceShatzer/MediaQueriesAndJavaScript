#Getting all media queries present in a stylesheet 


*Note: Access to the cssRules attribute is subject to the cross-origin policy*  
*Some thoughts on getting around that issue [here](http://stackoverflow.com/questions/3211536/accessing-cross-domain-style-sheet-with-cssrules)* 

```javascript
var allMediaQueries = [];
var uniqueMediaQueries = [];

//isolate the style sheet you want to work with. 
var rules = document.styleSheets[3].cssRules;

Array.prototype.forEach.call(rules, function(val,i){
    if(val instanceof CSSMediaRule){
        allMediaQueries.push(val.media.mediaText);
    }
})

//removed duplicates 
Array.prototype.forEach.call(allMediaQueries, function(rule,i){  
  if(uniqueMediaQueries.indexOf(rule) === -1){
    uniqueMediaQueries.push(rule);
  }
});

//print the results 
console.log('Total Media Queries: '+allMediaQueries.length+'\nto view them use console.dir(allMediaQueries)');
console.log('Total Unique Media Queries: '+uniqueMediaQueries.length+'\nto view them use console.dir(uniqueMediaQueries)');

```