---
title: games workshop
sidebar_link: true
sidebar_sort_order: 100
---
{% assign _statuses = "testing=In Playtesting,idea=Idea Stage,shelved=On The Shelf" | split: "," -%}
{% for _status_and_title in _statuses -%}
{%   assign _status_and_title_split = _status_and_title | split: "=" -%}
{%   assign _title = _status_and_title_split[1] -%}
{%   assign _status = _status_and_title_split[0] -%}
{%   for child in site.pages -%}
{%     if child.game.status == _status -%}
{%       if _status != _last_status -%}
{%         assign _last_status = _status -%}

## {{ _title }}

{%       endif -%}
{%       include template_gamelink.md game=child.game title=child.title url=child.url %}
{%     endif -%}
{%   endfor -%}
{% endfor -%}
