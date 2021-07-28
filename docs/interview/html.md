**Why you would use a srcset attribute in an image tag? Explain the process the browser uses when evaluating the content of this attribute.**  
The srcset attribute is used to serve different size images to different display widths. This will increase the performance on smaller devices and provide higher quality for bigger screens.

**What is progressive rendering?**  
Progressive rendering are techniques to improve webpage performance for devices with slower connection. An example of progressive rendering is lazy loading, that is when resource is downloaded on demand instead of the inital rendering of the page.

**Describe the difference between `<script>`, `<script async>` and `<script defer>`**  
With script the is executed immediately depending on where it is in the html. This may cause parsing of html to be blocked, thats why it is generally a good idea to place in the bottom of your body tag. Async will parse both html and the script in parallel and is executed as soon as it becomes available. Defer will ensure that html is fully parsed before executing which is similar as putting script at the bottom of body.

**Describe the difference between a cookie, sessionStorage and localStorage.**  
Cookie, sessionStorage and localStorage are client side technology for storing data as strings in a key value pair. Some differences are that cookies are smaller in terms of storage and you have to manually set the expiry time or date for cookies, as for localStorage it stays persisent and sessionStorage expires when you close the tab. Another difference is that cookie automatically sends data back to server with every http request.

**What are data- attributes good for?**  
Generally no encourged to use them anymore unless it for testing. The data- attribute was used
