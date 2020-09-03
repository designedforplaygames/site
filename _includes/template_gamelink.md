<div class="row" style="margin-left: 2rem">
### [{{include.title}}]({{include.url | relative_url}})

{% if include.game.images.logo.asset != null -%}
<div style="float:left">
![{{include.title}}{% if include.game.images.logo.title != null %} {{include.game.images.logo.title}}{% endif %}]({{ include.game.images.logo.asset | relative_url }}){: style="margin-right: 10px" {% if include.game.images.logo.display_width != null %}width="{{ include.game.images.logo.display_width }}"{% endif %} {% if include.game.images.logo.display_height != null %}height="{{ include.game.images.logo.display_height }}"{% endif %} }
</div>
{% endif -%}
<div style="float:left">

| Players | {{include.game.min_players}} - {{include.game.max_players}} |
| Age | {{include.game.min_age}} + |
| Time | {{include.game.time_range}} |
| Type | {{include.game.type}} |
{% if include.game.status != "published" -%}
| Status | <span class="status {{include.game.status|slugify}}">{{ site.game_statuses[include.game.status] }}</span> |
{% endif %}
{: width="50%"}

</div>
</div>
