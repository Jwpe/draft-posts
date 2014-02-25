Sublime Text 2 is my favourite editor for coding. Admittedly, my experience with editors is far from exhaustive. I know that there are many exciting editors and IDEs available to the modern programmer, many of which I haven’t explored. However, I have been using Sublime for a long time - the better part of a year - and it has yet to let me down in functionality. If you’re sick of Notepad or TextMate, and not quite prepared for the [vim learning curve](http://vim-adventures.com/), you should definitely try it out. With a free, time-unlimited evaluation copy available, there’s no reason not to.








One of the things I love about Sublime is the plug-and-play style with which you can add packages. These packages do everything from [changing the theme of the editor](https://github.com/wesbos/cobalt2), to allowing [compiling of code in-editor](https://github.com/surjikal/sublime-coffee-compile), to checking if your code is correctly formatted. Essentially, it’s very easy to tweak Sublime’s functionality to suit your needs.








Packages live in a hidden directory (.config/sublime-text-2/Packages in your home directory on Ubuntu) and can easily be installed by grabbing them from github and putting them straight into the directory. “Github?” I hear you cry - “Directories? That’s much too complicated and confusing for me!”* Never fear: thanks to one package in particular, installation of subsequent packages can be rendered so simple that you don’t even need to leave the editor to do it.








*I assume you won’t actually be crying this. However, everyone loves simplicity.








Enter Sublime Package Control, arguably the king of packages. If you’re using Sublime and you don’t have it, [install it now](http://wbond.net/sublime_packages/package_control/installation).








Right, done? Now, let’s go through installing a package from within Sublime. Open the editor and hit Ctrl+Shift+P (Cmd+Shift+P on Mac) to open up the Command Palette. Start typing “package” into the search box, and you’ll be greeted with a variety of Package Control commands. Find and select Package Control: Install Package. You’ll be greeted with a searchable list of installable packages.


![Sublime Text 2 Package Manager](https://jwpevans.s3.amazonaws.com/images/package_manager.png)


![Select Package](https://jwpevans.s3.amazonaws.com/images/select_package.png)


Let’s try installing one! Choose a package which sounds useful to you. I chose Python Flake8 Lint, which checks your Python syntax for errors and compliance to PEP8. Select it, and you’ll see a progress message magically appear in the bottom bar, followed quickly by a success message.


![Installing Package](https://jwpevans.s3.amazonaws.com/images/installing_package.png)




And that’s it. Your new package is installed. Thanks, Sublime Package Control! 








Know any other cool Sublime Text 2 tricks? Want to rant about how *insert editor here* is way better? Hit up the comments.