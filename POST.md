##Auditing media queries using javascript


**TL;DR:**: You can use JavaScript to get an better understanding of the media queries that are present in your project. Don't care about the rational behind doing something like this and are just looking for a snippet? [go here]()

<!-- Inheriting an existing web project is always one of the more interesting and (potentially infuriating) things that can happen to you as a developer. 

Even if the codebase has been well documented and written in a clear and concise manor
In the "excitement" of diving into the structure and functionality of the codebase, styling is often overlooked.
 -->


<!-- While the overall [thoughtfulness around how frontends are built](http://shop.oreilly.com/product/0636920040156.do) in general has improved in recent years,  -->

While the overall [thoughtfulness around how frontends are built](http://shop.oreilly.com/product/0636920040156.do) has improved in recent years,
generally speaking, styling simply isn't treated with the same amount of care and consideration as other parts of the frontend stack. Marry this apathy with tools like Sass/LESS/Stylus which enable developers to easily write complex and powerful CSS, and it's easy to envision the sort of tangled, nightmarish abomination that might exist in this world. 

<!-- The likelihood of confronting this sort of monstrosity is never more likely then when a developer inherits an existing web project. <!-- <<< maybe unneeded --> 

<!-- In my experience, this usually takes the form of a framework like bootstrap or foundation that has so many layers of paint and ad hoc fixes applied that [Theseus](https://en.wikipedia.org/wiki/Ship_of_Theseus) would be proud.  
In my experience, this usually takes the form of a framework like bootstrap or foundation that has so many layers of paint and ad hoc fixes applied that [Theseus]() would be proud. -->
In my experience, this usually takes the form of a framework like bootstrap or foundation that has had so many layers of paint and ad hoc fixes applied to it that [Theseus](https://en.wikipedia.org/wiki/Ship_of_Theseus) would be proud. 


The likelihood of confronting this sort of monstrosity is never higher then when a developer inherits an existing web project. <!-- <<< maybe unneeded --> 
On the surface, poorly written styling might not seem like a big issue. 

Unfortunately, when the time comes to make updates to the project, the flaws and idiosyncrasies that exist in the CSS can
quickly become a massive time sink as ad hoc fixes for one problem [cascades](https://youtu.be/ja0jS_toKxk) into other issues. The ideal course of action would be to go through and completely refactor the styling, 
but due to time constraints and the perceived magnitude of the task, it's something that is rarely is attempted. If only there was a way to easily see where potential issues might exist in order to provide a starting place for the process...


In auditing the our media queries, we can 

An audit of the a sites media queries can:<!--  provide insight into:  -->

- highlight places where mixed length unit values might have been used
- spot inconsistent or mistyped values
- find potential style overlaps and places to check for unintentional "double styling"
- point to weird-edge cases & one-offs that could potentially be investigated.

...and this discovery and documentation process can be automated using JavaScript. 

And we can a


We can automate the discovery and documentation process using javascript. 

Media queries 





If only there was some way to see where potential issues might exist, and start 

and/or 


high impact low effort


some low hanging fruit to get started with...

Media Queries are 
Auditing Media your 


We can automate the discovery and documentation process using javascript. 



- bring code into a unified and consistent state
- preventing the mixing of [absolute](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Absolute_length_units) & [font-relative](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Font-relative_lengths) length units.
- easily spot inconsistent or mistyped values
- help to spot overlaps and places to check for unintentional "double styling"
- highlight weird-edge cases & one-offs that could potentially be investigated.



CSS [unit](https://github.com/jamesshore/quixote/blob/master/README.md) and [regression](https://github.com/Huddle/PhantomCSS) testing would go a long way in preventing (or at least helping untangle) these sorts of issues, they are far from the standard industry practice. 

<!--
CSS unit and regression testing might have helped in preventing the issue, but isn't really much use in cleaning up the mess.  
refactoring becomes the best course of action. 
don't don't really do much to help with refactoring. 
-->







This sort of situation, while gross-looking, may seem benign.
Issues begin to arises when 

After all, if it ain't broke...
Issue begin to arises 

While on the appearing somewhat 
These sort
...this is an issue because...



<!-- While CSS [unit](https://github.com/jamesshore/quixote/blob/master/README.md) and [regression](https://github.com/Huddle/PhantomCSS) testing do exist, they are far from the standard industry practice.  -->

CSS [unit](https://github.com/jamesshore/quixote/blob/master/README.md) and [regression](https://github.com/Huddle/PhantomCSS) testing would go a long way in preventing (or at least helping untangle) the issue, they are far from the standard industry practice. This means we are basically left with two options when dealing with styling:  

- Manually going through all of the includes, noting any media queries that are uncovered,  
- or wait until you see unexpected behavior and debug issues on an ad-hoc basis

One is incredibly time consuming & tedious. The other is completely reactive & subject to a large degree of chance.

99% of the time, developers opt for the second option. (if it ain't broke...)


We can automate the discovery and documentation process using javascript. 



<!-- 
Usually this takes the form of a framework like bootstrap or foundation that has so many layers of paint and ad hoc fixes have been applied that [Theseus](https://en.wikipedia.org/wiki/Ship_of_Theseus) would be proud. 
Perhaps in the beginning a framework like bootstrap or foundation was used, but so many layers of paint and ad hoc fixes have been applied that [Theseus](https://en.wikipedia.org/wiki/Ship_of_Theseus) would be proud. 
 -->
<!-- 
have been applied to the point that 
but layers upon layers of paint and ad hoc fixes have been applied to the point that 
[Ship of Theseus](https://en.wikipedia.org/wiki/Ship_of_Theseus) -->
<!-- Inheriting an existing web project is always one of the more interesting and (potentially infuriating) things that can happen to you as a developer.  -->
<!-- 
This scenario is always one of the more interesting and (potentially infuriating) things that can happen to you as a developer. 
Include a framework like bootstrap or foundation and then pile on top of that 
 -->
<!-- 
of a style sheet scenario where the styleSheets
This sort of predicament 
This sort of fear actualize
apparent then 
is never more apparent then when a developer inherits an existing web project. 
 -->
<!-- This scenario is always one of the more interesting and (potentially infuriating) things that can happen to you as a developer.  -->
<!-- Inheriting an existing web project is always one of the more interesting and (potentially infuriating) things that can happen to you as a developer.  -->
<!-- styling often isn't treated with the same care and consideration that the other parts of the frontend stack. -->
<!-- are built has improved in recent years,  -->

<!-- Tools like Sass/LESS/Stylus have enabled developers to easily write complex and powerful CSS  -->

<!-- and while the overall thoughtfulness around how frontends in general has improved in recent years, --><!-- are built has improved in recent years,  -->

<!-- styling often isn't treated with the same care and consideration that the other parts of the frontend stack.

Marry this apathy with tools like Sass/LESS/Stylus which enable developers to easily write complex and powerful CSS, 
and it's easy to envision  -->
<!-- things spiraling out of control relatively quickly.  -->
<!-- 
the structure and implementation of styling 
is still an area where 
 -->
<!-- 
Inheriting an existing web project is always one of the more interesting things that can happen to you as a developer. 
In the "excitement" of diving into the structure and functionality of the codebase, styling is often overlooked.
 -->


<!-- The [thoughtfulness around how frontends are built](http://shop.oreilly.com/product/0636920040156.do) has started to get better,  -->


<!-- In the "excitement" of diving into the structure and functionality of the codebase, styling is often overlooked.
Even if the codebase has been well documented and written in a clear and concise manor, it's unlikely that much time or effort has been placed in the styling. 

The [thoughtfulness around how frontends are built](http://shop.oreilly.com/product/0636920040156.do) has started to get better, 

the likelihood that the styling has received the same care.  
-->

<!-- Inheriting an existing web project is always one of the more interesting and (potentially infuriating) things that can happen to you as a developer.  -->

<!-- figuring out how the different pieces fit together and what assumptions where made -->






Unfortunately, 
this can lead to substantial 
when the time comes to make updates to the project, 

the flaws and idiosyncrasies that 

it comes to 
but can result in trying  to figure out why something 


![JAVASCRIPT ALL THE THINGS!](http://www.tricedesigns.com/wp-content/uploads/2015/09/jsatt.jpg)
<!-- This isn't a bad idea to
Just want the code? [Here it is](). -->

<!-- could potentially effect your project. 
of your media  document your  -->

<!-- While CSS unit testing [does exist](https://github.com/jamesshore/quixote/blob/master/README.md), it's far -->


This means that, 


Unit testing CSS isn't
Wading into a

Unit testing CSS isn't really a thing.

<!-- Don't care about the reasoning for doing something like this or what sort of insights could possibly be gained, --> 
If you don't care about the rational behind doing something like this and are just looking for a snippet, go here 




####problem/why

- bring code into a unified and consistent state
- preventing the mixing of [absolute](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Absolute_length_units) & [font-relative](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Font-relative_lengths) length units.
- easily spot inconsistent or mistyped values
- help to spot overlaps and places to check for unintentional "double styling"
- highlight weird-edge cases & one-offs that could potentially be investigated.



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


#### other solutions

While CSS [unit](https://github.com/jamesshore/quixote/blob/master/README.md) and [regression](https://github.com/Huddle/PhantomCSS) testing do exist, they are far from the standard industry practice. 

This means we are basically left with two options when dealing with styling:  

- Manually going through all of the includes, noting any media queries that are uncovered,  
- or wait until you see unexpected behavior and debug issues on an ad-hoc basis

One is incredibly time consuming & tedious. The other is completely reactive & subject to a large degree of chance.

99% of the time, developers opt for the second option. (if it ain't broke...)


We can automate the discovery and documentation process using javascript. 


<!-- 
There are a couple of ways to deal with....
The first is to manually go through all of module, partial, import, include, vendor, manifest, primary, etc. files, noting any media query that is uncovered.

Unfortunately, any semi-robust or componentized project that is using a preprocessor will probably have a large number of files which would make this process incredibly time consuming and tedious.

A robust and heavily componentized project that is using a preprocessor could have a large number of include files which would make option A incredibly time consuming and tedious. -->



####running the code

So what exactly will be happening?

- Pick a target [style sheet](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets) and get it's [cssRuleList](https://developer.mozilla.org/en-US/docs/Web/API/CSSRuleList)
_Note: Keep in mind that style sheets are subject to the [same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy). This means that if the style sheet's origin doesn't match that of the page (e.g. being loaded from a CDN), the [cssRules](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet#cssRules) property of the `CSSStyleSheet` object isn't available and returns `null`. Some thoughts on dealing with this issue can be found [here](http://stackoverflow.com/questions/3211536/accessing-cross-domain-style-sheet-with-cssrules)._
- loop through this collection of [CSSRules](https://developer.mozilla.org/en-US/docs/Web/API/CSSRule) looking for [CSSMediaRules](https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule)
- When one is found,
  - if it hasn't been seen before, map it to `mediaQueriesMap` variable we have setup,
  - increment the count value for this `CSSMediaRule` in the map,
  - add all `cssRules` found within this particular instance of the media query to the entry in the `mediaQueriesMap` variable,
- Finally we format `mediaQueriesMap` into a table and print it in the console.


####code
```javascript

console.log('There will be javascript here');

```


####analyzing the results


This a result from a site
I've used


At the top of table, we see -several media queries- that contain the majority of the rules for this particular style sheet.
They're all
...using
...looking for length type media features using the em


We already knew that this project was built using foundation, so seeing a majority of the rules inside media queries that are using em length units is to be expected.
These media queries are most likely using Foundations built in variables, or at the very least are using a consistent unit of measurement.

- easily spot inconsistent or mistyped values
(#17 vs #16,#19,21 )
- help to spot overlaps and unintentional "double styling"
and element that is being styled at 768
(#21(min-768) & #16,19(max-768))
- highlight one-offs, weird edge-cases,
- with k




and checking the documentation
They are all using em as their unit of measurement.


em that contain a large
large collections  chunk of style rules that were created inside media

all of media queries that were created using foundation variables




---

#### expanding the usage

_The `mediaQueriesMap` map that is created offers a fair bit of utility_
_offers a fair bit of utility_
_The `mediaQueriesMap` map that is created offers a fair bit of utility that can be expanded on and used_
_The `mediaQueriesMap` map that is created offers a fair bit of flexibility_
_...that can be utilized and expanded on._
_The `mediaQueriesMap` map that is created is fairly flexible and can be used to produce additional insights._


The `mediaQueriesMap` map that is created is fairly flexible. In addition to creating a general overview, it can be used to drill into specific media queries.
From the previous 
In the prior example we can see that the media query `screen and (max-width: 1000px)` is being used in the style sheet 13 different times to declare 13 different rules. Using our existing `mediaQueriesMap` variable we can see what [selectors](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleRule#selectorText) are being used for each of those rules.
```javascript
var rules_at_this_breakpoint = mediaQueriesMap.get("screen and (max-width: 1000px)").styleRules


Array.prototype.forEach.call(rules_at_this_breakpoint, function(rule){
    console.log(rule.selectorText);
});
```

The resulting output could be useful in tracking down where exactly within the a project's uncompiled Sass/LESS/Stylus files to start looking for an issue.









#### a note about working with styles sheets,

There are two methods specified

_Note: Keep in mind that style sheets are subject to the [same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy). This means that if the style sheet's origin doesn't match that of the page (e.g. being loaded from a CDN), the [cssRules](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet#cssRules) property of the `CSSStyleSheet` object isn't available and returns `null`. Some thoughts on dealing with this issue can be found [here](http://stackoverflow.com/questions/3211536/accessing-cross-domain-style-sheet-with-cssrules)._




