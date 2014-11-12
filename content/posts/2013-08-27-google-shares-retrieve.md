---
title: 'What are the &#8216;Google+ shares&#8217; and how to retrieve them?'
author: Jean-Christophe Lavocat
layout: post
date: 2013-08-27
permalink: /content-marketing/google-shares-retrieve
dsq_thread_id:
  - 1653819002
snapEdIT:
  - 1
categories:
  - Content Marketing
tags:
  - +1
  - Comments
  - Google+
  - Ripples
  - Shares
---
Social networks all have different metrics. On Twitter, you can look for the number or retweets, on Pinterest, the number of &#8216;pinned&#8217; pictures, on LinkedIn, the number of &#8216;shares&#8217;, etc. Facebook is by far the more precise because you can get a number of likes, shares and comments. On Google+, the picture is not so clear yet. In this article we try to understand the different** available metrics from Google+** and we give you some code to** import the number of Google+ shares** in python and PHP.  
<!--more-->

## The different metrics on Google+ : comments, +1 and shares

On Google+ there is apparently three levels of engagement : sharing, agreeing (+1) and commenting. People can share, +1 or comment** a post** on Google+ or **any external website**. Google has also released a <a title="Google+ +1 button for your site" href="https://developers.google.com/+/web/+1button/" target="_blank">button</a> to allow +1 directly from a remote place, and you can use <a title="Add Google+ comments to your site" href="http://googlesystem.blogspot.com/2013/04/add-google-comments-to-any-web-page.html" target="_blank">some javascript</a> to embed Google+ comments on your website.

Surprisingly, to our knowledge, there isn&#8217;t a tool to show all these numbers in one same place yet. You can get the number of +1 on <a title="Shared Count" href="http://sharedcount.com/" target="_blank">SharedCount</a>, the number of comments on *Terry Simmonds*&#8216; <a title="Get number of comments" href="http://www.sim64.co.uk/shared/" target="_blank">tool</a> and the number of shares using <a title="Google Ripples" href="https://support.google.com/plus/answer/1713320?hl=en" target="_blank">Google Ripples</a>.

<p style="text-align: center;">
  <img class="aligncenter  wp-image-60" alt="Google Ripples" src="http://blog.wordiz.it/wp-content/uploads/2013/08/ripples.png" width="450" />
</p>

While the displayed +1 number on your website <a title="Google +1 aggregates +1 and shares" href="https://plus.google.com/107022061436866576067/posts/1jW7NJZCiHJ" target="_blank">aggregates all possible social events</a> (plus, reshares), the comments and shares reflects stronger interactions. Typically, the number of comments will include the number of shares and the number of comments made on your post or on a share, whereas, the number of shares will be limited to shares and re-shares only. The +1 signal is really easy to get growing whereas it is more difficult to have a high number of shares/comment without a great content.

In summary :

  * **+1** are the sum of 
      * Number of direct +1 received on a page
      * Number of shares and reshares
  * **Comments** are the sum of 
      * Shares and reshares
      * Comments and replies posted on G+ or on the website
  * **Shares** is only the number of shares and reshares

## Shares on Google+ , why is this so complicated ? The SID bug

Some month ago, a small **bug** impacting on Google+ comments has been <a title="Bug Google+ comments" href="https://plus.google.com/107547897649550914425/posts/CLWDRR14N35" target="_blank">discovered</a> by *Terry Simmons* who contacted the Google+ team for a fix which <a title="Fix for the _sid=0 bug on G+ comments" href="https://plus.google.com/107547897649550914425/posts/U66AsMMHCja" target="_blank">arrived</a> some time later. However this bug seems to be still active when you use Ripples.

It is usually pretty easy to use **Ripples** to get the number of shares : <a title="Using Ripples" href="https://plus.google.com/u/0/ripples/details?url=[your_url]" target="_blank">https://plus.google.com/u/0/ripples/details?url=[your_url]</a> but because of the bug, your website URL might not be the one saved correctly when it is shared on G+ by someone. When someone posts a link on Google+, an extra parameter (sid) is sometimes added.

If you cannot find all the expected shares, you should try adding a parameter at the end of your URL : %23\_\_sid%3D0 (#\_\_sid=0) or %23\_\_sid%3D3 (#\_\_sid=3) . On the URL I used for a test, I can find shares for <a title="Ripples with sid=0" href="https://plus.google.com/u/0/ripples/details?url=http%3A%2F%2Fwww.presstor.fr%2Ftechnologie%2Fmichelin-encourage-l-utilisation-de-puces-rfid-dans-pneus-188%23__sid%3D0" target="_blank">sid=0</a> and for <a title="Ripples sid3" href="https://plus.google.com/u/0/ripples/details?url=http%3A%2F%2Fwww.presstor.fr%2Ftechnologie%2Fmichelin-encourage-l-utilisation-de-puces-rfid-dans-pneus-188%23__sid%3D3" target="_blank">sid=3</a> and no shares for the <a title="Ripples without sid" href="https://plus.google.com/u/0/ripples/details?url=http%3A%2F%2Fwww.presstor.fr%2Ftechnologie%2Fmichelin-encourage-l-utilisation-de-puces-rfid-dans-pneus-188" target="_blank">standard url</a>.

## How to get some &#8216;Ghost&#8217; shares ?

When you submit a post on G+, only the initial content is saved on Ripples. If you later** edit your post** and remove or edit the initial url, **it will NOT be updated in Ripples**. While doing my tests I thought that a bug was present and tried the following : first sending a post with my URL to G+, then removing the URL, and later asked some friends to share the edited post. I expected to see the number of shares growing. But finally it&#8217;s not the case.

You cannot get &#8216;fake shares&#8217; but you can however share a post with a ghost link. That is the reason why I re-named this section &#8216;**ghost share**&#8216;.

<div id="attachment_42" style="width: 298px" class="wp-caption aligncenter">
  <img class="size-full wp-image-42" alt="Fake shares" src="http://blog.wordiz.it/wp-content/uploads/2013/08/fake_share.png" width="288" height="244" />
  
  <p class="wp-caption-text">
    Here, the initial link was heading to www.presstor.fr. After the edit, the message contains a link to www.example.com
  </p>
</div>

## Share and pictures/media

If you post a link together with a picture (first put the link, wait until the excerpt is loaded then removed the excerpt) you can get more attention from readers, and more reshares and +1. The number of +1 will be attributed to your link, but it is not the same story for shares.

In the case of a share, your URL has to be the only &#8216;rich element&#8217; present in the body of the post. If you have a link with a picture, it will not count as a share (because you have remove the link&#8217;s description to put the picture). So to get some reshares, you need some** great content** .

## Google can&#8217;t add

When you check on Ripples a post, you can get the number of public shares but also the number of private shares, namely the <a title="Total number of shares on G+" href="https://plus.google.com/u/0/ripples/details?activityid=z12bdfgzpwjjjrbg504celxqizrqc3fxllw0k" target="_blank">total shares</a>.

In the case of URLs, only the number of public shares is provided.  Google states clearly &#8220;we don&#8217;t show private shares&#8221; and probably does not take them into account to avoid spam.** Be sure to always share your link publicly**.

During my tests, I found a really funny situation and I don&#8217;t know how to interpret it. For one of my <a title="Ripples and incorrect numbers ?" href="https://plus.google.com/u/0/ripples/details?url=http%3A%2F%2Fwww.presstor.fr%2Ftechnologie%2Fmichelin-encourage-l-utilisation-de-puces-rfid-dans-pneus-188%23__sid%3D0" target="_blank">test link</a>, there was two contradicting data : the number of shares (indicated on the left) and the list of shares on the right, which was clearly not equal to the number indicated on the left.

<div id="attachment_40" style="width: 560px" class="wp-caption aligncenter">
  <a href="http://blog.wordiz.it/wp-content/uploads/2013/08/google_plus-shares-ripples_cannot_count.png"><img class=" wp-image-40 " alt="Google+ Ripples - Cannot count the total shares correctly" src="http://blog.wordiz.it/wp-content/uploads/2013/08/google_plus-shares-ripples_cannot_count.png" width="550" /></a>
  
  <p class="wp-caption-text">
    How many shares can you count on the right? Four or five?
  </p>
</div>

If someone understands this point, I am really curious to get your opinion as a comment below.

## Post with several links

What happens if you send a post with several links? For the sake of fairness, I was expecting to see a share added for every single URL, but this does not seem to be the case. I did not spend too much time on this test, but you are welcome to post your results in a comment below.

So, to summarize, **when you share a post with several links, only the first one receive a share** ! When I write the &#8220;first one&#8221;, I mean one from which Google+ extracted the content/picture for the small excerpt at the bottom of your post.

## How to retrieve the number of Google+ shares

One can easily retrieve the number of shares given by Google Ripples. By using the same URL that Ripples use, you can extract all the share information you like (the people who reshared your post, the time etc). I give you to sample of **code to extract the number of shares in PHP and in Python** (hat tip to Regis Montoya, creator of the nice google app <a title="C SIP Simple" href="https://play.google.com/store/apps/details?id=com.csipsimple&hl=en" target="_blank">CSIPSimple</a> for the python version) :

### Python

<pre class="brush: python; title: ; notranslate" title="">import urllib,urllib2,json
target_url="http://www.wordiz.it"
target=urllib.quote_plus(target_url+"#__sid=0") #url-friendly
data = 'f.req=%5B%22'+target+'%22%2Cnull%5D&'
url = "https://plus.google.com/u/0/ripple/update"
req = urllib2.Request(url, data, {'Content-Type': 'application/x-www-form-urlencoded'})
f = urllib2.urlopen(req)
response = f.read()
f.close()
response=response[6:] #remove some bad characters

# Remove ",," (non valid json) and replace with ,null, (
# Do that twice because re do not take into account overlapping matches)
response_json_str = response.replace(",,", ",null,").replace(",,", ",null,")
datas = json.loads(response_json_str)

# Find relevant data -- might need to be changed depending on possible incoming format
# Maybe need some recursive func searching for list with first item "orr.c"
orr_c = datas[0][1][-3]
print str(orr_c)+" share(s) pour "+target_url

</pre>

### Php

<pre class="brush: php; title: ; notranslate" title="">&lt;?php

$target="http://www.wordiz.it";
$data="f.req=%5B%22".$target."%22%2Cnull%5D&";
$url = "https://plus.google.com/u/0/ripple/update";

$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_POST, 1);
curl_setopt($ch, CURLOPT_POSTFIELDS, $data);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, array('application/x-www-form-urlencoded'));

$curl_results = curl_exec ($ch);
curl_close ($ch);
//echo $curl_results;
$curl_results=substr($curl_results,6);
$curl_results = str_replace(",,",",null,", $curl_results);
$curl_results = str_replace(",,",",null,", $curl_results);
// print_r($curl_results);

$parsed_results = json_decode($curl_results, true);
echo($parsed_results[0][1][4])." Google shares on ".$target;

?&gt;
</pre>

## Share me

Now, if you enjoyed the article, please help us and share this article on Google+. Remember, to do it correctly :

  1. Put the link to the article first (in case you have other links)
  2. Don&#8217;t add an extra image
  3. You can modify the text afterwards, it will not affect

Simple !

## Other metrics

Let&#8217;s say you are a blogger and want more data about your articles. You can check all your posts one by one or you can try using [WordiZ][1]. There you will **get more metrics associated with your articles** (the ones you tagged with rel=&#8221;author&#8221;). <a title="Signup on WordiZ" href="http://wordiz.it/accounts/login/google-oauth2/" target="_blank">Signup now</a> for an early invitation, we need some extra members to launch our beta.

> Hat Tip to <a title="Mark Traphagen" href="https://plus.google.com/+MarkTraphagen/posts" target="_blank">+Mark Traphagen</a> for the initial idea for the post

 [1]: http://www.wordiz.it "WordiZ"