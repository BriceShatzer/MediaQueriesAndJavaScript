##Auditing media queries using JavaScript


**TL;DR:** You can use JavaScript to easily audit the media queries that are present in your project. This could potentially [provide insight]() into portions of your styling that might need to be examined more closely. Don't care about the rational behind doing something like this and are just looking for a snippet? [Head here.]()

<!--
**TL;DR:** You can use JavaScript to get an better understanding of the media queries that are present in your project. 
Don't care about the rational behind doing something like this and are just looking for a snippet? [Head here.]()
-->

<!-- Inheriting an existing web project is always one of the more interesting and (potentially infuriating) things that can happen to you as a developer. 

Even if the codebase has been well documented and written in a clear and concise manor
In the "excitement" of diving into the structure and functionality of the codebase, styling is often overlooked.
 -->


<!-- While the overall [thoughtfulness around how frontends are built](http://shop.oreilly.com/product/0636920040156.do) in general has improved in recent years,  -->

While the overall [thoughtfulness around how frontends are built](http://shop.oreilly.com/product/0636920040156.do) has improved in recent years,
generally speaking, styling simply isn't treated with the same amount of care and consideration as other parts of the front-end stack. Marry this apathy with tools like Sass/LESS/Stylus which enable developers to easily write complex and powerful CSS, and it's easy to envision the sort of tangled, nightmarish abomination that might exist in this world. 

<!-- The likelihood of confronting this sort of monstrosity is never more likely then when a developer inherits an existing web project. <!-- <<< maybe unneeded --> 

<!-- In my experience, this usually takes the form of a framework like bootstrap or foundation that has so many layers of paint and ad hoc fixes applied that [Theseus](https://en.wikipedia.org/wiki/Ship_of_Theseus) would be proud.  
In my experience, this usually takes the form of a framework like bootstrap or foundation that has so many layers of paint and ad hoc fixes applied that [Theseus]() would be proud. -->
In my experience, this usually takes the form of a framework like bootstrap or foundation that has had so many layers of paint and ad hoc fixes applied to it that [Theseus](https://en.wikipedia.org/wiki/Ship_of_Theseus) would be proud. 


The likelihood of confronting this sort of monstrosity is never higher then when a developer inherits an existing web project. 
<!-- ^^^ maybe unneeded --> 
On the surface, poorly written styling might not seem like a big issue. 

Unfortunately, when the time comes to make updates to the project, the flaws and idiosyncrasies that exist in the CSS can
quickly become a massive time sink as ad hoc fixes for one problem [cascades](https://youtu.be/ja0jS_toKxk) into other issues. The ideal course of action would be to go through and completely refactor the styling, 
but due to time constraints and the perceived magnitude of the task, it's something that is rarely is attempted. If only there was a way to easily see where potential issues might exist in order to provide a starting place for the process...


In auditing the our media queries, we can 

An audit of the a sites media queries can:

- highlight places where mixed length unit values might have been used
- spot inconsistent or mistyped values
- find potential style overlaps and places to check for unintentional "double styling"
- point to weird-edge cases & one-offs that could potentially be investigated.

...and best of all this discovery and documentation process can be automated using JavaScript. 




####What are we doing

So what exactly will be happening?

- Pick a target [style sheet](https://developer.mozilla.org/en-US/docs/Web/API/Document/styleSheets) and get it's [cssRuleList](https://developer.mozilla.org/en-US/docs/Web/API/CSSRuleList)  
_Note: Keep in mind that style sheets are subject to the [same-origin policy](https://developer.mozilla.org/en-US/docs/Web/Security/Same-origin_policy). This means that if the style sheet's origin doesn't match that of the page (e.g. being loaded from a CDN), the [cssRules](https://developer.mozilla.org/en-US/docs/Web/API/CSSStyleSheet#cssRules) property of the `CSSStyleSheet` object isn't available and returns `null`. Some thoughts on dealing with this issue can be found [here](http://stackoverflow.com/questions/3211536/accessing-cross-domain-style-sheet-with-cssrules)._
- loop through this collection of [CSSRules](https://developer.mozilla.org/en-US/docs/Web/API/CSSRule) looking for [CSSMediaRules](https://developer.mozilla.org/en-US/docs/Web/API/CSSMediaRule)
- When one is found,
  - if it hasn't been seen before, map it to `mediaQueriesMap` variable we have setup,
  - increment the count value for this `CSSMediaRule` in the map,
  - add all `cssRules` found within this particular instance of the media query to the entry in the `mediaQueriesMap` variable,
- Finally we format `mediaQueriesMap` into a table and print it in the console.


#### code
```javascript

console.log('There will be javascript here');

```










---
---
---


<!-- 
some low hanging fruit to get started with...
Media Queries are 
Auditing Media your 
We can automate the discovery and documentation process using javascript. 
 -->

- bring code into a unified and consistent state
- preventing the mixing of [absolute](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Absolute_length_units) & [font-relative](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Font-relative_lengths) length units.
- easily spot inconsistent or mistyped values
- help to spot overlaps and places to check for unintentional "double styling"
- highlight weird-edge cases & one-offs that could potentially be investigated.


<!--
CSS [unit](https://github.com/jamesshore/quixote/blob/master/README.md) and [regression](https://github.com/Huddle/PhantomCSS) testing would go a long way in preventing (or at least helping untangle) these sorts of issues, they are far from the standard industry practice. 

CSS unit and regression testing might have helped in preventing the issue, but isn't really much use in cleaning up the mess.  
refactoring becomes the best course of action. 
don't don't really do much to help with refactoring. 
-->

<!-- 





This sort of situation, while gross-looking, may seem benign.
Issues begin to arises when 

After all, if it ain't broke...
Issue begin to arises 

While on the appearing somewhat 
These sort
...this is an issue because...
-->


<!-- While CSS [unit](https://github.com/jamesshore/quixote/blob/master/README.md) and [regression](https://github.com/Huddle/PhantomCSS) testing do exist, they are far from the standard industry practice.  -->

<!--

CSS [unit](https://github.com/jamesshore/quixote/blob/master/README.md) and [regression](https://github.com/Huddle/PhantomCSS) testing would go a long way in preventing (or at least helping untangle) the issue, they are far from the standard industry practice. This means we are basically left with two options when dealing with styling:  

- Manually going through all of the includes, noting any media queries that are uncovered,  
- or wait until you see unexpected behavior and debug issues on an ad-hoc basis

One is incredibly time consuming & tedious. The other is completely reactive & subject to a large degree of chance.

99% of the time, developers opt for the second option. (if it ain't broke...)


We can automate the discovery and documentation process using javascript. 
--> 


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

<!-- 
![JAVASCRIPT ALL THE THINGS!](http://www.tricedesigns.com/wp-content/uploads/2015/09/jsatt.jpg)
-->
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

---
---
---
####analyzing the results

So what are we looking for? 
<!-- 
Below is an example from a site that I've worked on recently. This was a project that I inherited. 
Below is an example from a project that I recently inherited. 
 -->
In the example below, I've run the audit script on a project that I recently inherited.  

At the top of table, we see several media queries that contain the majority of the rules for this particular style sheet.

We already knew that this project was built using [Foundation 5](http://foundation.zurb.com/sites/docs/v/5.5.3/), so seeing a majority of the [media features](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries#Media_features) statements 



At the top of table we see several media queries that contain the majority of the rules for this project. We know that this project was built using Foundation 5, so seeing their media feature definitions using the [em length units](https://developer.mozilla.org/en-US/docs/Web/CSS/length#em) is to be expected. These media queries are most likely using [Foundation's built in variables](http://foundation.zurb.com/sites/docs/v/5.5.3/media-queries.html) or at the very least are defined using a value that is consistent with those variables.

Around #14 (`"screen and (max-width: 1010px)`) we see the media queries begin to be defined using the [absolute](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Absolute_length_units) length unit of `px`.  
While the arguments can be made for using either length unit (`px` or `em`) in media query definitions, the bigger issue in this particular instance is of consistency. With the vast majority of the styling rules being housed in `em` based media queries, these `px` based definitions [stand out](https://youtu.be/ueZ6tvqhk8U?t=20s), and should be examined more closely for [code smell](http://csswizardry.com/2012/11/code-smells-in-css/), adherence/disregard for best practices, and broken code. At the very least, they should be rewritten to use the established methodology of the rest of the project. 
--
<!-- alt ..reduced? 
Around #14 ( `"screen and (max-width:1010px)` ) we see the media queries begin to be defined using the [absolute](https://developer.mozilla.org/en-US/docs/Web/CSS/length#Absolute_length_units) length unit of `px`.  
While the arguments can be made for using either length unit (`px` or `em`) in media query definitions, the bigger issue in this particular instance is of consistency. With the vast majority of the styling rules being housed in `em` based media queries, these `px` based definitions [stand out](https://youtu.be/ueZ6tvqhk8U?t=20s) and provide a great starting point from which to begin examining things more closely.
-->

<!-- The length unit inconsistencies — notwithstanding, #17 ( `"screen and (max-width: 770px)"` )  -->
<!-- Notwithstanding the length unit inconsistencies mentioned previously, their doesn't seem to be anything inherently wrong at first glance.  
The issue starts to become more apparent when examining some of the other media queries. 
-->


The next point of interest involves #17 ( `"screen and (max-width: 770px)"` ). 
Beyond the previously mentioned length unit inconsistencies, their doesn't seem to be anything inherently wrong with this particular media query at first glance. The issue starts to become more apparent when it is compared against some of the other media queries. #16 ( `"screen and (max-width: 768px) and (min-width: 320px)"` ) and #19 ( `"screen and (max-width: 768px)"` ) are using incredibly similar (but not quite matching) values in their definitions.
The odds of a specific rule needing to be exactly 2px smaller than an established breakpoint isn't very high. 
The more likely explanation is that the author either forgot or wasn't aware of the exact breakpoint that is used elsewhere in the project. Either way, this can be viewed as something that should be flagged for a closer look. 



Finally, #20 ( `"screen and (min-width: 768px)"` ) is classic example of an overlap taking place. 

Finally, #20 ( `"screen and (min-width: 768px)"` ) appears to be overlapping with some media queries that are set to use `"max-width: 768px"` ( #16 & #19).

We know that with some media queries that are set to use `"max-width: 768px"` ( #16 & #19) 

It's no accident that frameworks like Bootstrap & Foundation define their breakpoints in a consistent manor that prevents overlap 
(examples [A](https://github.com/twbs/bootstrap/blob/master/less/variables.less#L314) & [B](http://foundation.zurb.com/sites/docs/media-queries.html#copy-btn-0)).
It's no accident that CSS frameworks define their breakpoints in a consistent manor that prevents overlap 
(e.g. [Bootstrap](https://github.com/twbs/bootstrap/blob/master/less/variables.less#L314) & [Foundation](http://foundation.zurb.com/sites/docs/media-queries.html#copy-btn-0)).

So, when there are multiple definitions checking a particular [media feature](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries#Media_features) for an identical value but with opposing prefixes, 
it is something that should be investigated. 

Perhaps it's just a simple inconsistency in how a particular breakpoint was authored, but there is also a possibility of a huge issue where multiple elements are getting conflicting styling instructions when the width is 768px. 

but it has the potential to 
but there is also a possibility of a huge issue where multiple elements are getting conflicting styling instructions when the width is 768px. 

a large set of elements are getting conflicting styling instructions when the width is 768px. 

At best, it's just a simple inconsistency in how a that particular breakpoint was authored, 

in a way that prevents them from over 
having multiple definitions checking a [media feature](https://developer.mozilla.org/en-US/docs/Web/CSS/Media_Queries/Using_media_queries#Media_features) for and identical value, but with opposing prefixes, 

at worst a set of elements are getting conflicting styling instructions when the width is 768px. 

The reason that frameworks like Foundation & Bootstrap define their breakpoints so that they don't 

[Foundation](http://foundation.zurb.com/sites/docs/media-queries.html#copy-btn-0)
[Bootstrap](https://github.com/twbs/bootstrap/blob/master/less/variables.less#L314) 







The general idea is to try to survey the CSS landscape from 30,000 feet, 

and look for things that seem different or [stand out](https://youtu.be/ueZ6tvqhk8U?t=20s). [Developers are creatures of habbit](https://www.safaribooksonline.com/a/the-software-craftsman/70409/).
If you see smoke rising out of the forest, it's probably worth taking a closer look 

forest from 

forCSS from 30,000 feet. If you see smoke 
What are doing once we have this data?

Once we have this data,

What do we do with this data? The general idea is to look for things that that seem [different or stand out](https://youtu.be/ueZ6tvqhk8U?t=20s). [Developers are creatures of habit](https://www.safaribooksonline.com/a/the-software-craftsman/70409/), so if something seems inconsistent, peculiar, or out-of-place, it's likely that it was written by a different developer, or under different circumstances. These are the places we want to initially focus on, as they are more likely yield potential refactoring opportunities. At the very least they can be brought into alignment with the rest of the codebase to help make everything more maintainable going forward.

Specifically, we're on the looking for things like:




on as they'll pro
attention 
What are doing once we have this data?

The general idea is to try to survey the CSS landscape from 30,000 feet. 

It's unlikely (but not impossible) that anything will appear to be outright broken from this vantage point i,




We obviously want to notice any glaring issues, but if this is a codebase that is already in production, the likelihood of finding stuff that is broken at this 

things that seem different or [stand out](https://youtu.be/ueZ6tvqhk8U?t=20s). 

Once we have this data, what are we looking for? 

Generally speaking we're on the look out for:






<!-- The most likely reason for this discrepancy is that the author either forgot, or wasn't aware of the exact breakpoint that is used elsewhere in the project.  -->
The author either forgot, or wasn't aware of the exact breakpoint that is used elsewhere in the project. 
Either way, this can be viewed as something that should be flagged for a closer look. 


forgetting the exact breakpoint that they should be using


There a couple which are using incredibly close (but not quite matching) values in their definitions, 
that are using similar values in their definitions.
There are a few that are 
 it's apparent that 


Taking a look at some of the other media queries which 
Looking at media queries that have similar 



multiple other media queries are using an incredibly close (but not quite matching) values in their definitions. 
= #16 ( `"screen and (max-width: 768px) and (min-width: 320px)"` )
= #19 ( `"screen and (max-width: 768px)"` )



= #21 ( `"screen and (min-width: 768px)"` )


This could be an instance of 
or the author forgetting the exact breakpoint 
easily spot inconsistent or mistyped values

(#17 vs #16,#19,21 )

Within the collection of `px` defined 

it provides a starting point from which to being

...at the very least, these should be rewritten to used the established methodology. 


 refactor  





<!-- last I remember, I was working in this area -->
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





<!--
and checking the documentation
They are all using em as their unit of measurement.

em that contain a large
large collections  chunk of style rules that were created inside media

all of media queries that were created using foundation variables
-->

---
---
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




