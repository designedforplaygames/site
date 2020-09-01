---
title: games
---
{% for status in "published"|split(",") %}
{%   for child in site.pages -%}
{%     if child.game.status == status -%}
{%       include template_gamelink.md game=child.game title=child.title url=child.url %}
{%     endif %}
{%   endfor %}
{% endfor %}
