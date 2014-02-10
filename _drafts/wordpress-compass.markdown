---
layout: post
title:  "Set up Sass & Compass for WordPress theme development"
date:   2014-02-06 11:00:18
categories: front-end
tags: WordPress Sass CSS3 Compass WordPress theme development workflow set-up
description: A blogpost showing how to use Sass and Compass in a WordPress project

excerpt: "The dust has settled between the vanilla CSS, LESS and Sass brawl. And you're using Sass to compile your CSS now. That's great! Damn what a time and headache saver right? You don't use Sass? Please give it a try and say bye to vanilla CSS. Now that you're just feelin comfortable using  Sass you can't go back, i know. But your next project involves WordPress. How would one implement Sass (and Compass)? Let me show you how I do it."

---

When one is switched to Sass, it's hard to go back to just CSS. I'm assuming you already use Sass/Compass and now want to use these beautiful technologies in your next *WordPress* project. Chris Coyier from the famous <a target="_blank" href="http://css-tricks.com/">CSS tricks</a> explains the problem when <a target="_blank" href="http://css-tricks.com/compass-compiling-and-wordpress-themes/"> Implementing Sass </a>and gives one solution. I'll go over the problem as well, but I'll give another solution to the matter.

If you don't have Sass installed yet, please take a look at their <a target="_blank" href="http://Sass-lang.com/install">install guide</a>.
While you're at it, please make sure to <a class="_blank" href="http://compass-style.org/install/">install the Compass Sass extension</a> as well.


#Problem
The problems with using Sass in WordPress is that WordPress:

1. needs a style.css file in the roots of its theme folder.
2. this file needs a comment block to be recognized as theme, like so:

{% highlight css %}
/*
Theme Name: My Custom WordPress theme
Theme URI: http://superbwordpressthemebyme.com/
Author: Jeffrey Nijstad
Author URI: http://jnijstad.com
Description: This theme etc etc...
Version: 1.0
License: GNU General Public License
License URI: license.txt
Text Domain: custom-theme
Domain Path: /languages/
Tags: light, minimal, two-column

This theme, like WordPress, is licensed under the GPL.

*/
{% endhighlight %}

This is okay when you have a small Sass file at your root folder called style.scss and just let it compile to style.css with the required comment block at the top.

<figure class="overflow overflow-20 shadow-on">
	<img src="{{ site.url }}/images/wordpress-tree.png" alt="Wordpress tree directory example">
	  <figcaption>A sample of a partial Wordpress theme directory with style.css at root.</figcaption>
</figure>



But what if you have multiple Sass stylesheets? What if you want a couple of _footer.scss, _header.scss, _typography.scss partials for example? 

**Check out the <a target="_blank" href="http://sass-lang.com/documentation/file.SASS_REFERENCE.html#partials">Sass docs</a> to see why those filenames have underscores in their name.**

You don't want these floating around somewhere. For me, I like to add the following self explanatory structure to my directory:

{% highlight html %}
- wp-content
	- themes
		- mytheme
            - config.rb
            - /images
			- /sass
                - main.scss
                - vendor/
                    - _grids-example.scss
                    - _header.scss
			- /css
            - /js
            - style.css

{% endhighlight %}





<figure class="fit">
	<img src="{{ site.url }}/images/1.jpg" alt="">
	  <figcaption>A cheeky macaque, Lower Kintaganban River, Borneo. Original by <a href="http://www.flickr.com/photos/rclark/">Richard Clark</a></figcaption>
</figure>

<figure class="overflow overflow-40">
	<img src="{{ site.url }}/images/2.jpg" alt="">
	  <figcaption>A cheeky macaque, Lower Kintaganban River, Borneo. Original by <a href="http://www.flickr.com/photos/rclark/">Richard Clark</a></figcaption>
</figure>

<figure class="overflow overflow-70">
	<img src="{{ site.url }}/images/2.jpg" alt="">
	  <figcaption>A cheeky macaque, Lower Kintaganban River, Borneo. Original by <a href="http://www.flickr.com/photos/rclark/">Richard Clark</a></figcaption>
</figure>

Let us assume that at Yahoo the logo design team (including the intern) is comprised of the best designers in the field. It is conceivable that, with some luck, this dream team can design a logo “from start to finish” over a weekend. It sure is fun “weighing every minute detail” with a team of outstanding professionals. And what is more efficient than working directly with the CEO on the brand identity? A dream setup. Also, it’s cheap. A weekend for a logo, instead of paying a branding agency millions and waiting months for something that can be done in a couple of days? That’s smart business!

You'll find this post in your `_posts` directory - edit this post and re-build (or run with the `-w` switch) to see your changes!
To add new posts, simply add a file in the `_posts` directory that follows the convention: YYYY-MM-DD-name-of-post.ext.


Jekyll also offers powerful support for code snippets:

> Blockquotes are very handy in email to emulate reply text.
> This line is part of the same quote.

Quote break.

> This is a very long line that will still be quoted properly when it wraps. Oh boy let's keep writing to make sure this is long enough to actually wrap for everyone. Oh, you can *put* **Markdown** into a blockquote. 

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll's GitHub repo][jekyll-gh].

[jekyll-gh]: https://github.com/mojombo/jekyll
[jekyll]:    http://jekyllrb.com
