## loadCSS [Remove Old Stylesheet]

This is a branch of [filamentgroup/loadCSS](https://github.com/filamentgroup/loadCSS) that prevents stylesheets from adding more than once.

The changes I made check each stylesheet's href="" attribute, and if it matches the one specified in the loadCSS() function - it will be removed before it is added again.

So let's say you have a form that submits though ajax and you want to load a new stylesheet asynchronously if the server hits back with a 200 OK (perhaps some css to format a success message). If the form is submitted twice or more (very feasible in some scenarios) - the stylesheet will be appended to the DOM more than once. Although this shouldn't make a difference to the rendering of the css, appending the same stylesheet to the document more than once seems very wrong.
