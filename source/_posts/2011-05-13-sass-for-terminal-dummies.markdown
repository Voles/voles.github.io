---
layout: post
title: "Sass for Terminal dummies"
date: 2011-05-11 20:57
comments: true
categories: [sass, scss, less, css, styling]
---

A while ago, there were some posts on [Forrst](http://www.forrst.com "Forrst") about LESS. [LESS](http://www.lesscss.org/ "Less") is a tool, made to add extra functionality to CSS. Until now I only wrote _static_ CSS-files, sometimes with over 1500 lines of code for a simple website. To make the stylesheet more readable, I grouped codeblocks, used comments, added extra indent with tabs, etc.

Splitting up the stylesheet in separate files is also an option to keep everything structured, but that adds a lot of extra HTTP-request.

Recently, one of our teachers told us about [Syntactically Awesome Stylesheets (Sass)](http://sass-lang.com/ "Sass"). It is more or less the same as LESS, the main difference is that LESS uses the CSS syntax and Sass uses its own syntax. But it’s possible to use CSS-syntax with [SCSS](http://sass-lang.com/docs/yardoc/file.SCSS_FOR_SASS_USERS.html "Scss").

I was (and still am) very excited about it, and I'd like to share both my experience and knowledge with the rest of the world.

### What is Sass?
> Sass makes CSS fun again. Sass is an extension of CSS3, adding [nested rules](http://sass-lang.com/#nesting 'Sass nesting'), [variables](http://sass-lang.com/#variables 'variables'), [mixins](http://sass-lang.com/#mixins 'Sass mixins'), [selector inheritance](http://sass-lang.com/#extend 'selector inheritance'), [and more](http://sass-lang.com/docs/yardoc/file.SASS_REFERENCE.html 'More information about Sass'). It’s translated to well-formatted, standard CSS using the command line tool or a web-framework plugin.

> <cite>[sass-lang.com](http://www.sass-lang.com 'Sass homepage')</cite>


### Compass
One of the disadvantages of pure CSS was that if you import other CSS-files, you create extra HTTP-requests. Compass is a framework that makes it possible to compile all your imported CSS-files into one CSS-file.

I think there is no reasen why you wouldn’t use Compass if you work with Sass.

### Using Sass
To use Sass first create two new folders `css` and `sass`. In the same directory, create a file named `config.rb`. Add these lines to the file:

{% codeblock lang:ruby %}
css_dir = "css"
sass_dir = "sass"
output_style = :compressed
{% endcodeblock %}

The first line refers to the directory were your final CSS-file will be compiled to. The second line tells where your .scss-files are stored.

The last line tells the compiler to compress the final CSS-file, so you will save some bandwith (which is important for mobile-applications).

Now make a file named `screen.scss` in the directory `sass/`. Here you can write CSS-code like you did before.

Now we first have to install Sass and Compass. Type these two commands in the Terminal, to install both Ruby Gems.

{% codeblock %}
$ sudo gem install haml
$ sudo gem install compass
{% endcodeblock %}

To compile the file, we'll use Terminal. Go to the folder `sass` we have just created. To change the current directory, type the command `cd` and then   the path you want to go to. E.g. `cd /Applications/MAMP/htdocs/my-first-sass-project`.

Next, we have to compile the `screen.scss-file`. We will compile the file using Compass. Use the commando `compass compile sass/screen.scss` to compile your scss-file.

Now look at your `css-folder`. There should be a file named `screen.css`, with your previously written CSS-code, compressed.

That’s it. If you don’t want to manually compile the .scss-file after you saved it, you can use the commando ‘watch’. Use `compass watch sass/screen.scss` to automatically compile your sass-file when you make some changes (and save the file).

Sass offers some great build-in functions for [color manipulations](http://nex-3.com/posts/89-powerful-color-manipulation-with-sass 'color-manipulations'), be sure to check it out if you want to learn more about it.

### Sass functions
__Variables__  
You can declare variables and use them everywhere in your .scss-file. This can come in handy when you wan to use the same colors over and over again for e.g. headings, links, menu...

__Nesting__  
You can write much cleaner CSS-code with nesting.

{% codeblock lang:css %}
ul.message {
  li.warning {
    color: yellow;
  }

  li.error {
    color: red;
  }

  li.success {
    color: green;
  }
}
{% endcodeblock %}

__Mixins__  
Mixins are like functions. You can pass some parameters and it gives you the result you want.
{% codeblock lang:css %}
@makebox ($background, $border, $width) {
  background: $background;
  border: 1px solid $border;
  width: $width;
}
#boxA {
  @include makebox(#FF0000, #000000, 150);
}

#boxB {
  @include makebox(#00FF00, #CCCCCC, 375);
}
{% endcodeblock %}

__Inheritance__  
It is possible to extend selectors from other selectors.

{% codeblock lang:css %}
.blue {
  background: #0000FF;
  border: 10px dashed #0000FF;
}

#box {
  @extend .blue;
  width: 160px;
}
{% endcodeblock %}

If you like what you see, be sure to take a look at these resources to learn Sass. The most complicated part is installing / compiling the files. Most other things speak for themselves.

### Further reference
* [Sass homepage]('http://sass-lang.com/' 'Sass homepage')
* [LESS homepage]('http://www.lesscss.org/' 'LESS CSS homepage')
* [Quickstart guide to Sass]('http://blog.danielfischer.com/2011/04/18/quickstart-guide-to-using-compass-haml-sass-scss-with-rails-3/' 'Quickstart guide to Sass')

Feel free to leave a comment with your thoughts on Sass. I hope you've enjoyed this one!
