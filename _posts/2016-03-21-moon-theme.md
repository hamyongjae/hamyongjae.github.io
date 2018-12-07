---
layout: post
title:  "나혼자 못산다"
date:   2018-12-07
excerpt: "Spring Framework기반 동행을 구해주는 사이트"
project: true
tag:
- Spring Framework
- HTML5
- CSS
- JavaScript
- Bootstrap
- MVC Model
comments: true
---

![img_portfolio1_logo](https://user-images.githubusercontent.com/19748922/49650938-2d1e2980-fa71-11e8-9865-e0e0ca7e1592.jpg)
    
<center><b>나 혼자 못산다</b> Website Main Page</center>

나홀로족이 유행하는 시대에 반대로 혼자 잘 못 하는 사람들을 위한 동행을 구해주는 것을 목표로 하는 **Spring Framework**기반의 웹 프로젝트를 1개월 동안 3명의 팀원이 함께 진행하였습니다.

<iframe src="https://ghbtns.com/github-btn.html?user=hamyongjae&repo=hamyongjae.github.io&type=star&count=true&size=large" frameborder="0" scrolling="0" width="160px" height="30px"></iframe>


## 사용 기술
* HTML5 / CSS3.0 / JavaScropt
* Bootstrap
* jQuery / AJAX 
* Apache Tomcat 9.0 
* JSP / Servlet
* Spring Framework MVC Model
* OracleDB (MariaDB) / JDBC / Mybatis
* 네이버 지도 API
* Amazon EC2 - AWS



## Preview

{% capture images %}
	https://user-images.githubusercontent.com/19748922/49650958-3effcc80-fa71-11e8-86f2-2a338b50dce7.jpg
	https://user-images.githubusercontent.com/19748922/49650959-3f986300-fa71-11e8-942c-e0dd03c3a97f.jpg
    https://user-images.githubusercontent.com/19748922/49651121-b6cdf700-fa71-11e8-8c56-8ba0b8489b7d.jpg
{% endcapture %}
{% include gallery images=images caption="Screenshots of Project" cols=3 %}

---
<!--
{% capture images %}
	https://cloud.githubusercontent.com/assets/754514/14509718/61b09a20-01d6-11e6-8da1-4202ae4d83cd.png
	https://cloud.githubusercontent.com/assets/754514/14509715/61aa9d00-01d6-11e6-81a6-c6837edf2e84.png
{% endcapture %}
{% include gallery images=images caption="Moon Theme on Small Screen Size" cols=2 %}      
      
See a [live version of Moon](http://taylantatli.github.io/Moon) hosted on GitHub.      

## Site Setup
A quick checklist of the files you’ll want to edit to get up and running.    

### Site Wide Configuration
`_config.yml` is your friend. Open it up and personalize it. Most variables are self explanatory but here's an explanation of each if needed:

#### title

The title of your site... shocker!

Example `title: My Awesome Site`

#### bio

The description to show on your homepage.

#### description

The description to use for meta tags and navigation menu.

#### url

Used to generate absolute urls in `sitemap.xml`, `feed.xml`, and for generating canonical URLs in `<head>`. When developing locally either comment this out or use something like `http://localhost:4000` so all assets load properly. *Don't include a trailing `/`*.

Examples:

{% highlight yaml %}
url: http://taylantatli.me/Moon
url: http://localhost:4000
url: //cooldude.github.io
url:
{% endhighlight %}

#### reading_time

Set true to show reading time for posts. And set `words_per_minute`, default is 200.

#### logo
Your site's logo. It will show on homepage and navigation menu. Also used for twitter meta tags.

#### background
Image for background. If you don't set it, color will be used as a background.

#### Google Analytics and Webmaster Tools

Google Analytics UA and Webmaster Tool verification tags can be entered in `_config.yml`. For more information on obtaining these meta tags check [Google Webmaster Tools](http://support.google.com/webmasters/bin/answer.py?hl=en&answer=35179) and [Bing Webmaster Tools](https://ssl.bing.com/webmaster/configure/verify/ownership) support.

#### MathJax
It's enabled. But if you don't want to use it. Set it false in  `_config.yml`.

#### Disqus Comments
Set your disqus shortname in `_config.yml` to use comments.

---

### Navigation Links

To set what links appear in the top navigation edit `_data/navigation.yml`. Use the following format to set the URL and title for as many links as you'd like. *External links will open in a new window.*

{% highlight yaml %}
- title: Home
  url: /

- title: Blog
  url: /blog/

- title: Projects
  url: /projects/

- title: About
  url: /about/

- title: Moon
  url: http://taylantatli.me/Moon
{% endhighlight %}

---

## Layouts and Content

Moon Theme use [Jekyll Compress](https://github.com/penibelst/jekyll-compress-html) to compress html output. But it can cause errors if you use "linenos" (line numbers). I suggest don't use line numbers for codes, because it won't look good with this theme, also i didn't give a proper style for them. If you insist to use line numbers, just remove `layout: compress` string from layouts. It will disable compressing.

### Feature Image

You can set feature image per post. Just add `feature: some link` to your post's front matter.

```
feature: /assets/img/some-image.png
or
feaure: http://example.com/some-image.png
```    
 This also will be used for twitter card:

![Moon Twitter Card](https://cloud.githubusercontent.com/assets/754514/14509719/61c5751c-01d6-11e6-8c29-ce8ccad149bf.png)

### Comments
To show disqus comments for your post add `comments: true` to your post's front matter.

---

## Questions?

Found a bug or aren't quite sure how something works? By all means [file a GitHub Issue](https://github.com/TaylanTatli/Moon/issues/new). And if you make something cool with this theme feel free to let me know.

---

## License

This theme is free and open source software, distributed under the MIT License. So feel free to use this Jekyll theme on your site without linking back to me or including a disclaimer. -->
