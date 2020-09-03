---
title: notebook
sidebar_sort_order: 180
sidebar_category: site
sidebar_link_categories: testing development idea shelved site
---
{% for _status_and_title in site.game_statuses -%}
{%   assign _status = _status_and_title[0] -%}
{%   assign _title = _status_and_title[1] -%}
{%   if _status == 'published' -%}
{%     continue -%}
{%   endif -%}
{%   assign _status_pages = site.pages | where_exp: "item": "item.game.status == _status" -%}
{%   for child in _status_pages -%}
{%     if forloop.first -%}

## {{ _title }}

{%     endif -%}
{%     include template_gamelink.md game=child.game title=child.title url=child.url %}
{%   endfor -%}
{% endfor -%}
