---
title: How to display your best articles on the web ?
author: Jean-Christophe Lavocat
layout: post
date: 2014-07-29
permalink: /features/wordpress_widget
dsq_thread_id:
  - 2882937903
categories:
  - Features
tags:
  - Plugin
  - Widget
  - Wordpress
---
We already presented our WordPress widget to <a title="Elokenz Widget for WordPress" href="http://blog.elokenz.com/features/wordpress-widget-showcase-best-articles" target="_blank">showcase your best articles</a>. We made some improvement to the basic widget and want to share with you the new features. The widget is useful for authors who are using the G+ authorship system. It takes in input your Google+ id and list your most shared articles on the social networks.

## Who could gain from this widget ?

Before entering into details, let&#8217;s see who is likely to use this widget. Take my friend <a title="Ann Smarty" href="http://www.seosmarty.com/" target="_blank">Ann Smarty</a> she is frequently writing on <a title="Social Media Examiner" href="http://www.socialmediaexaminer.com" target="_blank">several</a> <a title="Search Engine Journal" href="http://www.searchenginejournal.com/" target="_blank">websites</a>. Her various writings are often covering complementary topics but his audience sometime does not know he is writing on other websites.

She had recently published a viral article on one of these websites, but this cannot be reflected on her personal blog. On this private blog she wanted to showcase her best articles from all over the web, not only from her own blog.

When Ann heard about our widget she was one of the first to use it. It allowed her to **collect automatically the articles** which have been** most shared on social networks** and to display these numbers on her personal blog for self promotion. This is what is displayed on her website these days :<img class="aligncenter wp-image-304 size-full" src="http://blog.elokenz.com/wp-content/uploads/2014/07/ann_smarty_best_articles.png" alt="Elokenz - Widget best articles example - (via @elokenz)" width="275" height="335" />

So, if you are like her, and write on several places around the web, you might want to display your &#8216;content portfolio&#8217; too. Enters the **Elokenz widget**.

## How to install the widget ?

This widget works with the database we are building with <a title="Helping Authors to be more visible" href="http://www.elokenz.com" target="_blank">Elokenz</a>. The first thing you need is to use the authorship tag. Then, depending on your installation, you can use the code we provide on <a title="Elokenz Dashboard - Widget" href="http://www.elokenz.com/dashboard/widgets/" target="_blank">our dashboard</a> or the <a title="Wordpress widget - Socially best articles" href="http://wordpress.org/plugins/elokenz-most-shared-articles-for-authors/" target="_blank">wordpress plugin</a> directly.

<a title="Wordpress Elokenz Plugin" href="http://wordpress.org/plugins/elokenz-most-shared-articles-for-authors/" target="_blank"><img class="aligncenter wp-image-305" src="http://blog.elokenz.com/wp-content/uploads/2014/07/elokenz_wordpress_plugin.png" alt="elokenz_wordpress_plugin" width="500" height="348" /></a>

Once you have collected the good code (self hosted site) or the plugin, you have few settings to customize the display.

<img class="aligncenter size-full wp-image-306" src="http://blog.elokenz.com/wp-content/uploads/2014/07/screenshot-3.png" alt="elokenz_widget_settings" width="286" height="660" />

First, the widget comes with two basic themes : **bright** or **dark**. Depending on your template you might need to have one or the other. If you need other colors, drop a comment below and we will publish an article to explain how to tune the CSS.

Second : you might want to display 1, 2 , 3 .. or up to 10 articles. That&#8217;s pretty self-explanatory.

The **ordering system** represent the algorithm that is applied to sort your articles. Do you focus on *Facebook likes* or on *Twitter mentions* ? You can change the order here, or keep the default : sum of Facebook likes + Twitter mentions + Google+ plus ones.

On WordPress we added an option to print links with a &#8220;nofollow&#8221; attribute. Depending on the blog where you install the widget, you might not want to have dofollow links (who knows&#8230;)

Finally, comes the only required field, your G+ id. For the moment you still need to copy/paste your id number. In the future we might implement a system to convert your &#8216;vanity url&#8217; into the G+ id, but it&#8217;s not yet the case.

## Do you need the widget on a single page ?

On WordPress we added a shortcode support recently. This means you can import the widget on a given page or post, instead of having it sitewide on your sidebar.

For this, you need to use the following syntax :

For that, you can add the following text when you are editing an article :

    [elokenz_widget user_id="113400244614302404694"]

(where `113400244614302404694` is replaced by your Google+ id).

You can use several **arguments** to configure the output :

  * *width* [integer] : give the width in pixel. (Default : the widget will use all available space)
  * *follow* ["do"/"no"] : use dofollow links or nofollow links. (Default : dofollow links)
  * *style* ["bright"/"dark"] : use a bright or dark background. (Default : &#8220;bright&#8221;)
  * * item*_*number* [integer < 10] : how many articles do you want to list here ? (Default : 5)
  * * network* [0,1,2 or 3] : which ordering system should we use ? (Default : 0) {0. sum of all metrics 1. Twitter 2. Facebook 3. Google+}

**Example** :

`[elokenz_widget user_id="113400244614302404694" follow="no" item_number="10" style="dark" network="1"]`  
will output a list of 10 articles, with nofollow links, on a dark background, ordered according the number of RTs.

## How can you contribute ?

Since we had to change our name recently we lost all our nice statistics. If you use the widget and like it, you can help us in different ways :

  * <a title="Tweet about the plugin" href="https://twitter.com/home?status=I%20am%20using%20a%20new%20WP%20plugin%20to%20display%20my%20most%20shared%20articles%20:%20http://blog.elokenz.com/features/wordpress_widget" target="_blank">Tweet about it</a> or share it on <a title="Wordpress Widget" href="https://www.facebook.com/sharer/sharer.php?u=http://blog.elokenz.com/features/wordpress_widget" target="_blank">Facebook</a> or <a title="Wordpress Widget" href="https://plus.google.com/share?url=http://blog.elokenz.com/features/wordpress_widget" target="_blank">Google+</a>
  * Try it, and leave us a comment or <a title="Review Elokenz plugin" href="http://wordpress.org/support/view/plugin-reviews/elokenz-most-shared-articles-for-authors?filter=5#postform" target="_blank">a review on the plugin page</a>
  * Write an article about how you use the plugin and **get featured here**

Do not hesitate if you find any bug, let us know (the easiest is to comment here) &#8230; One of our early user <a title="Didier J Mary" href="https://plus.google.com/+DidierJMARY/about" target="_blank">Didier</a> from <a title="Kotonteej - African Music" href="http://www.kotonteej.com/" target="_blank">KotonTeej</a> was the first to discover a big flaw in in the previous version.