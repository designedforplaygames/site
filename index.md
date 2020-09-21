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

{%- comment -%}
The following lines each have two trailing spaces.  **these trailing spaces are important** to force line breaks after each line!
{%- endcomment -%}
the designed for play logo uses the [Henry Morgan Hand](https://www.dafont.com/henry-morgan-hand.font) font by Manfried Klein, available on [dafont.com](https://www.dafont.com).  
this site uses the [Syne](https://fonts.google.com/specimen/Syne) font family by Bonjour Monde and Lucas Descroix, available on [Google Fonts](https://fonts.google.com).  
the theme for this site is a customized version of the [Hydeout](https://github.com/fongandrew/hydeout) Jekyll theme.  

## what's new?

{%- comment -%}
########################################################################
###                  capture total number of posts                   ###
########################################################################
{%- endcomment -%}
{%- capture posts_count -%}{{ site.posts | size }}{%- endcapture -%}
{%- comment -%}
########################################################################
###                  capture excerpt configurations                  ###
########################################################################
{%- endcomment -%}
{%- capture excerpt_count -%}{{ site.front_news.excerpt_posts | default: -1 | to_integer }}{%- endcapture -%}
{%- capture excerpt_months -%}{{ site.front_news.excerpt_months | default: -1 | to_integer }}{%- endcapture -%}
{%- capture excerpt_weeks -%}{{ site.front_news.excerpt_weeks | default: -1 | to_integer }}{%- endcapture -%}
{%- capture excerpt_days -%}{{ site.front_news.excerpt_days | default: -1 | to_integer }}{%- endcapture -%}
<!-- trying fixed %- .. -% ... -->
<!-- excerpt_months={{excerpt_months}} excerpt_weeks={{excerpt_weeks}} excerpt_days={{excerpt_days}} -->
{%- comment -%}
########################################################################
###            convert excerpt time periods into seconds             ###
########################################################################
{%- endcomment -%}
{%- if excerpt_months != "-1" -%}
{%- capture excerpt_earliest_seconds -%}{{ excerpt_months | times: 30 | times: 86400 }}{%- endcapture -%}
{%- elsif excerpt_weeks != "-1" -%}
{%- capture excerpt_earliest_seconds -%}{{ excerpt_weeks | times: 7 | times: 86400 }}{%- endcapture -%}
{%- elsif excerpt_days != "-1" -%}
{%- capture excerpt_earliest_seconds -%}{{ excerpt_days | times: 86400 }}{%- endcapture -%}
{%- else -%}
{%- assign excerpt_earliest_seconds = -1 -%}
{%- endif -%}
{%- comment -%}
########################################################################
###            calculate earliest timestamp for excerpts             ###
########################################################################
{%- endcomment -%}
{%- if excerpt_earliest_seconds != -1 -%}
{%- capture excerpt_earliest -%}{{ "now" | date: "%s" | minus: excerpt_earliest_seconds }}{%- endcapture -%}
{%- else -%}
{%- assign excerpt_earliest = -1 -%}
{%- endif -%}
<!-- showing at most {{excerpt_count}} excerpts to no earlier than {{excerpt_earliest}} ({{excerpt_earliest_seconds}}) -->
{%- comment -%}
########################################################################
###                  capture summary configurations                  ###
########################################################################
{%- endcomment -%}
{%- capture summary_count -%}{{ site.front_news.summary_posts | default: posts_count }}{%- endcapture -%}
{%- capture summary_months -%}{{ site.front_news.summary_months | default: -1 | to_integer }}{%- endcapture -%}
{%- capture summary_weeks -%}{{ site.front_news.summary_weeks | default: -1 | to_integer }}{%- endcapture -%}
{%- capture summary_days -%}{{ site.front_news.summary_days | default: -1 | to_integer }}{%- endcapture -%}
<!-- summary_months={{summary_months}} summary_weeks={{summary_weeks}} summary_days={{summary_days}} -->
{%- comment -%}
########################################################################
###            convert summary time periods into seconds             ###
########################################################################
{%- endcomment -%}
{%- if summary_months != "-1" -%}
{%- capture summary_earliest_seconds -%}{{ summary_months | times: 30 | times: 86400 }}{%- endcapture -%}
{%- elsif summary_weeks != "-1" -%}
{%- capture summary_earliest_seconds -%}{{ summary_weeks | times: 7 | times: 86400 }}{%- endcapture -%}
{%- elsif summary_days != "-1" -%}
{%- capture summary_earliest_seconds -%}{{ summary_days | times: 86400 }}{%- endcapture -%}
{%- else -%}
{%- assign summary_earliest_seconds = -1 -%}
{%- endif -%}
{%- comment -%}
########################################################################
###            calculate earliest timestamp for summaries            ###
########################################################################
{%- endcomment -%}
{%- if summary_earliest_seconds != -1 -%}
{%- capture summary_earliest -%}{{ "now" | date: "%s" | minus: summary_earliest_seconds }}{%- endcapture -%}
{%- else -%}
{%- assign summary_earliest = -1 -%}
{%- endif -%}
<!-- showing at most {{summary_count}} summaries to no earlier than {{summary_earliest}} ({{summary_earliest_seconds}}) -->
{%- comment -%}
########################################################################
###                         display excerpts                         ###
########################################################################
{%- endcomment -%}
{%- assign excerpts = 0 -%}
{%- for post in site.posts -%}
{%- if excerpt_count != "-1" and excerpts == excerpt_count -%}
{%- break -%}
{%- endif -%}
{%- capture post_timestamp -%}{{ post.date | date: "%s" }}{%- endcapture -%}
{%- if excerpt_earliest != "-1" and post_timestamp < excerpt_earliest -%}
{%- break -%}
{%- endif -%}
{%- capture excerpts -%}{{ excerpts | plus: 1 }}{%- endcapture -%}
<article class="post-body" markdown="0">
<h3 class="post-title">
<a href="{{post.url | relative_url }}">{{post.title}}</a>
</h3>
{%- include post-meta.html post=post -%}
{%- if post.excerpt -%}
{{ post.excerpt }}
{%- comment -%}Excerpt may be equal to content. Check.{%- endcomment -%}
{%- capture content_words -%}{{ post.content | number_of_words }}{%- endcapture -%}
{%- capture excerpt_words -%}{{ post.excerpt | number_of_words }}{%- endcapture -%}
{%- if content_words != excerpt_words -%}
<a href="{{ post.url | relative_url }}">More &hellip;</a>
{%- endif -%}
{%- else -%}{%- comment -%} post.excerpt {%- endcomment -%}
{{ post.content }}
{%- endif -%}{%- comment -%} post.excerpt {%- endcomment -%}
</article>
{%- endfor -%}
{%- comment -%}
########################################################################
###                        display summaries                         ###
########################################################################
{%- endcomment -%}
{%- assign summaries = 0 -%}
{%- for post in site.posts offset:excerpts -%}
{%- if summary_posts != "-1" and summaries == summary_posts -%}
{%- break -%}
{%- endif -%}
{%- capture post_timestamp -%}{{ post.date | date: "%s" }}{%- endcapture -%}
{%- if summary_earliest != "-1" and post_timestamp < summary_earliest -%}
{%- break -%}
{%- endif -%}
{%- capture summaries -%}{{ excerpts | plus: 1 }}{%- endcapture -%}
<article class="post-summary" markdown="0">
<h3 class="post-title">
<a href="{{post.url | relative_url }}">{{post.title}}</a>
</h3>
{%- include post-meta.html post=post -%}
<a href="{{ post.url | relative_url }}">Read post &hellip;</a>
</article>
{%- endfor -%}
