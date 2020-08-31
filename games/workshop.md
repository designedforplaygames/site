---
title: games workshop
---
{% for _status in "testing=In Playtesting,idea=Idea Stage,shelved=On The Shelf" | split: "," -%}
{%   assign _status = _status | split: "=" -%}
{%   assign _title = _status[1] -%}
{%   assign _status = _status[0] -%}
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
