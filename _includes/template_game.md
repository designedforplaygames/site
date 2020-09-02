{% if include.game.tgc_id != null -%}
<div>
[_{% if include.game.status == "published" %}Purchase{% else %}Preview{% endif %} **{{include.title}}** at The Game Crafter_](https://www.thegamecrafter.com/games/{{include.game.tgc_id}})
</div>
{% endif -%}
<div class="row">
<div class="two columns">
{% if include.game.images.logo.asset != null -%}
![{{include.title}}{% if include.game.images.logo.title != null %} {{include.game.images.logo.title}}{% endif %}]({{ include.game.images.logo.asset | relative_url }}){: {% if include.game.images.logo.display_width != null %}width="{{ include.game.images.logo.display_width }}"{% endif %} {% if include.game.images.logo.display_height != null %}height="{{ include.game.images.logo.display_height }}"{% endif %} }
{% endif %}
| Players | {{include.game.min_players}} - {{include.game.max_players}} |
| Age | {{include.game.min_age}} + |
| Time | {{include.game.time_range}} |
| Type | {{include.game.type}} |
{% if include.game.status != "published" -%}
| Status | <span class="status {{include.game.status|slugify}}">{{ include.game.status }}</span> |
{% endif %}

</div>
<div class="two columns">
{% if include.game.images.blurb.asset != null -%}
![{{include.title}}{% if include.game.images.blurb.title != null %} {{include.game.images.blurb.title}}{% endif %}]({{ include.game.images.blurb.asset | relative_url }}){:align="right" {% if include.game.images.blurb.display_width != null %}width="{{ include.game.images.blurb.display_width }}"{% endif %} {% if include.game.images.blurb.display_height != null %}height="{{ include.game.images.blurb.display_height }}"{% endif %} }
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
![{{include.title}}{% if _action_shot.title != null %} {{_action_shot.title}}{% endif %}]({{ _action_shot.asset | relative_url }}){:align="{{_align}}" {% if _action_shot.display_width != null %}width="{{ _action_shot.display_width }}"{% endif %} {% if _action_shot.display_height != null %}height="{{ _action_shot.display_height }}"{% endif %} }
{% endfor -%}
</div>
