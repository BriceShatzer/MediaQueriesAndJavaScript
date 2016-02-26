##Auditing media queries using javascript 

This isn't a bad idea to 
Just want the code? [Here it is]().

While CSS unit testing [does exist](https://github.com/jamesshore/quixote/blob/master/README.md), it's far 

Unit testing CSS isn't 
Wading into a 

Unit testing CSS isn't really a thing. 
Don't care about the reasoning for doing something like this, or what sort of insight 


Just looking for the snippet
If you don't care about the rational behind doing something like this 




####problem/why



- bring code into a unified and consistent state
- - preventing the mixing of [absolute](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Absolute_length_units) & [font-relative](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Font-relative_lengths) length units.  
- -easily spot inconsistent or mistyped values  
- -help to spot overlaps and places to check for unintentional "double styling"  
- -highlight weird-edge cases & one-offs that could potentially be investigated. 



mixing  
absolute & font relative lengths are by far the most widely used length values that are used in media queries 
mixing them can have


- easily spot inconsistent or mistyped values 
(#17 vs #16,#19,21 )  
- help to spot overlaps and unintentional "double styling" 
and element that is being styled at 768
(#21(min-768) & #16,19(max-768))
- highlight one-offs, weird edge-cases,    
- with k


####other solutions
manually going through all of the includes, noting any media query that 
or wait until you see unexpected behavior and debug the issue then.  

One is incredibly time consuming & tedious. The other is completely reactive & subject to a large degree of chance.  
There are a couple of ways to deal with....  
The first is to manually go through all of module, partial, import, include, vendor, manifest, primary, etc. files, noting any media query that is uncovered.  
Unfortunately, any semi-robust or componentized project that is using a preprocessor will probably have a large number of files which would make this process incredibly time consuming and tedious. 

A robust and heavily componentized project that is using a preprocessor could have a large number of include files which would make option A incredibly time consuming and tedious.  


####code
--targeting a stylesheet 


####running the code

- Pick a target [stylesheet](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets) and get it's [cssRuleList](https://developer.mozilla.org/en-US/docs/Web/API/CSSRuleList)  
- loop through this collection of [CSSRules](https://developer.mozilla.org/en-US/docs/Web/API/CSSRule) looking for [CSSMediaRules](https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule)  
- When one is found,  
- - if it hasn't been seen before, map it to `mediaQueriesMap` variable
- -    

item in that collection,  
map the mediaQueryRules  

####analyzing the results 

At the top of table, we see several media queries that contain the majority of the rules for this particular stylesheet.  
They're all   
...using  
...looking for length type media features using the em   


We already knew that this project was built using foundation, so seeing  
...this  
...a majority of the rules inside media queries that are using em length units is to be expected.  
These media queries are most likely using Foundations built in variables, or at the very least are using a consistent unit of measurement.  




and checking the documentation 
They are all using em as their unit of measurement.   


em that contain a large  
large collections  chunk of style rules that were created inside media 

all of media queries that were created using foundation variables 