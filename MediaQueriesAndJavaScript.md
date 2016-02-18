#Getting all media queries present in a stylesheet 


*Note: Access to the cssRules attribute is subject to the cross-origin policy*  
*Some thoughts on getting around that issue [here](http://stackoverflow.com/questions/3211536/accessing-cross-domain-style-sheet-with-cssrules)* 

```javascript
var allMediaQueries, uniqueMediaQueries = [];

//isolate the style sheet you want to work with. 
var rules = document.styleSheets[3].cssRules;

  //jQuery.each(rules,function(i,val){
  Array.prototype.forEach.call(rules, function(val,i){
    if(val instanceof CSSMediaRule){allMediaQueries.push(val.media)}
})


var uniqueNames = [];
Array.prototype.forEach(allMediaQuries, function(rule,i){
  //if($.inArray(rule, uniqueMediaQueries) === -1){
  if(uniqueMediaQueries.indexOf(rule) === -1){
    uniqueMediaQueries.push(rule);
  }
});



```