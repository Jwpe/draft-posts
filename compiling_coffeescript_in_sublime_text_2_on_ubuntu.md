JavaScript is an incredibly useful programming language. Even though most of my code is written in Python, both at work and in my own projects I often make use of JS for a variety of purposes, mostly client-side logic. However, since I’m so used to lovely Python syntax, I prefer to write my JS code using CoffeeScript.




CoffeeScript is awesome. Obviously it’s not a substitute for knowing and understanding JS, but in my limited experience it has helped immensely with writing clear code quickly. However, I have one problem with the language. Compiling.




Before we go any further, here’s how to install the CoffeeScript compiler itself on Ubuntu, my working OS:




<script src="https://gist.github.com/Jwpe/5281005.js"></script>


My colleagues who work on Macs can make use of delightful software such as [LiveReload](http://livereload.com/) to watch their CoffeeScript files and auto-compile them to JavaScript on save. As an Ubuntu man, I naturally abhor all non-command-line applications*. Besides, I haven’t run into any good compilers/watchers that are available on Linux. As a result, I’m limited to using the command line every time I want to compile my CoffeeScript...or am I?




*not actually true at all. this is a joke




I write the vast majority of my code in the fantastic Sublime Text 2. This text editor allows the addition of build systems, scripts which can call shell commands to compile files. There is even a package called [CoffeeCompile](https://github.com/surjikal/sublime-coffee-compile) available through Sublime’s own package manager, which will install a build system for CoffeeScript. Yay! Now we can compile CoffeeScript straight from the editor! 




***


For simple usage, the above is more than sufficient. However, CoffeeCompile compiles .coffee files to .js files in the same directory - so my_app/app.coffee would compile to my_app/app.js. All well and good if you have a nice simple codebase, but once you start getting more complicated directory structures, this falls short. 




What I really wanted to do was to mirror my CoffeeScript file directory structure with JS. I wanted a file at /my_app/coffeescript/models/backbone_models.coffee to compile to /my_app/js/models/backbone_models.js. Here’s how I made it happen. 




From Sublime Text 2, use the Tools/Browse Packages menu option to view installed packages. Find the CoffeeScript package. We’re going to write a custom build system for CoffeeScript, in the file Packages/CoffeeScript/Commands/CoffeeScript.sublime-build. When we hit the build shortcut (CTRL+B), this command will be run, and will build our file as specified below.


<script src="https://gist.github.com/Jwpe/5281067.js"></script>


The code above merits a little explanation. For starters, let’s look at the “cmd” variable. For some reason best known to itself, Sublime prefers that command line instructions are passed in as a list of quoted words. So first we call the coffeescript compiler with “coffee”, then pass the flags “--compile” (hopefully self-explanatory) and “--output”, which specifies the destination path of our compiled file. The next section - passing a parameter to the output flag - is more interesting. Using Sublime’s build system syntax, we can take the file path of our original coffeescript file, and substitute any instances of ‘coffee’ with ‘js’. This allows us to achieve the mirrored directory structure described above. The final parameter is simply the target file to be compiled.




Hopefully, this should give a clear idea of how to compile your CoffeeScript files on Ubuntu. Remember, custom build systems are limited only by your imagination*! Have you found a better or easier way to compile CoffeeScript on Linux? Let me know in the comments below.




*as well as Sublime Text 2’s syntax, the arguments which your shell command accepts, and so on and so forth