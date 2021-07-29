# CSS Interview Question

**What is CSS selector specificity and how does it work?**  
Specificity is basically is how the browser decides which style rules to render. Depending on which styling technique you use determines which styles will override another. So order goes from inline, ID, Classes, Tags and pseudo elements. Left side being more 'specific' than the right.

**What's the difference between "resetting" and "normalizing" CSS? Which would you choose, and why?**  
Resetting will remove all preset styling on elements which is good unconvential site designs and creating your own styles for each element. Normalization will adjust the styles on elements that will effect . One of these methods should be included to provide consistency across multiple browsers.

**Describe floats and how they work.**  
Before flexbox or grid, floats were mainly used to position elements. Floats does not get taken off the flow of the page.

**Describe z-index**  
Z-index basically determines which element should be infront of which element depending on how high the value is.

**Grid System vs Flex Box**  
Grid system is better for position elements as a whole and better for bigger applications that require more of a structure. I personally still use flex box because it is widely supported by all browsers compared to grid. Flexbox is mainly meant for 1-dimensional layouts while Grid is meant for 2-dimensional layouts.

**What are the advantages/disadvantages of using CSS preprocessors?**  
Some advantages of using a preprocessor is that it makes it more maintainable, usually features nested selectors which goes really well with BEM. You may also create variables for consistent themes, mixin for repeated css and ability to split your code into multiple file. As it goes with all new tools and library there will be a learning curve, extra steps and downloads you have to do.

**Describe the box model**  
Box model will calculate width, height, padding, borders and margin and determine how much space the element will take up.

**What does border-box do?**  
By default box sizing is set to content-box which only accounts for the content size. While border-box takes into account margin, padding and border as a whole
