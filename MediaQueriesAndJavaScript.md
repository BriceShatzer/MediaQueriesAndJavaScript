#Getting all media queries present in a stylesheet 


```
var mediaQueries = [];
//isolate the style sheet you want to work with. 
//Note: access to the cssRules attribute is subject to cross-origin  stylesheet 
var rules = document.styleSheets[3].cssRules;

  //jQuery.each(rules,function(i,val){
  Array.prototype.forEach.call(rules, function(val,i){
    if(val instanceof CSSMediaRule){mediaQueries.push(val.media)}
})
```