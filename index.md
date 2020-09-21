---
title: about
sidebar_sort_order: 100
sidebar_category: site
sidebar_link_categories: site
---

**designed for play**&trade; is a one-person game studio.  i currently have one game (self-)published, with several more either in testing or in the idea stage.

[@designedforplay](https://twitter.com/designedforplay)  
[designedforplaygames@gmail.com](mailto:designedforplaygames@gmail.com)

## who i am

i'm a computer geek and long time board game fan.  i grew up playing board and card games with family, with friends, at high school _(mr kennedy's room in high school was the place to go for strategy games!)_, and continued all through college and ever since.

i'm a unix system administrator by profession, but i hope to keep designing games on the side for as long as my creativity keeps up.

## colophon

{% comment %}
The following lines each have two trailing spaces.  **these trailing spaces are important** to force line breaks after each line!
{% endcomment %}
the designed for play logo uses the [Henry Morgan Hand](https://www.dafont.com/henry-morgan-hand.font) font by Manfried Klein, available on [dafont.com](https://www.dafont.com).  
this site uses the [Syne](https://fonts.google.com/specimen/Syne) font family by Bonjour Monde and Lucas Descroix, available on [Google Fonts](https://fonts.google.com).  
the theme for this site is a customized version of the [Hydeout](https://github.com/fongandrew/hydeout) Jekyll theme.  

## what's new?

{% comment %}
########################################################################
###                  capture total number of posts                   ###
########################################################################
{% endcomment %}
{% capture posts_count %}
{{ site.posts | size }}
{% endcapture %}
<!-- number of posts: {{posts_count}} -->
{% comment %}
########################################################################
###                  capture excerpt configurations                  ###
########################################################################
{% endcomment %}
{% capture excerpt_count %}
{{ site.front_news.excerpt_posts | default: -1 }}
{% endcapture %}
<!-- excerpt_count: {{excerpt_count}} -->
{% capture excerpt_months %}
{{ site.front_news.excerpt_months | default: -1 }}
{% endcapture %}
<!-- excerpt_months: {{excerpt_months}} -->
{% capture excerpt_weeks %}
{{ site.front_news.excerpt_weeks | default: -1 }}
{% endcapture %}
<!-- excerpt_weeks: {{excerpt_weeks}} -->
{% capture excerpt_days %}
{{ site.front_news.excerpt_days | default: -1 }}
{% endcapture %}
<!-- excerpt_days: {{excerpt_days}} -->
{% comment %}
########################################################################
###            convert excerpt time periods into seconds             ###
########################################################################
{% endcomment %}
{% if excerpt_months != -1 %}
{% capture excerpt_earliest_seconds %}
{{ excerpt_months | times: 30 | times: 86400 }}
{% endcapture %}
{% elsif excerpt_weeks != -1 %}
{% capture excerpt_earliest_seconds %}
{{ excerpt_weeks | times: 7 | times: 86400 }}
{% endcapture %}
{% elsif excerpt_days != -1 %}
{% capture excerpt_earliest_seconds %}
{{ excerpt_days | times: 86400 }}
{% endcapture %}
{% else %}
{% assign excerpt_earliest_seconds = -1 %}
{% endif %}
{% comment %}
########################################################################
###            calculate earliest timestamp for excerpts             ###
########################################################################
{% endcomment %}
{% if excerpt_earliest_seconds != -1 %}
{% capture excerpt_earliest %}
{{ "now" | date: "%s" | minus: excerpt_earliest_seconds }}
{% endcapture %}
{% else %}
{{ assign excerpt_earliest = -1 }}
{% endif %}
<!-- excerpt_earliest: {{ excerpt_earliest }} -->
{% comment %}
########################################################################
###                  capture summary configurations                  ###
########################################################################
{% endcomment %}
{% capture summary_count %}
{{ site.front_news.summary_posts | default: posts_count }}
{% endcapture %}
<!-- max summaries: {{summary_count}} -->
{% capture summary_months %}
{{ site.front_news.summary_months | default: -1 }}
{% endcapture %}
{% capture summary_weeks %}
{{ site.front_news.summary_weeks | default: -1 }}
{% endcapture %}
{% capture summary_days %}
{{ site.front_news.summary_days | default: -1 }}
{% endcapture %}
{% comment %}
########################################################################
###            convert summary time periods into seconds             ###
########################################################################
{% endcomment %}
{% if summary_months != -1 %}
{% capture summary_earliest_seconds %}
{{ summary_months | times: 30 | times: 86400 }}
{% endcapture %}
{% elsif summary_weeks != -1 %}
{% capture summary_earliest_seconds %}
{{ summary_weeks | times: 7 | times: 86400 }}
{% endcapture %}
{% elsif summary_days != -1 %}
{% capture summary_earliest_seconds %}
{{ summary_days | times: 86400 }}
{% endcapture %}
{% else %}
{% assign summary_earliest_seconds = -1 %}
{% endif %}
{% comment %}
########################################################################
###            calculate earliest timestamp for summaries            ###
########################################################################
{% endcomment %}
{% if summary_earliest_seconds != -1 %}
{% capture summary_earliest %}
{{ "now" | date: "%s" | minus: summary_earliest_seconds }}
{% endcapture %}
<!-- earliest summary: {{excerpt_earliest|date:"%c"}} -->
{% else %}
{{ assign summary_earliest = -1 }}
<!-- no earliest summary -->
{% endif %}
{% comment %}
########################################################################
###                         display excerpts                         ###
########################################################################
{% endcomment %}
{% increment excerpts %}
{% for post in site.posts %}
{% if excerpt_posts != -1 and excerpts == excerpt_posts %}
<!-- stopping excerpts after {{excerpts}} posts -->
{% break %}
{% endif %}
{% capture post_timestamp %}
{{ post.date | date: "%s" }}
{% endcapture %}
{% if excerpt_earliest != -1 and post_timestamp > excerpt_earliest %}
<!-- stopping excerpts at post timestamp {{post_timestamp}} before earliest excerpt {{excerpt_earliest}} -->
{% break %}
{% endif %}
{% increment excerpts %}
<article class="post-body" markdown="0">
<h3 class="post-title">
<a href="{{post.url | relative_url }}">{{post.title}}</a>
</h3>
{% include post-meta.html post=post %}
{% if post.excerpt %}
{{ post.excerpt }}
{% comment %}Excerpt may be equal to content. Check.{% endcomment %}
{% capture content_words %}
{{ post.content | number_of_words }}
{% endcapture %}
{% capture excerpt_words %}
{{ post.excerpt | number_of_words }}
{% endcapture %}
{% if content_words != excerpt_words %}
<a href="{{ post.url | relative_url }}">More &hellip;</a>
{% endif %}
{% else %}{% comment %} post.excerpt {% endcomment %}
{{ post.content }}
{% endif %}{% comment %} post.excerpt {% endcomment %}
</article>
{% endfor %}
{% comment %}
########################################################################
###                        display summaries                         ###
########################################################################
{% endcomment %}
{% increment summaries %}
{% for post in site.posts offset:excerpts %}
{% if summary_posts != -1 and summaries == summary_posts %}
<!-- stopping summaries after {{summaries}} posts -->
{% break %}
{% endif %}
{% capture post_timestamp %}
{{ post.date | date: "%s" }}
{% endcapture %}
{% if summary_earliest != -1 and post_timestamp > summary_earliest %}
<!-- stopping summaries at post timestamp {{post_timestamp}} before earliest summary {{summary_earliest}} -->
{% break %}
{% endif %}
{% increment summaries %}
<article class="post-summary" markdown="0">
<h3 class="post-title">
<a href="{{post.url | relative_url }}">{{post.title}}</a>
</h3>
{% include post-meta.html post=post %}
<a href="{{ post.url | relative_url }}">Read post &hellip;</a>
</article>
{% endfor %}
