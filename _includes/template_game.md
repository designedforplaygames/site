<div>
[_Purchase **{{include.title}}** at The Game Crafter_](https://www.thegamecrafter.com/games/{{include.game.tgc_id}})
</div>
<div class="row">
<div class="two columns">
{% if include.game.images.logo != null -%}
![{{include.title}} Shop Logo]({{ include.game.images.logo | relative_url }})
{% endif %}
| Players | {{include.game.min_players}} - {{include.game.max_players}} |
| Age | {{include.game.min_age}} + |
| Time | {{include.game.time_range}} |
| Type | {{include.game.type}} |
{% if include.game.status != "production" -%}
| Status | <span class="status {{include.game.status|slugify}}">{{ include.game.status }}</span> |
{% endif %}

</div>
<div class="two columns">
{% if include.game.images.blurb != null -%}
![{{include.title}} Box]({{ include.game.images.blurb | relative_url }}){:align="right"}
{% endif -%}
{{include.game.blurb}}
</div>
</div>
<div class="row">
{% for _action_shot in include.game.images.action_shots -%}
{%   if forloop.last -%}
{%     if forloop.first -%}
{%       assign _align = "center" -%}
{%     else -%}
{%       assign _align = "right" -%}
{%     endif -%}
{%   else -%}
{%     assign _align = "left" -%}
{%   endif -%}
![{{include.title}} {{_action_shot.title}}]({{ {{_action_shot.asset | relative_url }}){:width="320" align="{{_align}}"}
{% endfor -%}
</div>
