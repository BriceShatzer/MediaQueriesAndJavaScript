#Getting all media queries present in a stylesheet 


*Note: Access to the cssRules attribute is subject to the cross-origin policy*  
*Some thoughts on getting around that issue [here](http://stackoverflow.com/questions/3211536/accessing-cross-domain-style-sheet-with-cssrules)* 

```javascript
var mediaQueries = [];

//isolate the style sheet you want to work with. 
var rules = document.styleSheets[3].cssRules;

  //jQuery.each(rules,function(i,val){
  Array.prototype.forEach.call(rules, function(val,i){
    if(val instanceof CSSMediaRule){mediaQueries.push(val.media)}
})
```